# CNN Model for Multi-Class Image Classification

This project demonstrates a Convolutional Neural Network (CNN) built with TensorFlow/Keras for classifying images into multiple classes. The model includes regularization, data augmentation, and callbacks for efficient training.

## Table of Contents
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Dataset Structure](#dataset-structure)
- [Model Architecture](#model-architecture)
- [Training Process](#training-process)
- [Evaluation](#evaluation)
- [Prediction](#prediction)
- [Acknowledgments](#acknowledgments)

---

## Installation

1. Clone the repository:
    bash
    git clone https://github.com/Adnan1902/CNN_Image_Classifier.git
    cd cnn-image-classification
    

2. Set up a virtual environment (optional but recommended):
    bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    

3. Install the dependencies:
    bash
    pip install -r requirements.txt
    

---

## Dependencies

Here are the dependencies required for this project:

- *Python* >= 3.8
- *TensorFlow* >= 2.10
- *NumPy* >= 1.19
- *Matplotlib* >= 3.3

The required dependencies are listed in the requirements.txt file:
txt
tensorflow>=2.10
numpy>=1.19
matplotlib>=3.3


---

## Dataset Structure

The dataset directory should be organized as follows:

D:/IMAGES_DATASET/
    Train/
        Class1/
        Class2/
        Class3/
    Test/
        Class1/
        Class2/
        Class3/

Replace Class1, Class2, etc., with the actual class names.

---

## Model Architecture

The CNN model consists of:
1. Four convolutional layers with ReLU activation and L2 regularization.
2. Batch normalization after each convolutional layer.
3. Max pooling for down-sampling.
4. Fully connected layers with dropout for regularization.
5. A final softmax layer for classification.

---

## Training Process

1. *Data Augmentation:*
    - Rotation, width/height shift, zoom, and horizontal flipping.

2. *Callbacks:*
    - ModelCheckpoint: Saves the best model.
    - EarlyStopping: Stops training when validation loss doesn't improve.
    - ReduceLROnPlateau: Reduces learning rate on plateau.

3. *Hyperparameters:*
    - Batch size: 32
    - Image dimensions: 128x128
    - Epochs: 20
    - Dropout rate: 0.5
    - L2 regularization: 0.01

---

## Evaluation

1. *Test Accuracy:*
    The model is evaluated on a separate test dataset.

2. *Metrics:*
    - Accuracy
    - Loss

Run the evaluation code:
python
model.evaluate(test_generator)


---

## Prediction

To predict the class of a new image:
1. Load the image:
    python
    new_image = tf.keras.preprocessing.image.load_img('path/to/new/image.jpg', target_size=(128, 128))
    new_image = tf.keras.preprocessing.image.img_to_array(new_image)
    new_image = new_image / 255.0  # Normalize the image
    new_image = tf.expand_dims(new_image, axis=0)  # Add batch dimension
    

2. Predict the class:
    python
    predicted_class = model.predict(new_image)
    print(predicted_class)
    

---

## Acknowledgments

- *TensorFlow/Keras* for the deep learning framework.
- *Matplotlib* for visualization.
- *NumPy* for numerical computations.
