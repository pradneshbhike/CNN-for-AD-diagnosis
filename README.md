# CNN for Alzheimer's Disease Diagnosis
Machine learning has a phenomenal range of application in the health sciences. This code is complete pipeline to build a model that can determine the dementia level of an Alzheimer's patient from their MRI image. This model achieves high ROC AUC score. A CNN using Keras.

Dataset consists of two files - 

Training and Testing both containing a total of around ~5000 images each segregated into the severity of Alzheimer's

Classes and number of images:

1.	Mild Demented: 717
2.	Very Mild Demented: 52
3.	Non-Demented: 2560
4.	Moderate Demented: 1792

Our dataset is not balanced, so we cannot use accuracy as our metric. We will be using ROC AUC. Intuitively, ROC AUC gives a score, with higher scores closer to 1 indicating that the different classes can be distinguishable for the model. A lower score closer indicates that the model cannot distinguish between different classes. A score of 0.5 indicates that the ordering the images is pretty much random.

CNN Architecture:

The next step was to build the model. This can be described in the following 5 steps.

1.	I used five convolutional blocks comprised of separable convolutional 2D layers, max-pooling and batch-normalization.

2.	I used a flatten layer and followed it by four fully connected layers.

3.	Also in between I have used dropouts to reduce over-fitting.

4.	Activation function was Relu throughout except for the last layer where it was Softmax as this is a multilabel classification problem.

5.	I have used Adam as the optimizer and categorical cross-entropy as the loss.

6.	The metrics used is AUC.
