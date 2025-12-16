# Skin Cancer Detection Using Deep Learning

## Project Overview

This project focuses on the development of a deep learning–based system for early skin cancer detection using dermoscopic images. The main objective is to compare the performance of several convolutional neural network (CNN) architectures in classifying skin lesion images accurately and efficiently.

This project is part of an academic research initiative in the field of machine learning and medical image analysis.

---

## Dataset

* **Dataset:** HAM10000 (Human Against Machine with 10,000 training images)
* **Source:** Kaggle
* **Description:** A large collection of multi-source dermatoscopic images categorized into several skin lesion classes.

---

## Models Implemented

The following deep learning models were evaluated and compared:

* **VGG16**
* **ResNet50**
* **MobileNetV2**

Transfer learning was applied to leverage pre-trained weights and improve classification performance.

---

## Methodology

The workflow of this project includes:

1. Data preprocessing and normalization
2. Data augmentation to address class imbalance
3. Model training using transfer learning
4. Model evaluation using accuracy and validation metrics
5. Comparative analysis of model performance

---

## Results

* All models achieved **classification accuracy above 85%**
* Performance comparison highlights trade-offs between accuracy, model complexity, and computational efficiency
* MobileNetV2 showed potential for lightweight deployment scenarios

---

## Tools & Technologies

* **Programming Language:** Python
* **Framework:** TensorFlow, Keras
* **Libraries:** NumPy, Pandas, Matplotlib
* **Model Type:** Convolutional Neural Network (CNN)

---

## How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/Aurelviolita/Skin_cancer_project.git
   ```
2. Install required dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Run the training or evaluation notebook/script as provided.

> Note: Due to hardware limitations, experiments were conducted using optimized batch sizes.

---

## Future Improvements

* Integration of GAN-based data augmentation
* Hyperparameter optimization
* Deployment using a lightweight web application (Streamlit)

---

## Author

**Aurel Elviolita Putri**
Undergraduate Computer Science Student

* LinkedIn: [https://linkedin.com/in/aurel-elviolita-putri](https://linkedin.com/in/aurel-elviolita-putri)
* GitHub: [https://github.com/Aurelviolita](https://github.com/Aurelviolita)

---

## Why This Project Matters

This project demonstrates practical experience in:

* Deep learning implementation
* Medical image classification
* Research-oriented problem solving
* Comparative model evaluation

