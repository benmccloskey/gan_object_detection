# Benefits of using blended generative adversarial network images to augment classification model training data sets
link: https://journals.sagepub.com/doi/full/10.1177/15485129231170225

**GAN_Code** - Folder contains the code for the Generative Adversarial Networks used to create deepfakes. 
Architectures used:
1. Deep Convolutional GAN (DCGAN)
2. Conditional DCGAN
3. Wasserstein GAN (WGAN)
4. Conditioned WGAN

General Steps of Research:
1. Train Object Detection Model - Dataset, no augmented images
2. Create deepfakes of items of interest within images (Cars, Trucks, Vans)
3. Embedded deepfake images within orginal imahes
4. Retrain Object Detectio Model w/ augmented dataset

**Excursion**
1. Use a completely different test set with images of the same class, but contrasting in physical depiction
