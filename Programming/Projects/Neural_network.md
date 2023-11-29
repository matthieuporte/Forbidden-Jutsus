The whole code presented here will soon be available on github #todo 

A neural network is a computational model inspired by the way biological neural networks in the human brain function.
<span class="desktop"><span class="rightimg"><span class="smallimg">![[Colored_neural_network.svg.png]]</span></span></span><span class="mobile">![[Colored_neural_network.svg.png]]</span>

It is used to solve complex problems such as, in our case, recognizing handwritten digits.

The network looks like this. Every circle is called a _**neuron**_ and they connect together _(or fire together)_ through the black arrows called _**weights**_.

A neuron is simply a float value between 0 and 1. The closest it is to one the more activated it is.

So it takes some values as input (it's gonna be our image pixels) and the value of the weights are gonna dictate how each neuron in the next layer will be activated. You repeat the same process until you get to the last layer which is the output layer. 

For our problem of recognising hand written digits, each pixel of the image is gonna be a neuron in the input layer, and the ouput layer will have a size of 10, from 0 to 9.

---

### Meaning

The index of the most activated neuron in the output layer is the answer of the network.
If the output layer looks like this :  $\begin{bmatrix} 0.9 \\ 0.2  \\ \end{bmatrix}$
It means that the network confidently thinks it is the first label. 

Otherwise if it looks like this : $\begin{bmatrix} 0.4 \\ 0.5  \\ \end{bmatrix}$ 
It means that the network isn't really sure of what he is doing.

As you can see here, a layer can be represented as a matrix. This will be very convenient to do computations later on.

---

### The network

 I used a struct to store all the information needed about my network :

```c
typedef struct network
{
	size_t num_layers;
	size_t* sizes;
	matrix* biases;
	matrix* weights;
}network;
```

In the example image the `num_layers` would be 3 and `size` 3 -> 4 -> 2.
I'll go more in depth about matrices later on.

I introduced weights but to have a better grasp on how our networks "thinks" we are going to use _**biases**_ too. Each neuron (except in the output layer) will have a bias, if it is positive then the neuron will have more value for the network and if it is negative then the network won't take it much into account.

Example : maybe the top left pixel isn't as important in our image recognition than middle pixels. In that case a negative bias could be applied to this top left pixel.

The important thing to do here is to set up our initial weights and biases. Initially I didn't think it mattered that much as long as it was random, but I was wrong. Setting very high or very low weights and biases will make it very hard for the network to learn. What we want are values around 0.5 and -0.5 to leave space for improvement.

To do this I use the formula given in [Michael Nielsen's book](http://neuralnetworksanddeeplearning.com/chap3.html#weight_initialization) which is a Gaussian distribution with mean 0 and standard deviation 1 over the square root of the number of weights connecting to the same neuron.

```c
((double)rand() / RAND_MAX) / sqrt((double)weights[i].cols);
```

I used [srand(3)](https://linux.die.net/man/3/srand) to set a seed to my random calls depending on the current time, so every network generation is different.

```c
srand((unsigned int)time(NULL));
```

You can initialize your biases the same way or you can go as far as initializing them as 0 and let the network learn by itself (which I did).

---

### Feedforward

So what really happens when our network "gives an answer" ? 

<span class="desktop"><span class="leftimg"><span class="smallimg">![[tikz32.png]]</span></span></span><span class="mobile">![[tikz32.png]]</span>


The value of a neuron in an inner layer is the sum of all the values of the neurons in the precedent layer times each weight. 

The neurons are $\{a_1,...,a_n\}$ and the associated weights are $\{w_1,...,w_n\}$ then the value of a neuron is $w_1a_1 + ... + w_na_n$. 

But wait I said that the value of a neurons was between 0 and 1 and this could be a big sum ! 

To fix this we use the sigmoid function ($\sigma$)  that brings big values close to 1 and negative values close to 0, it is smooth for small values.


<span class="desktop"><span class="rightimg"><span class="mediumimg">![[1200px-Logistic-curve.svg.png]]</span></span></span><span class="mobile">![[1200px-Logistic-curve.svg.png]]</span>

$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$


So we apply this function to our sum and we get a value between 0 and 1 !

We could do this manually for every neurons but we will save a lot of time by doing operations on matrices.

<span class="desktop"><br><br><br></span>

#### Matrices

>[!tip]
>If you're rusty on matrices go check out [[3 - Matrices]]


To get the next layer you need to multiply the current layer (which is a column matrix) with the weight matrix (each line n is the list of weights to the nth neuron of the next layer), and add the bias matrix (which is a column matrix too) to this result.

As you might know in c you need to pass the size of an array as a parameter. 
You might also know that the dimensions matter when you multiply matrices. 
The thing is you're going to do a lot of matrix multiplication throughout the process, and I coded my matrix function with the idea that I would not make mistakes about thoses dimension.

I was wrong and I lost a lot of time not doing it from the beggining.

This is why I strongly recommend to create a `struct matrix` and to check if the dimensions are corrects in your functions. 

Here's the struct I made :

```c
typedef struct{
    double** mx; //values
    size_t rows;
    size_t cols;
} matrix;
```

---

Ok that's nice, we can get an output from an input, but for now it is a garbage output since we randomly initialized the weights and biases. How can we make our network learn ?

### Backprop

The function used to solve this problem is called backprop. The idea is to have a cost function, computing how good the network is doing. If the result are close from expected then we keep this behavior and try to make it stronger, on the other hand if the network is far from the expected result we will try to nudge his behavior in the right direction.

We will have a training set of images, all labeled, and for each image we will compare the network result with the expected result. 

The cost function I use is the quadratic cost function which is the sum of the difference squared. All you have to know is that it gives back a value and that the smaller that value, the better the network is doing.

Let's say you input a 8 (so really you input all the pixels that make up this 6) and the network gives this answer : 
$$\begin{bmatrix} 0.1 \\ 0.8 \\ 0.4 \\ \vdots\\ 0.6 \\ 0.1  \\ \end{bmatrix}$$

If you've followed so far you'll know that the network gave $1$ as an answer with a value of $0.8$. Since this is now what we want we will go back in the network, following the trail of weights and biases that made this neuron become a $0.8$ and we will update those weights and biases. 
We do this for every neuron in the output layer.

There you go ! our network just became a little better at recognizing this particular 6 !


### Stochastic Gradient Descent

Backprop is nice but for now it has a little too much power. The thing is that we don't want our network to only recognise the 6 in the example above. Maybe the weights that were modified by backprop were in fact useful to recognise a 2.

This is why we need to do a stochastic gradient descent (sgd). The idea is to do a backprop on every element of the training data, do not apply the change but instead keep a track of them. Then we do the sum of all the changes (some are going to be positive and some are going to be negative so it will eventually even out) and apply them to the network.

To optimise this process we will split the training data in mini batches (10 images for example) and apply the changes after every mini batch.

Then we will have a different data set called a test set to see how good our network is doing. It wouldn't be very accurate to test it with the data he's been trained with. 

### MNIST

The [MNIST database](http://yann.lecun.com/exdb/mnist/) is a collection of 70000 handwritten digits to help us train our network. 

Here is how to parse it and use it : #todo

Be aware : training on such large amount of data is going to take some time. I did some [[Pretty Prints]] in my code to see the progress live.

### Save the network

The network is only the values of it's weights and biases. We need to save them in a file and to be able to load them back in our network.

Remember : It's training the network that takes a long time, once you have good weights and biases you're fine. 

### Go more in depth

The network I built is not the most optimised and there is many other ways to do the same things. 
Here's some very good content to go further :

[3blue1brown youtube course](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)

[Neural networks and deep learning](http://neuralnetworksanddeeplearning.com/chap1.html)
  