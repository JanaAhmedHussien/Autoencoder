# Denoising Autoencoder for Image Denoising

## Objective

In this project, we design, implement, and evaluate a **Convolutional Denoising Autoencoder (CDAE)** to explore how convolutional autoencoders can remove noise from images while preserving their core features. This project uses the **Oxford-IIIT Pet Dataset**, which contains over 7,000 images of 37 different pet breeds. The goal is to train a CDAE to reconstruct clean images from noisy versions and evaluate the performance using various metrics.

## Dataset

This project uses the **Oxford-IIIT Pet Dataset**, which includes diverse images of 37 cat and dog breeds. The dataset features different textures, colors, and shapes, making it ideal for exploring image denoising techniques. The images can be downloaded from the following link:
[Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/).

The dataset contains:
- Over 7,000 images.
- 37 pet breeds, including various cats and dogs.

### Data Preprocessing

1. **Loading the Dataset**: The images from the Oxford-IIIT Pet Dataset are loaded and explored.
2. **Data Splitting**: The data is split into training and testing sets (e.g., 80% for training, 20% for testing).
3. **Noise Addition**: Gaussian noise or salt-and-pepper noise is added to the original images to create a noisy dataset.
4. **Shape Consistency**: The noisy images maintain the same shape and size as the original clean images to ensure consistency during training.

## CNN Architecture

The CDAE model is constructed using a Convolutional Autoencoder architecture. The architecture consists of the following components:

### 1. Encoder
- **Convolutional Layers**: Used to extract features from the noisy images.
- **Activation Function**: ReLU is applied after each convolution to introduce non-linearity.
- **Batch Normalization**: Helps stabilize and accelerate training.
- **Max-Pooling**: Reduces the spatial dimensions of the feature maps.

### 2. Decoder
- **Upsampling**: The decoder upsamples the compressed representation to reconstruct the original image size.
- **Conv2D Transpose Layers**: Used for upsampling the feature maps and reconstructing the image.

### 3. Model Compilation
- **Optimizer**: Adam optimizer is used to minimize the loss function.
- **Loss Function**: Mean Squared Error (MSE) is used as the loss function to evaluate the quality of reconstruction.

## Model Training

The CDAE model is trained using the noisy dataset while validating against the clean dataset. During training:
- **Training Loss**: Mean Squared Error between the noisy image and the clean image.
- **Validation Loss**: Evaluates the performance on the validation set.
- The model is trained for several epochs, and training progress is visualized using metrics like loss and validation loss.

## Evaluation

After training the model, the performance is evaluated using the following steps:
1. **Visual Comparison**: The following images are visualized for qualitative comparison:
    - Noisy images (input).
    - Denoised images (output of the CDAE).
    - Clean images (ground truth).
2. **Metrics**: The CDAE's performance is measured using **Mean Squared Error (MSE)** between the denoised and clean images to quantify how well the model has removed noise.

## Hyperparameter Tuning (Optional)

- Experiment with different hyperparameters such as:
  - Number of convolutional layers.
  - Number of filters in each layer.
  - Batch size.
  - Learning rate.
  - Regularization techniques like dropout or L2 regularization to improve model generalization.


