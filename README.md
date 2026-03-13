# Assignment: Clinical MRI Classification using CNNs

**Course:** Deep Learning in Medicine (SBES361)

## Objective
Transition from the 28x28 BloodMNIST images to higher-resolution MRI brain scans. You will build, train, and clinically evaluate a custom Convolutional Neural Network (CNN) to classify brain tumours.

## The Dataset
You must use a brain MRI dataset containing four classes:
1. `glioma`
2. `meningioma`
3. `notumor`
4. `pituitary`

*(Note: You are responsible for loading and splitting the raw image directories).*

## Tasks & Requirements

### 1. Architecture Design
Design a custom CNN suitable for higher-resolution images. You cannot simply reuse the BloodMNIST architecture, as the spatial dimensions and feature complexities are fundamentally different.

### 2. Clinical Metrics
Evaluate your model's success using class-wise **Recall**. Generating a False Negative for the "notumor" class is a critical clinical failure (sending a patient with a tumour home). 
* **Deliverable:** You must generate and display a 4x4 Confusion Matrix with axes explicitly labelled with the four class names.

### 3. Regularisation
Because MRI images are high-resolution and datasets are often small, the risk of overfitting is severe. 
* **Deliverable:** You must implement **at least one** of the following: 
  * `Dropout`
  * L2 weight regularisation (`kernel_regularizer=tf.keras.regularizers.l2(...)`)
  * `EarlyStopping`

### 4. Capacity Justification
* **Deliverable:** Print the total trainable parameter count of your model using `model.summary()`. 
* Below the output, write a one-sentence markdown justification of whether this count is appropriate relative to your training set size. *(Note: While classical machine learning requires datasets to be an order of magnitude larger than parameters, defend your parameter count based on the regularisation techniques you applied).*

---

## Submission Protocol

To complete this assignment, commit and push the following to this repository:
1. Your completed `assignment.ipynb` notebook with **all cells executed and outputs visible**.
2. Update this `README.md` file by replacing this text with your **Medical Report**, which must include:
    * A textual description or diagram of your model architecture.
    * The per-class Recall values from your classification report.
    * **Error Analysis:** Identify which class pair is most confused by your model and provide a brief biological/clinical interpretation of why the network struggles with them.
