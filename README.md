# face-mask-detection-cnn
A CNN-based deep learning project for classifying faces as with mask, without mask, or mask worn incorrectly.
# Face Mask Detection Using CNN

A deep learning project that uses a Convolutional Neural Network (CNN) to classify faces into three categories:

* With Mask
* Without Mask
* Mask Worn Incorrectly

## Project Overview

This project uses a CNN to learn visual features from face images and classify them into one of three mask-related categories.

The images are first processed using the annotations provided with the dataset. Face regions are cropped from the original images, resized to 64 × 64 pixels, and normalized before being given to the CNN.

## Dataset

The project uses the **Face Mask Detection** dataset from Kaggle by Andrew MVD.

The dataset contains images with XML annotations that identify the location and category of faces.

Dataset: `andrewmvd/face-mask-detection`

The dataset is downloaded automatically using `kagglehub`, so the dataset itself is not included in this repository.

## Classes

The model classifies faces into three classes:

| Class                 | Label |
| --------------------- | ----: |
| With Mask             |     0 |
| Without Mask          |     1 |
| Mask Worn Incorrectly |     2 |

## Project Workflow

```text
Kaggle Dataset
      ↓
Read Images and XML Annotations
      ↓
Find Face Bounding Boxes
      ↓
Crop Face Regions
      ↓
Resize to 64 × 64
      ↓
Normalize Pixel Values
      ↓
Train / Validation / Test Split
      ↓
CNN Model
      ↓
Train the Model
      ↓
Evaluate on Test Data
      ↓
Predict Mask Category
```

## Data Preprocessing

The following preprocessing steps are performed:

1. Images are loaded using OpenCV.
2. XML annotation files are used to find face bounding boxes.
3. Face regions are cropped from the images.
4. Cropped faces are resized to 64 × 64 pixels.
5. Pixel values are normalized from 0–255 to 0–1.
6. The dataset is divided into training, validation, and testing sets.
7. Labels are converted into one-hot encoded format for classification.

## CNN Architecture

The model consists of three convolutional blocks followed by fully connected layers.

```text
Input Image (64 × 64 × 3)
        ↓
Conv2D (32 filters)
        ↓
MaxPooling
        ↓
Conv2D (64 filters)
        ↓
MaxPooling
        ↓
Conv2D (128 filters)
        ↓
MaxPooling
        ↓
Flatten
        ↓
Dense (128 neurons)
        ↓
Dropout (0.5)
        ↓
Dense (3 neurons)
        ↓
Softmax
```

### Model Details

* **Input size:** 64 × 64 × 3
* **Convolutional layers:** 3
* **Filters:** 32, 64, 128
* **Activation:** ReLU
* **Pooling:** MaxPooling
* **Dense layer:** 128 neurons
* **Dropout:** 0.5
* **Output classes:** 3
* **Optimizer:** Adam
* **Loss function:** Categorical Crossentropy
* **Epochs:** 20
* **Batch size:** 32

## Training

The model is trained using the training dataset while the validation dataset is used to monitor the model's performance during training.

The final performance is evaluated using the separate test dataset.

## Results

After running the notebook, the final test accuracy is displayed in the output:

```text
Test Accuracy: XX.XX%
```

Replace `XX.XX%` with the actual accuracy produced by your notebook.

## Technologies Used

* Python
* OpenCV
* NumPy
* TensorFlow / Keras
* Scikit-learn
* KaggleHub
* XML / ElementTree
* Google Colab

## How to Run

### 1. Open the notebook

Open `face_mask_detection.ipynb` in Google Colab or Jupyter Notebook.

### 2. Install required libraries if needed

```bash
pip install kagglehub opencv-python tensorflow scikit-learn
```

### 3. Run the notebook

The notebook automatically downloads the dataset using KaggleHub, preprocesses the images, trains the CNN, and evaluates the model.

## Project Purpose

This project was created as a learning project to understand:

* Image preprocessing
* CNN architecture
* Image classification
* Training and validation
* Model evaluation
* Deep learning with TensorFlow/Keras

## Future Improvements

Possible improvements include:

* Data augmentation
* Confusion matrix and classification report
* Training accuracy and loss visualizations
* Testing the model on new images
* Real-time webcam mask classification
* Using transfer learning with a pretrained CNN

## Author

**Jameel Arham**

**Artificial Intelligence student**
