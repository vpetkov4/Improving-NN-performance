# Symbol-recognition-and-data-augmentation
This project presents a method to clean a data set of images from duplicates and later augment to run a CNN model

Often when we seek to accumulate a large dataset to run a successful neural network model we use more than one sourse of data, which results to duplication of some of the data.
Naturally this leads to overfitting and poor performance of the model.

In this project I present a simple source to clear the dataset from duplicates and then to augment the dataset sufficiently to train the neural network model.

To illustrate the application of the code, I use the mathematical symbols dataset from https://www.kaggle.com/xainano/handwrittenmathsymbols
The dataset consists of 82 classes of images including mathematical symbols, letters and some elementary functions. I train a deep neural network model on the set before and after 
clearing the duplicates and augmenting the set.

The original set consists of around 376,000 images.

There are many duplicate images, however. After clearing the dataset from all duplicates the number of images decreases to 83,000 images. In some of the classes there are only
a few images left.

I use the Augmentor library to create more samples. The types of image warpings I chose are random small rotations, elastic distortions and constrast changes.
I increase the dataset to 225,000 by concentrating on the classes that had particularly few images.

The preformance of the deep Convolutional Neural Network model was as expected. On the original data the validation accuracy was higher than the training accuracy, which is a good
sign of data duplication. On the reduced data the mean accuracy was over 90% mostly due to the skewed data. The model performed particularly poorly on the sparse classes.
After training the model on the augmented data, which does not contain duplicates, the performance improved. The lowest F1 score for a class improves from 0.15 to 0.73.
For most classes it is around 0.90.  



