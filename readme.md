# Benefits of using blended generative adversarial network images to augment classification model training data sets
link: https://journals.sagepub.com/doi/full/10.1177/15485129231170225

**Blended_GAN_Object_Detection_Research** - Object detection model training file

**./yolo_training_support_files** - Folder contains scripts and configuration files for training Yolov4-Tiny

**./GAN_Code** - Folder contains the code for the Generative Adversarial Networks used to create deepfakes. 
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

**Related Towards Data Science Publications**
1. Deep Learning Model Visualization Tools: Which is best?: https://towardsdatascience.com/deep-learning-model-visualization-tools-which-is-best-83ecbe14fa7
2. Image Quality Assessment of Deepfakes Produced by Different Generative Adversarial Networks: https://towardsdatascience.com/image-quality-assessment-of-deepfakes-produced-by-different-generative-adversarial-networks-b20513539cc6
3.Convolutional Neural Networks: From An Everyday Understanding to a More Technical Deep Dive: https://towardsdatascience.com/convolutional-neural-networks-from-an-everyday-understanding-to-a-more-technical-deep-dive-83af329e5d89
