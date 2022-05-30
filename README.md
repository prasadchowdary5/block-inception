An Inception Module is an image model block that aims to approximate an optimal local sparse structure in a CNN. Put simply, it allows for us to use multiple types of filter size, instead of being restricted to a single filter size, in a single image block, which we then concatenate and pass onto the next layer.
Inception V4 was introduced in combination with Inception-ResNet by the researchers a Google in 2016. The main aim of the paper was to reduce the complexity of Inception V3 model which give the state-of-the-art accuracy on ILSVRC 2015 challenge. This paper also explores the possibility of using residual networks on Inception model. This model 

Architectural Changes in Inception-V4:

 In the paper there are two types of Inception architectures were discussed.

Pure Inception architecture (Inception -V4):
The initial set of layers which the paper refers “stem of the architecture” was modified to make it more uniform . These layers are used before Inception block in the architecture.
This model can be trained without partition of replicas unlike the previous versions of inceptions which required different replica in order to fit in memory. This architecture use memory optimization on back propagation to reduce the memory requirement.
Inception architecture with residuals:
The authors of the paper was inspired by the success of Residual Network. Therefore they explored the possibility of combining the Inception with ResNets. They proposed two Residual Network based Inception models: Inception ResNet V1 and Inception ResNet V2. Let’s look at the key highlights of these architectures.
The Inception block used in these architecture are computationally less expensive than original Inception blocks that we used in Inception V4.
Each Inception block is followed by a 1×1 convolution without activation called filter expansion. This is done to scale up the dimensionality of filter bank to match the depth of input to next layer.
The pooling operation inside the Inception blocks were replaced by residual connections. However, pooling operations can be found in reduction blocks. 
In Inception ResNets models, the batch normalization does not used after summations. This is done to reduce the model size to make it trainable on a single GPU.
Both the Inception architectures have same architectures for Reduction Blocks, but have different stem of the architectures. They also have difference in their hyper parameters for training.
It is found that Inception-ResNet V1 have similar computational cost as of Inception V3 and Inception-ResNet V2 have similar computational cost as of Inception V4.
