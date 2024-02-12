# Image-Forgery-Detection

Use it here:

https://detectimageforgery.streamlit.app/

In today's world it's becoming more and more difficult to identify the difference between real and modified photos that are being shared across various platforms because of the availability of powerful image editing softwares. Digital media's authenticity is at risk by image tampering which includes manipulations such as object removal, splicing, and copy-move.
This project aims to use deep learning techniques to identify forged images. We have used the CoMoFoD dataset, specifically designed for copy-move forgery having 200 different image sets, each undergoing various alterations such as JPEG compression, noise addition, blurring, brightness changes, color reduction, and contrast adjustments.
This report outlines the methodology, experimental setup, and results of the image forgery detection model. By addressing these challenges, we aim to contribute to the ongoing efforts in ensuring the integrity of digital images and bolstering trust in visual content across various applications.

For our project, we will be using the CoMoFoD (Copy Move Forgery Detection) database, which is a collection of 200 distinct images specifically designed to detect manipulated pictures. 
The dataset contains 10,400 Images of dimension 512 X 512.
There are 200 sets of images with each image having following components:
Original Image: The Original picture.
Colored Mask: A mask showing original and manipulated region.
Binary Mask: A binary mask used showing the original and manipulated region.
Forged Image: The manipulated picture.
Each Set of Image contains Images with several alterations which includes:
JPEG compression,
Noise adding,
Image blurring,
Brightness change,
Color reduction,
Contrast adjustments.
Thus Each Set of Images 40 images:
19 Original Images
19 Forged Images
1 Mask
1 Binary Mask

To  detect forged images with the CoMoFoD dataset, a multi-model approach was used to get the best model.
Image Preprocessing
In our framework, we have implemented some image pre-processing methods on our dataset which involves noise removal, color reduction, histogram equalization, and resized image and then applied data augmentation. To augment the data, we have applied certain transformations such as scaling, compression, and others to expose the neural network to diverse image variations. All the images were resized to 256 x 256 pixels and The resulting images, labeled whether they were forged or not, were then splitted into training, and test sets to feed the CNN.
Dataloader
DataLoaders were used to facilitate data to the models with a streamlined preprocessing pipeline. Through DataLoaders, all the preprocessing tasks, including histogram equalization, color correction, noise removal, and image augmentation, were done without altering the actual dataset and batches of 32 images were generated with all operations applied encompassing preprocessing, image augmentation, and normalization.

Building CNN Models
To identify potentially forged images , we built several CNN models for comparative analysis, which included VGG16, MobileNet. ResNet50, DenseNet121, and a Vanilla model. All models shared a standardized input size of 256 x 256,  RGB images. The output layer categorized images into two classes – forged and real using a softmax and categorical cross entropy.
**VGG16**
 The VGG16 model features an architecture with repeated convolutional layers, followed by max-pooling and dense layers with a consistent use of 3x3 convolutional filters, providing a deeper understanding of spatial hierarchies in the input data.
**MobileNet**
MobileNet model offers a lightweight architecture with competitive accuracy with depth-wise separable convolutions, which significantly reduce the computational load.
**ResNet50**
ResNet50 uses residual connections to overcome the vanishing gradient problem in very deep networks. It facilitates the training of deep neural networks, allowing the model to capture intricate features in the data.
**DenseNet121**
DenseNet121 uses feature reuse and gradient flow, which captures intricate patterns.
**Vanilla Model**
The Vanilla model represents a simplistic Convolutional Neural Network with only 7 convolutional and pooling layers.
