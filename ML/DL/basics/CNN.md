## Basics

Converlutions
- N * N   Filter: F * F
- Output: N-F+1 * N-F+1


Why Padding?
- Problems Exists
    - shrink output.
    - throw away info from edge.
    
- Valid and Same convolutions
    - valid: P = 0
    - same: pad so that output size is the same as the input size
        - N + 2P - F + 1 = N   => p = (F -1) / 2

- F is usually odd
    - P = (F-1)/2 Symmetric
    - F*F have a central pixel talk about the positon of the filter

- Advantage
    - It allows you to use a CONV layer without necessarily shrinking the height and width of the volumes. This is important for building deeper networks, since otherwise the height/width would shrink as you go to deeper layers. 
    - It helps us keep more of the information at the border of an image. Without padding, very few values at the next layer would be affected by pixels as the edges of an image.

![](../../../images/CNN/zero_padding.jpg)

![](../../../images/CNN/stride.jpg)


    
![](../../../images/cnn_size_cal.jpg)



![](../../../images/cnn_advantage.jpg)


## Classic CNN Papers
- LeNets. 1998. Gradient-based learning applied to document recognition. LeCun. 
    - 60000 parameters.
- AlexNets. 2012. ImageNet classification with deep convolutional neural networks.
    - 60 million parameters.
    - Local Response Normalization(LRN).
- VGG-16. 2015. Very deep convolutional networks for large-scale image recognition.
    - channel * 2, nh & hw / 2, 很规整.
    - 16 weight layers.
- ResNets. 2015. Deep residual networks for image recognition.
    - every tow layer, add before two layer.
    - ![](../../../images/CNN/resnet.jpg)
- 2013. Network in network.

## CNN tips
- 随着层数加深，nh, nw降低，nc增大
- conv, pool, conv, pool, ..., fc, fc, ..., output
- one by one conv
    - shrinking nc
    -  
## Terms
- FC: full-connected layer
