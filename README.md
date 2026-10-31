# Glacier Debris Segmentation Using Prithvi EO 2.0 and UPerNet

## 📌 Project Overview

This project explores semantic segmentation of debris-covered glaciers using multispectral satellite imagery and a pretrained geospatial foundation model.

The approach combines the **Prithvi EO 2.0 (600M) encoder** with a **UPerNet-style decoder** to generate pixel-level segmentation predictions.

The goal is to investigate how geospatial foundation models can support the analysis of glacier regions in Earth observation imagery.

## 🎯 Objectives

- Explore multispectral satellite imagery for glacier segmentation.
- Use a pretrained geospatial foundation model for feature extraction.
- Generate pixel-level segmentation masks.
- Evaluate segmentation performance using standard metrics.
- Visualize and analyze model predictions.

## 🧠 Model Architecture

- **Encoder:** Prithvi EO 2.0 (600M)
- **Decoder:** UPerNet-style decoder
- **Task:** Binary semantic segmentation
- **Input size:** 448 × 448 pixels
- **Input data:** Multispectral satellite imagery

The pretrained encoder extracts geospatial features, while the decoder uses these features to produce segmentation predictions.

## 📂 Dataset

The dataset is organized into training, validation, and testing splits, with corresponding satellite images and segmentation masks.

| Dataset Split | Image-Mask Pairs |
|---|---:|
| Training | 1,496 |
| Validation | 186 |
| Testing | 194 |
| **Total** | **1,876** |

These counts are based on the notebook's dataset inspection outputs.

The dataset files are not included in this repository. Access the dataset here:

[Download Glacier Debris Segmentation Dataset](https://drive.google.com/file/d/1Q5OT3QVmBi7u7Pm5XQFKL6v5ujUNWdws/view?usp=sharing)

## ⚙️ Methodology

The notebook covers the following workflow:

1. Dataset preparation and inspection.
2. Loading the pretrained Prithvi EO 2.0 encoder.
3. Integrating the encoder with a UPerNet-style decoder.
4. Preparing satellite imagery and segmentation masks.
5. Training and validating the segmentation model.
6. Evaluating predictions on the test dataset.

## 🏋️ Training Details

Training was continued from a previously saved checkpoint.

- **Configured epochs:** 30
- **Last completed epoch:** 28
- **Training approach:** Resumed training using a previously saved checkpoint.

### Model Checkpoints

- [Previous Training Checkpoint](https://drive.google.com/file/d/1CTMlVl6DgmW1LQzZ_EemDfsu1vvBVD8I/view?usp=sharing)
- [Latest Checkpoint (After Epoch 28)](https://drive.google.com/file/d/12_KmrrUmz1ni003jRFfdBAW06-TjONaP/view?usp=sharing)

## 📊 Evaluation Results

The following metrics were obtained from the model evaluation:

| Metric | Result |
|---|---:|
| Background IoU | 0.894608 |
| Debris IoU | 0.587007 |
| Mean IoU (mIoU) | 0.740808 |
| Precision | 0.805986 |
| Recall | 0.683602 |
| F1-score | 0.739766 |

### Confusion Matrix Values

| Metric | Pixel Count |
|---|---:|
| True Positives (TP) | 5,072,752 |
| True Negatives (TN) | 30,294,855 |
| False Positives (FP) | 1,221,095 |
| False Negatives (FN) | 2,347,874 |

### Evaluation Metrics Explained

- **Intersection over Union (IoU):** Measures overlap between predicted and ground-truth regions.
- **Mean IoU (mIoU):** Summarizes IoU across segmentation classes.
- **Precision:** Measures the proportion of predicted positive pixels that are correct.
- **Recall:** Measures the proportion of ground-truth positive pixels detected.
- **F1-score:** Combines precision and recall.

## 🛠️ Tools and Technologies

- Python
- PyTorch
- Jupyter Notebook / Google Colab
- Prithvi EO 2.0
- UPerNet-style decoder
- Rasterio
- NumPy
- Matplotlib

## 📁 Repository Structure

```text
glacier-debris-segmentation/
│
├── prithvi(test_train).ipynb
└── README.md
```

The repository currently contains the training/testing notebook and this documentation.

## 🚀 How to Run

1. Clone or download this repository.
2. Open the notebook in Google Colab or a compatible Jupyter environment.
3. Configure the dataset paths for your environment.
4. Install the required Python dependencies.
5. Configure access to the pretrained model and any required checkpoints.
6. Execute the notebook cells in the appropriate order.

**Note:** Reproducing the experiments requires access to the dataset, pretrained model weights, and any checkpoints referenced by the notebook.

### Google Colab Notebook

[Open the Training and Testing Notebook](https://colab.research.google.com/drive/1IKYfpIg3R5YoZUectrzNoR60LeSFom6A?usp=sharing)

## 🌍 Potential Applications

Semantic segmentation of glacier regions can support Earth observation research and the study of glacier surface characteristics. This project explores the use of pretrained geospatial models for this type of image-analysis task.

## 🙌 Acknowledgements

This project uses the Prithvi EO 2.0 geospatial foundation model developed through collaboration between IBM and NASA.

## 📝 Project Note

This is a collaborative project. The repository documents the model approach and notebook-based workflow. Additional documentation, visualizations, and reproducibility instructions can be added as the project is further developed.
