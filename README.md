# Residual_CNN_Explanation

In this notebook, I try to say the basic topics in order to understand the subject : *Residual,Architecture_of_Resnet50, BottleNeck, Linear BottleNeck,Inverted Residual... , * So that we can finally understand the famous models such as MobileNet architecture
 

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/34R.png" width="500" height="700">

In the table, there is a summary of the output size at every layer and the dimension of the convolutional kernels at every point in the structure.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/Resnets_tabel.jpg" width="600" height="400">

Two-dimensional view:

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/aspect_resnet34.jpg" width="600" height="400">

Conv1:

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/conv1_resnet34.jpg" width="600" height="400">

Conv1+ Max Pooling:First, a padding 1 is created, then we have the (3x3) Max Pooling operation with a stride of 2 .

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/conv-maxpool.jpg" width="600" height="400">

ResNet Layers: Every layer of a ResNet is composed of several blocks.We can see how, as we mentioned previously, the size of the volume does not change within a block. This is because a padding = 1 is used and a stride =1.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig6.jpg" width="600" height="400">

Let’s see how this extends to an entire block, to cover the 2 [3x3, 64] that appears in the table.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig7.jpg" width="600" height="400">

We can see how we have the [3x3, 64] x 3 times within the layer.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig8.jpg" width="600" height="400">

 Represents this down sampling performed by increasing the stride = 2.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig9.jpg" width="600" height="400">

In the shortcut we need to apply one of our down sampling strategies. The 1x1 convolution approach is shown :

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig10.jpg" width="600" height="400">

The final picture looks then like in Figure  where now the 2 output volumes of each thread has the same size and can be added.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig11.jpg" width="600" height="400">

In Figure we can see the global picture of the entire second layer. The behavior is exactly the same for the following layers 3 and 4, changing only the dimensions of the incoming volumes.

<img src="https://github.com/SAMashiyane/Residual_CNN_Explanation/blob/main/image/fig12.jpg" width="600" height="400">









