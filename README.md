# Skin Lesion Classification using EfficientNetB3 and DWT

An AI-based skin lesion image classification project that uses **EfficientNetB3 and Discrete Wavelet Transform (DWT)** to classify dermoscopic images as **benign or malignant**.

The project explores wavelet-based image preprocessing combined with transfer learning for binary skin lesion classification.

## Kaggle Notebook

This project was developed and executed using Kaggle Notebooks.

**View the complete implementation:** [Open Kaggle Notebook](https://www.kaggle.com/code/miniproject36/final-execution)

## Project Overview

Skin lesions have different visual characteristics, making their classification a challenging computer vision task.

This project implements a deep learning pipeline consisting of:

* **Image preprocessing:** Images are resized and Gaussian filtering is applied during data generation.
* **Discrete Wavelet Transform (DWT):** Haar wavelet transformation is applied to grayscale images, and the LL approximation coefficients are used.
* **EfficientNetB3:** An ImageNet-pretrained convolutional neural network processes the transformed images.
* **Binary classification:** A sigmoid output layer predicts whether an image belongs to the benign or malignant class.

The model is trained and evaluated using the HAM10000 dataset.

## Objectives

* Develop a deep learning model for binary skin lesion image classification.
* Explore DWT as an image preprocessing technique.
* Apply transfer learning using EfficientNetB3.
* Use image augmentation during training.
* Evaluate model performance using classification metrics.

## Model Architecture

The notebook implements the following pipeline:

1. **Input Image:** A dermoscopic skin lesion image is loaded from the HAM10000 dataset.
2. **Image Preprocessing:** The image is resized to 224 × 224 pixels. Gaussian blur is applied during data generation.
3. **Grayscale Conversion:** The RGB image is converted to grayscale.
4. **DWT Transformation:** Haar DWT is applied, and the LL approximation coefficients are selected. The transformed image is resized and converted into a three-channel input.
5. **EfficientNetB3:** The transformed image is passed to an ImageNet-pretrained EfficientNetB3 model.
6. **Classification Layer:** Global average pooling and a sigmoid dense layer produce a binary prediction.
7. **Fine-Tuning:** The model is fine-tuned by unfreezing the last 30 layers of the EfficientNetB3 base model.

The model uses the Adam optimizer and binary cross-entropy loss.

**Note:** DWT is applied to the input image before EfficientNetB3. The notebook does not use separate DWT and EfficientNet feature branches or a feature-fusion layer.

## Dataset

**HAM10000 – Human Against Machine with 10000 Training Images**

The HAM10000 dataset contains dermatoscopic images of pigmented skin lesions and is commonly used in skin lesion classification research.

Dataset source: [Skin Cancer MNIST: HAM10000 – Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)

The dataset contains 10,015 dermatoscopic images across seven diagnostic categories:

| Label | Lesion Category                                 |
| ----- | ----------------------------------------------- |
| akiec | Actinic keratoses and intraepithelial carcinoma |
| bcc   | Basal cell carcinoma                            |
| bkl   | Benign keratosis-like lesions                   |
| df    | Dermatofibroma                                  |
| mel   | Melanoma                                        |
| nv    | Melanocytic nevi                                |
| vasc  | Vascular lesions                                |

### Binary Label Mapping

The notebook groups the original seven categories into two classes:

| Binary Class | Original Labels   |
| ------------ | ----------------- |
| Benign       | nv, bkl, df, vasc |
| Malignant    | mel, bcc, akiec   |

The data is divided into training, validation, and test sets using stratified sampling:

* Training set: 72%
* Validation set: 18%
* Test set: 10%

## Technologies Used

* Python
* TensorFlow / Keras
* EfficientNetB3
* Discrete Wavelet Transform (DWT)
* PyWavelets
* OpenCV
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* Kaggle Notebooks / Jupyter Notebook

## Training Configuration

* **Input size:** 224 × 224 pixels
* **Batch size:** 32
* **Initial training:** 15 epochs
* **Fine-tuning:** 10 epochs
* **Initial learning rate:** 0.0001
* **Fine-tuning learning rate:** 0.00001
* **Optimizer:** Adam
* **Loss function:** Binary cross-entropy
* **Output activation:** Sigmoid

## Results

The model was evaluated on the HAM10000 dataset for binary classification.

### Validation Performance

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 89.02% |
| Precision | 74.84% |
| Recall    | 65.91% |
| F1-score  | 70.09% |

### Test Performance

| Metric        | Score  |
| ------------- | ------ |
| Test Accuracy | 87.72% |
| Test Loss     | 0.469  |

The validation metrics and confusion matrix are calculated using the validation set. Test accuracy and test loss are reported separately using the held-out test set.

These results represent an experimental model. Performance should be interpreted in the context of the dataset, preprocessing, and evaluation methodology and does not establish clinical reliability.

## How to Run the Project

This project was developed and executed using Kaggle Notebooks.

### Run on Kaggle

1. Open the [Kaggle Notebook](https://www.kaggle.com/code/miniproject36/final-execution).
2. Sign in to Kaggle.
3. If needed, make a copy of the notebook.
4. Add the HAM10000 dataset using Kaggle's **Add Input** option.
5. Confirm that the dataset paths in the notebook match the attached dataset.
6. Enable GPU acceleration in the notebook settings if available.
7. Run the notebook cells sequentially.

### Run Locally

The notebook can also be executed locally using Jupyter Notebook or JupyterLab.

1. Clone the repository:

   ```bash
   git clone https://github.com/chHarshi/skin-lesion-classification.git
   cd skin-lesion-classification
   ```

2. Install the required libraries:

   ```bash
   pip install numpy pandas matplotlib opencv-python PyWavelets scikit-learn tensorflow jupyter
   ```

3. Download the HAM10000 dataset and update the dataset paths in the notebook.

4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open the notebook and run the cells sequentially.

**Note:** The notebook was originally developed in Kaggle. Dataset paths, package versions, and hardware settings may need to be adjusted when running it locally.

## Applications

* Research in automated skin lesion image classification
* Medical image analysis experimentation
* Computer vision and deep learning research
* Exploring wavelet-based image preprocessing with transfer learning

## Limitations and Disclaimer

This project is intended for educational and research purposes only.

It is not a medical diagnostic system and must not be used to diagnose skin conditions or make treatment decisions. Predictions from the model require appropriate clinical validation before any real-world medical use.

Model performance may vary depending on image quality, dataset distribution, preprocessing, and evaluation methodology.

## Author

**Harshitha**

Computer Science and Engineering – Artificial Intelligence and Machine Learning

GitHub: [chHarshi](https://github.com/chHarshi)

## License

A license has not yet been specified. Add an appropriate open-source license if you intend to permit others to reuse or distribute this project.
