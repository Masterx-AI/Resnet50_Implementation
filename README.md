## ResNet-50 Model Description:

In recent years of the Deep Learning revolution, neural networks have become deeper, with state-of-the-art networks going from just a few layers (e.g., VGG16) to over a hundred layers. The main benefit of a very deep network is that it can represent very complex functions. It can also learn features at many different levels of abstraction, for example,  edges (at the lower layers) to very complex features (at the deeper layers) in the case of an image.

However, using a deeper network doesn’t always produce favorable outcomes. A huge barrier to training huge neural networks is the phenomenon of vanishing gradients. Very deep networks often have a gradient signal that goes to zero quickly, thus making gradient descent slow. If we see more specifically, during gradient descent, as you backpropagate from the final layer back to the first layer, you are multiplying by the weight matrix on each step, and thus the gradient can decrease exponentially quickly to zero and hindering the training process.

In ResNet architecture, a “shortcut” or a “skip connection” allows the gradient to be directly backpropagated to earlier layers:

The image on the top shows the “main path” through the network. The image on the bottom adds a shortcut to the main path. By stacking these ResNet blocks on top of each other, you can form a very deep network.

There are two main types of blocks are used in a ResNet, depending mainly on whether the input/output dimensions are the same or different.

The identity block is the standard block used in ResNets and corresponds to the case where the input activation has the same dimension as the output activation.

We can use this type of block when the input and output dimensions don’t match up. The difference with the identity block is that there is a CONV2D layer in the shortcut path.

The ResNet-50 model consists of 5 stages each with a convolution and Identity block. Each convolution block has 3 convolution layers and each identity block also has 3 convolution layers. The ResNet-50 has over 23 million trainable parameters.
