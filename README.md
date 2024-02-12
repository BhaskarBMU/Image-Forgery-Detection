Introduction
In today's digital landscape, distinguishing between authentic and modified photos is increasingly challenging due to advanced image editing tools. This project addresses the issue of image forgery using deep learning techniques, focusing on the CoMoFoD dataset—a specialized collection for copy-move forgery detection.

Dataset Overview
Size: 10,400 images (512 x 512 pixels)
Components per set:
Original Image
Colored Mask
Binary Mask
Forged Image
Alterations include:
JPEG compression
Noise addition
Image blurring
Brightness change
Color reduction
Contrast adjustments
Image Preprocessing
The dataset underwent preprocessing to enhance model performance:

Noise removal
Color reduction
Histogram equalization
Resizing to 256 x 256 pixels
Data augmentation: scaling, compression, etc.
Data Loader
DataLoaders were utilized for streamlined preprocessing, including histogram equalization, color correction, noise removal, and image augmentation. Batches of 32 images were generated with preprocessing, augmentation, and normalization.

CNN Models
Several CNN models were employed for comparative analysis:

VGG16

Architecture: Repeated convolutional layers, max-pooling, and dense layers with 3x3 convolutional filters.
Spatial hierarchies understanding.
MobileNet

Lightweight architecture with depth-wise separable convolutions.
Reduced computational load.
ResNet50

Uses residual connections to address vanishing gradient problem in deep networks.
Facilitates training of deep neural networks.
DenseNet121

Feature reuse and gradient flow for capturing intricate patterns.
Vanilla Model

Simplistic CNN with 7 convolutional and pooling layers.
Model Training and Evaluation
Input Size: 256 x 256 RGB images.
Output: Binary classification (forged or real) using softmax and categorical cross entropy.
Evaluation: Comparative analysis of models to identify the most effective for image forgery detection.
Conclusion
This project contributes to ongoing efforts in preserving the integrity of digital images. By employing a multi-model approach on the CoMoFoD dataset, the aim is to enhance the ability to detect forged images, ensuring trust in visual content across diverse applications.


![image](https://github.com/BhaskarBMU/Image-Forgery-Detection/assets/114286743/459166da-1d9a-4160-8d5e-4adf44b9d5f6)

