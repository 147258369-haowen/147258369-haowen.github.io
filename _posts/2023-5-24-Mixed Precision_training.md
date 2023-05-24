# Mix Precision training

Usually, deep learning framework training uses single-precision 32-bit floating-point or 16-bit half-precision floating-point training, but 32-bit takes up too much memory and takes a long time to calculate, while 16-bit half-precision although calculation time Faster, but less accurate. Is there a way to have your cake and eat it too? 

Mixed precision training perfectly solves this problem. Mixed-precision training is an accelerated training method that combines half-precision training and full-precision training. It stores weights and gradients using FP16, half-precision floating point numbers. It has the effect of accelerating training while reducing memory usage.

Using FP16 in the forward and reverse directions, the whole process becomes: the weight is converted from FP32 to FP16 for forward calculation, after the loss is obtained, the gradient is calculated with FP16, then converted to FP32 and updated to the weight of FP32.

The purpose of saving weights in FP32 is to prevent data overflow. FP16 cannot represent values below 2e-24. One is that the update value of the gradient is too small, and FP16 directly becomes 0; the other is that if FP16 represents weights, it is also possible to calculate the results of gradients. becomes 0.

![](/images/mix2.png)


After getting the FP32 loss, enlarge it and save it in FP16 format, perform backpropagation, and convert it to FP32 to scale back when updating.