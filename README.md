# Benefits of using blended generative adversarial network images to augment classification model training data sets
link: https://journals.sagepub.com/doi/full/10.1177/15485129231170225

**Abstract**


Object detection algorithms have reached nearly superhuman levels within the last decade; however, these algorithms require large diverse training data sets to ensure their operational performance matches performance demonstrated during testing. The collection and human labeling of such data sets can be expensive and, in some cases, such as Intelligence, Surveillance and Reconnaissance of rare events it may not even be feasible. This research proposes a novel method for creating additional variability within the training data set by utilizing multiple models of generative adversarial networks producing both high- and low-quality synthetic images of vehicles and inserting those images alongside images of real vehicles into real backgrounds. This research demonstrates a 17.90% increase in mean absolute percentage error, on average, compared to the YOLOv4-Tiny Model trained on the original non-augmented training set as well as a 14.44% average improvement in the average intersection over union rate. In addition, our research adds to a small, but growing, body of literature indicating that the inclusion of low-quality images into training data sets is beneficial to the performance of computer vision models.

**Original MS Thesis** : Using Generative Adversarial Networks to Augment Unmanned Aerial Vehicle Image Classification Training Sets - https://scholar.afit.edu/etd/5362/

**Blended_GAN_Object_Detection_Research** - Object detection model training file

./gan_images - example deepfakes

**./yolo_training_support_files** - Folder contains scripts and configuration files for training Yolov4-Tiny

**./GAN_Code** - Folder contains the code for the Generative Adversarial Networks used to create deepfakes. 
Architectures used:
1. Deep Convolutional GAN (DCGAN)
2. Conditional DCGAN
3. Wasserstein GAN (WGAN)
4. Conditioned WGAN

General Steps of Research:
1. Train Object Detection Model - Dataset, no augmented images
2. Create deepfakes of items of interest within parent images (Cars, Trucks, Vans)
3. Embedded deepfake child images within orginal parent images. Label using labelimg
4. Retrain Object Detection Model w/ augmented dataset

**Excursion**
1. Use a completely different test set with images of the same  children classes, but contrasting in physical depiction. 

**Related Towards Data Science Publications**
1. Deep Learning Model Visualization Tools: Which is best?: https://towardsdatascience.com/deep-learning-model-visualization-tools-which-is-best-83ecbe14fa7
2. Image Quality Assessment of Deepfakes Produced by Different Generative Adversarial Networks: https://towardsdatascience.com/image-quality-assessment-of-deepfakes-produced-by-different-generative-adversarial-networks-b20513539cc6
3.Convolutional Neural Networks: From An Everyday Understanding to a More Technical Deep Dive: https://towardsdatascience.com/convolutional-neural-networks-from-an-everyday-understanding-to-a-more-technical-deep-dive-83af329e5d89
