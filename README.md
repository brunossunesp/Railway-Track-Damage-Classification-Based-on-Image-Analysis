# Railway-Track-Damage-Classification-Based-on-Image-Analysis

eu escrevi esse readme , acha que precisa melhorar?



# Railway-Track-Damage-Classification-Based-on-Image-Analysis

# CNN-Based Classification of Railway Track Defects

This repository contains a Convolutional Neural Network (CNN) implementation based on the ResNet50 architecture for classifying surface defects in railway tracks. The pipeline supports preprocessing, training, validation, evaluation, and exporting of results for four defect types: **Squats**, **Flakings**, **Spallings**, and **Shellings**.

## 📌 Description

Each defect type is handled using a binary one-vs-rest classification strategy. The dataset images undergo preprocessing (resizing, median filter, and Canny edge detection) before being passed into the CNN. The project performs:

- Training using a ResNet50 backbone
- 5-fold cross-validation
- Generation of accuracy, sensitivity, and specificity statistics
- Export of learning curves, ROC curves, and confusion matrices for each defect class

## 🧠 Model Architecture

- **Base model**: ResNet50 (ImageNet weights, frozen)
- **Input size**: 150x150 RGB images (converted from edge detection maps)
- **Layers**: Flatten → Dense (512, ReLU) → Dense (1, Sigmoid)
- **Loss**: Binary Crossentropy
- **Optimizer**: Adam

## 🧪 Dataset

The dataset used in this project is publicly available and consists of images labeled into four defect categories. Each image is converted to edge-detected format using the Canny filter.

📂 **Expected directory structure**:
DATASET_ARAIN_4/
├── Squats/
├── Flakings/
├── Spallings/
└── Shellings/


> 📎 *Note: Each folder must contain images for the corresponding defect.*

## 📁 Output

The script saves the following in the specified `SAVE_PATH`:

- `learning_specificity_<CLASS>.txt`
- `roc_curve_<CLASS>_Test.txt` and `roc_curve_<CLASS>_Validation.txt`
- `confusion_matrix_<CLASS>_Test.txt` and `confusion_matrix_<CLASS>_Validation.txt`

## 📊 Evaluation Metrics

- Accuracy (mean ± std)
- Sensitivity (mean ± std)
- Specificity (mean ± std)
- ROC AUC for test and validation sets
- Confusion matrix (absolute and percentage)

## ▶️ Running the Code

1. Clone the repository or upload the script to your environment.
2. Ensure the dataset is properly structured and paths are correctly configured.
3. Run the Python script in a Jupyter environment or using a Python interpreter.

## 🛠 Dependencies

- TensorFlow
- OpenCV
- NumPy
- scikit-learn

Install them using:

```bash
pip install tensorflow opencv-python numpy scikit-learn👨‍💻 Author
Bruno Soares dos Santos
PhD Candidate – São Paulo State University (UNESP)
📧 bruno.soares-santos@unesp.br




