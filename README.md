# Skin Lesion Classification using EfficientNet and DWT

An AI-based skin lesion classification project that combines **EfficientNet and Discrete Wavelet Transform (DWT)** to classify dermoscopic skin images.
The project explores how deep learning and image frequency analysis can be combined to support automated skin lesion image classification.

## Kaggle Notebook

This project was developed and executed using Kaggle Notebooks.
**View the complete implementation:** [Open Kaggle Notebook](https://www.kaggle.com/code/miniproject36/final-execution)

## Project Overview

Skin lesions can have different visual characteristics, making their classification a challenging computer vision task.
This project uses a hybrid deep learning approach that combines:
* **EfficientNet:** A convolutional neural network used for extracting meaningful visual features from skin lesion images.
* **Discrete Wavelet Transform (DWT):** An image processing technique used to capture frequency and texture information.
* **Deep Learning Classification:** The extracted features are used to classify dermoscopic images into different skin lesion categories.
The model is trained and evaluated using the HAM10000 dataset.

## Objectives

* Develop a deep learning model for skin lesion image classification.
* Explore the combination of EfficientNet and DWT.
* Analyze the effectiveness of combining spatial and frequency-based image features.
* Evaluate the model using classification performance metrics.

## Model Architecture

The proposed approach combines deep learning with wavelet-based image processing.

1. **Input Image:** A dermoscopic skin lesion image is provided to the pipeline.
2. **Image Preprocessing:** The image is prepared according to the model's input requirements.
3. **DWT Feature Extraction:** Wavelet transformation captures additional texture and frequency information.
4. **EfficientNet Feature Extraction:** EfficientNet extracts high-level visual features from the image.
5. **Feature Fusion and Classification:** The extracted features are combined and passed to the classification layers.
6. **Prediction:** The model predicts the skin lesion category.
> Note: The exact feature fusion and classification implementation should match the architecture used in the notebook.

## Dataset

**HAM10000 – Human Against Machine with 10000 Training Images**
The HAM10000 dataset contains dermatoscopic images of pigmented skin lesions and is commonly used for skin lesion classification research.
Dataset source: [Skin Cancer MNIST: HAM10000 – Kaggle](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)
The dataset includes seven diagnostic categories:

| Label | Lesion Category                                 |
| ----- | ----------------------------------------------- |
| akiec | Actinic keratoses and intraepithelial carcinoma |
| bcc   | Basal cell carcinoma                            |
| bkl   | Benign keratosis-like lesions                   |
| df    | Dermatofibroma                                  |
| mel   | Melanoma                                        |
| nv    | Melanocytic nevi                                |
| vasc  | Vascular lesions                                |
The dataset contains 10,015 dermatoscopic images.

## Technologies Used

* Python
* TensorFlow / Keras
* EfficientNet
* Discrete Wavelet Transform (DWT)
* NumPy
* Pandas
* OpenCV
* Matplotlib
* Scikit-learn
* Kaggle Notebooks / Jupyter Notebook

## Results

The hybrid EfficientNet + DWT model achieved approximately **89% classification accuracy** in the reported experiment.
The model performance should be interpreted in the context of the dataset split, preprocessing, and evaluation methodology used in the notebook.
Additional evaluation metrics may include:
* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix

## How to Run the Project

This project was developed and executed using Kaggle Notebooks.
### Run on Kaggle
1. Download or open the `.ipynb` notebook from this repository.
2. Sign in to [Kaggle](https://www.kaggle.com/).
3. Create a new Kaggle Notebook.
4. Upload the notebook file `final-execution (1).ipynb`.
5. Add the HAM10000 dataset to the notebook using Kaggle's Add Input option.
6. Update the dataset paths if required.
7. Enable GPU acceleration in the notebook settings if needed.
8. Run the notebook cells sequentially to reproduce the experiment.
### Run Locally
The notebook can also be executed locally using Jupyter Notebook or JupyterLab.
1. Clone the repository:
```bash
git clone https://github.com/chHarshi/skin-lesion-classification.git
cd skin-lesion-classification
```
2. Install the dependencies required by the notebook.
3. Download the HAM10000 dataset and configure the dataset paths.
4. Open the notebook:
```bash
jupyter notebook
```
5. Run the notebook cells sequentially.
**Note:** The notebook was originally developed in Kaggle. Dataset paths, package versions, and hardware settings may need to be adjusted when running it locally.

## Applications

* Research in automated skin lesion image classification
* Medical image analysis
* Computer vision and deep learning experimentation
* Exploring hybrid feature extraction techniques

## Limitations and Disclaimer

This project is intended for educational and research purposes only.
It is not a medical diagnostic system and must not be used to diagnose skin conditions or make treatment decisions. Predictions from the model require appropriate clinical validation before any real-world medical use.
Model performance may vary depending on image quality, dataset distribution, and the evaluation methodology.

## Author

**Harshitha**
Computer Science and Engineering – Artificial Intelligence and Machine Learning
GitHub: [chHarshi](https://github.com/chHarshi)

## License

A license has not yet been specified. Add an appropriate open-source license if you intend to permit others to reuse or distribute this project.
