#  Variational autoencoder (VAE) as a Generator

### Dataset
MNIST images show digits from 0-9 in 28x28 grayscale images. We do not center them at 0, because we will be using a binary cross-entropy loss that treats pixel values as probabilities in [0,1]. We create both a training set and a test set.

### Encoder

We use a convolutional encoder and decoder, which generally gives better performance than fully connected versions that have the same number of parameters.
In convolution layers, we increase the channels as we approach the bottleneck, but note that the total number of features still decreases, since the channels increase by a factor of 2 in each convolution, but the spatial size decreases by a factor of 4. Kernel size 4 is used to avoid biasing problems described here: https://distill.pub/2016/deconv-checkerboard/

### VAE Loss
VAE loss is a linear combination of the reconstruction loss (computed as BCE between original and reconstructed image) and the KL-Divergence between the prior distriubtrion over latent vectors and the distribution estimated by the gerenated for the given image. Here, we give you the KL term and the combintation, but have you implement the reconstruction loss.

### Original images
![image](https://github.com/sumedhreddy90/Variational-Auto-Encoders-MINST/assets/24978535/0ee4c4de-0dca-43f1-bcb1-8a9a6c54fa20)

###  Training Curve
![image](https://github.com/sumedhreddy90/Variational-Auto-Encoders-MINST/assets/24978535/5a1acecb-d460-4b5e-bdeb-672ec630e793)

### VAE reconstruction:
![image](https://github.com/sumedhreddy90/Variational-Auto-Encoders-MINST/assets/24978535/f1153f81-d0d0-43cf-8e2c-d682a54c18c9)

### VAE can generate new digits by drawing latent vectors from the prior distribution. Although the generated digits are not perfect, they are usually better than for a non-variational Autoencoder

![image](https://github.com/sumedhreddy90/Variational-Auto-Encoders-MINST/assets/24978535/04cd3259-0a49-4763-93fd-d41f47133af0)
