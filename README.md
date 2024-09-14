# GAN-based Hand-written Image Generation
## Overview
This project implements a Generative Adversarial Network (GAN) to generate high-quality 64x64 images from random noise. 
<br> The GAN architecture includes a Generator and a Discriminator, trained using adversarial loss to improve the quality of generated images.


## Architecture
### Generator
* Layers:

**  Linear layer to project the latent vector into a higher-dimensional space.
** Series of transpose convolutional layers (ConvTranspose2d) to upsample to 64x64 image dimensions.
** Final convolutional layer to produce a single-channel (grayscale) 64x64 image.
* Input:
 Latent vector of dimension latent_dim.
* Output:
 64x64 grayscale image.
### Discriminator
* Layers:

** Series of convolutional layers (Conv2d) to process the 64x64 image and downsample to a smaller feature map.
** Dropout layer to prevent overfitting.
** Fully connected layers to output a single probability indicating whether the image is real or generated.
* Input:
 64x64 grayscale image.
* Output:
Probability score (single value) indicating whether the image is real or fake.

## Training
* Loss Function: Binary Cross-Entropy Loss.
* Optimizers: Separate optimizers for Generator and Discriminator.
* Training Process:
* Generator: Aims to generate realistic images to fool the Discriminator.
* Discriminator: Aims to distinguish between real and generated images
