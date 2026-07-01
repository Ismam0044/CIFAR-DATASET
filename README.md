# CIFAR-10 Image Classifier

# About the Project

This project trains a convolutional neural network to sort images from the CIFAR-10 dataset into ten classes. The classes are airplane, automobile, bird, cat, deer, dog, frog, horse, ship, and truck. The trained model reaches about 82 percent accuracy on the test set. The project also includes a small app where you can upload your own image and get a prediction. Everything is kept in one notebook file called cifar.ipynb.

# Dataset

CIFAR-10 has 60,000 colour images, and each one is 32 by 32 pixels. There are 50,000 images for training and 10,000 for testing. The dataset loads on its own through TensorFlow, so you do not need to download it by hand.

# Setup

To set up the project, you need Python 3.10 or newer. First clone the repository with git clone https://github.com/Ismam0044/CIFAR-DATASET.git and move into the folder. Then install the packages the project needs by running pip install tensorflow numpy matplotlib scikit-learn seaborn ipywidgets pillow. That is all the setup you need. The dataset downloads by itself the first time you run the notebook.

# Training

To train the model, open cifar.ipynb in Jupyter Notebook or VS Code and run the cells one by one from the top. The cells load the data, normalize it, add augmentation, build the model, and then train it. The training runs for up to 40 epochs. It stops early if the accuracy stops going up, and it lowers the learning rate when progress slows down. Training is faster on a GPU, so a machine with a GPU is better if you have one, but it also works on a normal CPU.

# Model

The model is a CNN built from scratch. It has three blocks of convolution layers that go from 32 to 64 to 128 filters, and each block uses batch normalization and max pooling. After the blocks, the model flattens the data, passes it through a dense layer, uses dropout to cut down on overfitting, and ends with a softmax layer that gives a score for each of the ten classes. The model has about 358,000 parameters. Before training, the images are scaled so the pixel values sit between 0 and 1. Data augmentation is also used, which flips, rotates, and zooms the images by small amounts so the model sees more variety and learns to handle new images better.

# Performance Results

The model reaches about 82 percent accuracy on the test set, and the precision, recall, and f1-score are all around 0.82 across the ten classes. The notebook also shows a confusion matrix that shows which classes the model mixes up, along with accuracy and loss curves for both training and validation. The training and validation lines stay close together, which shows the model is not overfitting.

# Prediction App

The notebook has an upload button near the end. When you run that cell, an upload button shows up. You click it, pick an image from your computer, and the model predicts the class and shows how sure it is. The model was trained on small 32 by 32 images, so it works best on simple, clear pictures of one object.

# Files

The repository holds cifar.ipynb, which is the full project with the data, model, training, results, and the prediction app. It also holds the training and validation graph and a gitignore file that keeps large and temporary files out of the repository. The trained model file and the virtual environment are not stored in the repository, because the model is created again when you run the training cells.
