# MNIST-DataSet

I used the standard MNIST data set, a collection of 70,000 handwriting samples of the numbers 0-9. Challenge - to predict which number each handwritten image represents.
Each image is 28x28 grayscale pixels, so we can treat each image as just a 1D array, or tensor, of 784 numbers. MNIST provides 55,000 samples in a training data set, 10,000 samples in a test data set, and 5,000 samples in a "validation" data set. 
## TensorFlow Model.
Model Parameters 
- Input Nodes 784
- Hidden Nodes 512
- Final Layer Nodes 10
- Learning Rate 0.1
- No of Epochs 2000
- Batch size 200

 This model gives about 93% accuracy.
## Keras Neural Network Model
Using same model parameters with Keras, I obtained about 98% accuracy on the test data set which is a significant improvement over the Tesnor Flow Model

## Keras Convolutional Neural Network Model

For Convolutional Neural Networks, I started with a 2D convolution of the image - it's set up to take 32 windows, or "filters", of each image, each filter being 3x3 in size. I then run a second convolution on top of that with 64 3x3 windows. Next applying a MaxPooling2D layer that takes the maximum of each 2x2 result to distill the results down into something more manageable. A dropout filter is then applied to prevent overfitting. Next I flatten the 2D layer we have at this stage into a 1D layer. So at this point we can just pretend we have a traditional multi-layer perceptron and feed that into a hidden, flat layer of 128 units. I then applied dropout again to further prevent overfitting. And finally,fed that into the final 10 units where softmax is applied to choose our category of 0-9.
I obtained over 99% accuracy with just 10 epochs!
## Final Comparison
Model  | Accuracy(On Test Data)
------------- | -------------
TensorFlow NN | 0.9389
Keras NN  | 0.98
Keras CNN  | 0.9924

Clearly CNN outperformed the other two models. And this is pretty much in line with the intuition behind CNN as they are better suited to find the spatial features in images. 
