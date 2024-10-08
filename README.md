# Benefits of using blended generative adversarial network images to augment classification model training data sets
link: https://journals.sagepub.com/doi/full/10.1177/15485129231170225

## **Executive Summary**

This repository contains the code and resources supporting the research on the benefits of using blended Generative Adversarial Network (GAN) images to augment training datasets for classification models. The study focuses on how blending GAN-generated images with real data can enhance the accuracy and robustness of classification models, particularly in scenarios with limited real-world data.

The research, published in [Journal of Defense Modeling an Simulation](https://journals.sagepub.com/doi/full/10.1177/15485129231170225), provides evidence that incorporating synthetic images produced by GANs into training datasets leads to better generalization and improved performance of machine learning models. The biggest impact from this research was the oberservation that blending qualities of deepfake images, where quality is the visual clearness of image, has more of a postivie impact on model performance than using the most clear images. This repository includes all code, data, and supplementary materials used in the research.


**Abstract**

Object detection algorithms have reached nearly superhuman levels within the last decade; however, these algorithms require large diverse training data sets to ensure their operational performance matches performance demonstrated during testing. The collection and human labeling of such data sets can be expensive and, in some cases, such as Intelligence, Surveillance and Reconnaissance of rare events it may not even be feasible. This research proposes a novel method for creating additional variability within the training data set by utilizing multiple models of generative adversarial networks producing both high- and low-quality synthetic images of vehicles and inserting those images alongside images of real vehicles into real backgrounds. This research demonstrates a 17.90% increase in mean absolute percentage error, on average, compared to the YOLOv4-Tiny Model trained on the original non-augmented training set as well as a 14.44% average improvement in the average intersection over union rate. In addition, our research adds to a small, but growing, body of literature indicating that the inclusion of low-quality images into training data sets is beneficial to the performance of computer vision models.

**Original MS Thesis** : Using Generative Adversarial Networks to Augment Unmanned Aerial Vehicle Image Classification Training Sets - https://scholar.afit.edu/etd/5362/


## **Repository Structure**

- **GAN_Code/**:
  - `DCGAN_CGAN_Image_Generation.ipynb`: Notebook for training and evaluating DCGAN models.
  - `WGAN_CWGAN_Image_Generation.ipynb`: Notebook for training and evaluating WGAN models.
  - `README.md`: Documentation for the GAN code directory, detailing the purpose and usage of the included notebooks.

- **yolo_training_support_files/**:
  - `generate_test.py`: Script for loading and preparing test data.
  - `generate_train.py`: Script for loading and preparing training data.
  - `obj.data`, `obj.names`, `yolov4-tiny.cfg`: Configuration files for training the YOLOv4 model.
  - `obj.zip`, `test.zip`: Compressed datasets used for training and testing.
  - `README.md`: Documentation for the YOLOv4 support files, including details on the scripts and configuration files.

- **gan_images/**:
  - `car.png`, `car_reflection.png`, `truck.png`: Example images generated using GANs and used in subsequent classification tasks.
  - `README.md`: Documentation explaining the images, their generation process, and their use in research.
  
  
### **General Steps of Research**:
1. Train Object Detection Model - Dataset, no augmented images
2. Create deepfakes of items of interest within parent images (Cars, Trucks, Vans)
3. Embedded deepfake child images within orginal parent images. Label using labelimg
4. Retrain Object Detection Model w/ augmented dataset

## **Excursion**

This section includes additional experiments and explorations conducted beyond the scope of the primary paper. These excursions delve into alternative GAN architectures, hyperparameter tuning, and the integration of GAN-generated data with other machine learning models. These supplementary studies provide a broader perspective on the versatility and potential of GANs in various domains.

## **Related Towards Data Science Publications**

1. **[Deep Learning Model Visualization Tools: Which is Best?](https://towardsdatascience.com/deep-learning-model-visualization-tools-which-is-best-83ecbe14fa7)**  
   A comparison of different tools used to visualize deep learning models, helping practitioners choose the best tool for their needs.

2. **[Image Quality Assessment of Deepfakes Produced by Different Generative Adversarial Networks](https://towardsdatascience.com/image-quality-assessment-of-deepfakes-produced-by-different-generative-adversarial-networks-b20513539cc6)**  
   An analysis of the quality of deepfake images generated by various GAN models, focusing on their strengths and weaknesses.

3. **[Convolutional Neural Networks: From An Everyday Understanding to a More Technical Deep Dive](https://towardsdatascience.com/convolutional-neural-networks-from-an-everyday-understanding-to-a-more-technical-deep-dive-83af329e5d89)**  
   A detailed explanation of convolutional neural networks, bridging the gap between a basic understanding and more technical insights.



## **Setup and Requirements for Google Colab**

This repository is designed to be run in Google Colab, with specific steps required to set up the environment correctly. Follow these instructions to get started:

### 1. **Open the Notebook in Google Colab**:
   - Navigate to the repository on GitHub and open the `.ipynb` notebook file you want to run.
   - Click on the "Open in Colab" button, or manually open the notebook in Google Colab by replacing the `github.com` URL with `colab.research.google.com/github/`.

### 2. **Clone the Darknet Repository (For YOLO Setup)**:\
   - Ensure that your notebook is in "GPU" under _Hardware Accelerator_. *_Note: This may require a colab pro account_
   - If you're running `Blended_GAN_Object_Detect_Research.ipynb`, you'll need to clone and build Darknet:
   
     ```python
     !git clone https://github.com/AlexeyAB/darknet
     %cd darknet
     !sed -i 's/OPENCV=0/OPENCV=1/' Makefile
     !sed -i 's/GPU=0/GPU=1/' Makefile
     !sed -i 's/CUDNN=0/CUDNN=1/' Makefile
     !sed -i 's/CUDNN_HALF=0/CUDNN_HALF=1/' Makefile
     !make
     ```

### 3. **Install Required Python Packages**:
   - Some dependencies might need to be installed. Use the following command to install required packages:
   
     ```python
     !pip install -r requirements.txt
     ```

   - For TensorFlow 2.x (especially if running in Colab):
   
     ```python
     try:
         # %tensorflow_version only exists in Colab.
         %tensorflow_version 2.x
     except Exception:
         pass
     ```

### 4. **Ensure GPU Availability**:
   - Verify that a GPU is available for running deep learning models. If not, switch to a GPU runtime in Colab:
   
     ```python
     if not tf.config.list_physical_devices('GPU'):
         print("No GPU was detected. LSTMs and CNNs can be very slow without a GPU.")
         print("Go to Runtime > Change runtime and select a GPU hardware accelerator.")
     ```

### 5. **Run the Code**:
   - Once the environment is set up, run the cells in the notebook sequentially to execute the code and generate results.
   - For custom datasets, us Labelimg for labeling data: https://github.com/HumanSignal/labelImg. Recommend loading at dataset as two zipped files (train and test) of images with annotations
   - Store custom dataset in a folder in google drive (recommend naming file_yolov4_)
   - use _generate_train.py_ and _generate_test.py_ in supporting documents to generate train.txt and test.txt yolov4 configuration files
   - Train detector model. _Note - weights are saved every 1000 iterations in case notebook crashes_
   - Evaluate Mean Average Precision (mAP) and Intersection-over-Union (IoU)


## **Future Work**

This repository serves as a foundation for further exploration in GANs and their application in augmenting training data for classification models. Potential areas for future research include evaluating the long-term impacts of synthetic data on model generalization and exploring other GAN architectures for data augmentation.

## **Acknowledgments**

We thank the community and contributors who have provided valuable feedback during the development of this research. This work is supported by the Air Force Institute of Technology.
