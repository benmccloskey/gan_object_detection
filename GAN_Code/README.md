# Generative Adversarial Network Notebooks

This repository contains various notebooks that demonstrate the implementation and training of different types of Generative Adversarial Networks (GANs). Each notebook focuses on a specific GAN architecture and provides step-by-step instructions for running and understanding the models.

## Available Notebooks

### 1. [DCGAN and CGAN Image Generation](./DCGAN_CGAN_Image_Generation.ipynb)
   - **Description**: This notebook explores the implementation of Deep Convolutional Generative Adversarial Networks (DCGAN) and Conditional GANs (CGAN) for generating images. The notebook covers the entire pipeline from data preprocessing to model training and visualization of generated images.

### 2. [Wasserstein GAN (Unconditioned/Conditioned)](./WGAN_CWGAN_Image_Generation.ipynb)
   - **Description**: This notebook focuses on the Wasserstein GAN (WGAN) and Conditional Wasserstein GAN (CWGAN) models. It delves into the theory behind the Wasserstein distance and how it can be used to stabilize GAN training, as well as how conditioning can be applied to control the generation process.

## How to Use

1. **Cloning the Repository**: 
   - Start by cloning the repository to your local machine:
     ```bash
     git clone https://github.com/your-username/gan-project.git
     cd gan-project
     ```

2. **Running the Notebooks**: 
   - These notebooks are designed to run in a Jupyter environment. You can open them locally using JupyterLab or Jupyter Notebook, or directly in Google Colab by navigating to the desired notebook and clicking "Open in Colab."
   
3. **Setup Requirements**:
   - Ensure that you have the necessary dependencies installed. If using a local environment, install the required packages:
     ```bash
     pip install -r requirements.txt
     ```

4. **Exploring the Notebooks**: 
   - Each notebook is self-contained, with code cells that can be run sequentially. Start by running the setup and import cells, then proceed with data loading, model training, and evaluation steps.
