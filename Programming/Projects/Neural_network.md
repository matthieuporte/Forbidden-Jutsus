
  
A neural network is a computational model inspired by the way biological neural networks in the human brain function.
<span class="rightimg"><span class="smallimg">
![[Colored_neural_network.svg.png]]
</span></span>

It is used to solve complex problems such as, in our case, recognizing handwritten digits.

The network looks like this. Every circle is called a _**neuron**_ and they connect together _(or fire together)_ through the black arrows called _**weights**_.

A neuron is simply a float value between 0 and 1. The closest it is to one the more activated it is.

So it takes some values as input (it's gonna be our image pixels) and the value of the weights are gonna dictate how each neuron in the next layer will be activated. You repeat the same process until you get to the last layer which is the output layer. 

The index of the most activated neuron in the output layer is the answer of the network.
If the output layer looks like this : 
$$