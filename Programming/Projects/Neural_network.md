The whole code presented here will soon be available on github #WIP 


A neural network is a computational model inspired by the way biological neural networks in the human brain function.
<span class="rightimg"><span class="smallimg">
![[Colored_neural_network.svg.png]]
</span></span>

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

Here's the whole function, the val parameter is used for setup weights to 0. (You'll see later why)

```c
matrix* init_weights(size_t* sizes, size_t len, int val){
	srand((unsigned int)time(NULL));

	matrix* weights = malloc((len-1) * sizeof(matrix));
	// no weights from the last layer for(size_t i = 0; i < len-1; i++)
	for(size_t i = 0; i < len - 1; i++){
		//nb rows = size next layer
		//nb cols = size current layer
        weights[i] = init_empty_matrix(sizes[i+1],sizes[i]);
		for(size_t j = 0; j < weights[i].rows; j++){
			for(size_t k = 0; k < weights[i].cols; k++){
				weights[i].mx[j][k] = val *
						((double)rand() / RAND_MAX) / 
						sqrt((double)weights[i].cols);
				if (rand() % 2 == 0)
					weights[i].mx[j][k] *= -1;
			}
		}
	}
	return weights;
}
```

As you can see weights is a list of matrices for our whole network.

Notice here that I used [srand(3)](https://linux.die.net/man/3/srand) to set a seed to my random calls depending on the current time, so every network generation is different.

```c
srand((unsigned int)time(NULL));
```

The main line of the precedent call is 

You can initialize your biases the same way or you can go as far as initializing them as 0 and let the network learn by itself (which I did).

---

### Feedforward

So what really happens when our network "gives an answer" ? 


<span class="leftimg"><span class="smallimg">
![[tikz32.png]]
</span></span>

The value of a neuron in an inner layer is the sum of all the values of the neurons in the precedent layer times each weight. 

The neurons are $\{a_1,...,a_n\}$ and the associated weights are $\{w_1,...,w_n\}$ then the value of a neuron is $w_1a_1 + ... + w_na_n$. 

But wait I said that the value of a neurons was between 0 and 1 and this could be a big sum ! 

To fix this we use the sigmoid function ($\sigma$)  that brings big values close to 1 and negative values close to 0, it is smooth for small values.


$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$


```functionplot
---
title: Sigmoid function
bounds: [-5, 5, -0.2, 1.2]
disableZoom: false
grid: true
---
f(x) = 1/(1 + E^(-x))
```

So we apply this function to our sum and we get a value between 0 and 1 !

We could do this manually for every neurons but we will save a lot of time by doing operations on matrices.

#### Matrices

---

### SGD

### Backprop

### MNIST

### Save the network

So our goal is to set the weights so that the network gives interesting outputs.

### Go more in depth

[3blue1brown youtube course](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)

[Neural networks and deep learning](http://neuralnetworksanddeeplearning.com/chap1.html)
  