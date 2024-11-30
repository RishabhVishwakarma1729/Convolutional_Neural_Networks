# **MNIST Handwritten Digit Classification**

This project focuses on building and evaluating a **Convolutional Neural Network (CNN)** to classify handwritten digits (0-9) using the popular **MNIST dataset**. The project includes **Exploratory Data Analysis (EDA)**, preprocessing, model training, evaluation, and visualization of predictions.
---

## **🚀 Features**

- **Exploratory Data Analysis (EDA):**
  - Visualize sample images, label distribution, and patterns in the dataset.
  - Identify challenges in digit classification.

- **Data Preprocessing:**
  - Normalize pixel values to the range [0, 1].
  - Reshape images to `(28, 28, 1)` for CNN input.
  - One-hot encode the labels for multi-class classification.

- **Model Development:**
  - Design and train a CNN with convolutional, pooling, and dropout layers.
  - Use `ReLU` activation for non-linearity and `softmax` for multi-class output.

- **Evaluation Metrics:**
  - Compute accuracy, precision, recall, and F1-score.
  - Visualize confusion matrix and misclassified examples.

- **Visualization:**
  - Display sample predictions using both Matplotlib and OpenCV.
  - Highlight correct and incorrect predictions with labels.

---

## **📊 Dataset Overview**

The MNIST dataset contains grayscale images of handwritten digits ranging from 0 to 9.

| **Attribute**    | **Details**                  |
|-------------------|------------------------------|
| **Image Size**    | 28x28 pixels (grayscale)    |
| **Pixel Range**   | 0 (black) to 255 (white)    |
| **Channels**      | Single-channel (grayscale)  |
| **Training Set**  | 60,000 images               |
| **Test Set**      | 10,000 images               |
| **Classes**       | 10 (Digits: 0-9)           |

---

## **🧠 Model Architecture**

| **Layer Type**       | **Details**              |
|-----------------------|--------------------------|
| Input Layer           | Input shape: (28, 28, 1) |
| Convolutional Layer   | 32 filters, 3x3 kernel   |
| Max Pooling Layer     | 2x2 pool size           |
| Convolutional Layer   | 64 filters, 3x3 kernel   |
| Max Pooling Layer     | 2x2 pool size           |
| Dropout Layer         | Dropout rate: 0.5       |
| Fully Connected Layer | 128 neurons             |
| Output Layer          | 10 neurons (softmax)    |

---

## **📈 Performance**

- **Training Accuracy**: ~98.5%
- **Validation Accuracy**: ~98%
- **Test Accuracy**: ~98%

---

## **📖 Insights**

1. **High Accuracy**:  
   The CNN achieves excellent accuracy on both training and test data.

2. **Misclassifications**:  
   Some digits, such as `5` and `6`, are occasionally misclassified due to handwriting ambiguities.

3. **Potential Improvements**:  
   - Data augmentation to make the model robust to variations.
   - Experimenting with deeper architectures like ResNet.

---

## **📚 Lessons Learned**

- **Normalization**: Scaling input pixel values improves model convergence and accuracy.
- **Regularization**: Dropout layers prevent overfitting, especially on small datasets.
- **EDA Importance**: Visualizing the dataset helps identify challenges and potential preprocessing needs.

---

## **⚙️ Installation and Usage**

### **Clone the Repository**
```bash
git clone https://github.com/your-username/mnist-classification.git
cd mnist-classification

