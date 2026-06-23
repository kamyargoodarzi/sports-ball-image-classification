# Sports Ball Image Classification Prototype

A computer vision prototype for classifying sports ball images into their correct product categories.  
The project was prepared for an AI bootcamp assignment based on the Vectura online sports equipment store scenario.

## Project objective

Vectura receives many sports product images every day. Manual categorization is slow and error-prone, especially when images have different lighting conditions, backgrounds, camera angles, or low quality.

This project tests whether an image classification model can automatically identify the type of sports ball from an image and recommend the correct product category.

## Assignment requirements covered

- Image preprocessing
- Model training and evaluation on the original dataset
- Error analysis and visualization of incorrect predictions
- Construction of a new external test set collected outside the original dataset
- Evaluation of the trained model on the external test set without retraining
- Managerial report
- Technical teammate report

## Repository structure

```text
.
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
├── notebooks/
│   └── Moghaddasin_Noori_Goodarzi_Final.ipynb
├── reports/
│   ├── Manager_Report.pdf
│   └── Teammate_Technical_Report.pdf
├── outputs/
│   ├── figures/
│   │   ├── confusion_matrices/
│   │   ├── training_curves/
│   │   └── sample_predictions/
│   └── metrics/
├── data/
│   └── README.md
└── models/
    └── README.md
```

## Dataset

The original dataset is not included in this repository because datasets can be large and may have licensing restrictions.

Expected local structure:

```text
data/
├── original/
│   ├── train/
│   │   ├── class_1/
│   │   ├── class_2/
│   │   └── ...
│   └── test/
│       ├── class_1/
│       ├── class_2/
│       └── ...
└── external_test/
    ├── class_1/
    ├── class_2/
    └── ...
```

The external test set was collected separately from the internet and was not used during training.  
It was used only to evaluate model generalization.



## Output files

The `outputs/` folder contains the final figures and numerical results extracted from the completed notebook.

```text
outputs/
├── figures/
│   ├── dataset_overview/
│   ├── training_curves/
│   ├── confusion_matrices/
│   │   ├── original_test/
│   │   └── external_test/
│   ├── sample_predictions/
│   │   └── original_test/
│   ├── external_test_predictions/
│   ├── error_analysis/
│   │   ├── original_test/
│   │   └── external_test/
│   └── model_comparison/
└── metrics/
    ├── classification_reports/
    │   ├── original_test/
    │   └── external_test/
    ├── training_logs/
    ├── final_metrics.csv
    └── notebook_output_manifest.csv
```

The figures include dataset overview plots, training curves, confusion matrices, sample predictions, external test-set predictions, misclassified examples, and final model-comparison results. The `final_metrics.csv` file summarizes the original-test and external unseen-test accuracies for the evaluated models.


## Method summary

The project uses transfer learning for sports ball image classification. The workflow includes:

1. Loading images from class-based folders
2. Resizing and normalizing images
3. Applying data augmentation during training
4. Training multiple CNN-based models
5. Evaluating models using accuracy, confusion matrix, and class-level metrics
6. Testing the best trained model on a new external test set
7. Analyzing misclassified images

## Models tested

Update this table with the exact final numbers from your notebook before publishing.

| Model | Fine-tuning | Original test accuracy | External test accuracy | Notes |
|---|---:|---:|---:|---|
| MobileNetV2 | No | TODO | TODO | Lightweight baseline |
| EfficientNetB2 | No | TODO | TODO | Good accuracy/efficiency balance |
| ResNet50 | No | TODO | TODO | Strong transfer learning baseline |
| ResNet50 | Yes | TODO | TODO | Best-performing model in the final experiments |

## Main findings

Update this section after checking the final notebook outputs.

- The best model was: `TODO`
- The strongest classes were: `TODO`
- The most difficult classes were: `TODO`
- Main error sources:
  - Similar ball shapes across classes
  - Poor lighting or low image quality
  - Unusual camera angles
  - Complex backgrounds
  - External images differing from the training distribution

## How to run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
```

### 2. Create an environment

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook notebooks/Moghaddasin_Noori_Goodarzi_Final.ipynb
```

## Important reproducibility notes

- Dataset folders are ignored by Git.
- Trained model weights are ignored by Git.
- Large files should be stored externally, for example on Google Drive, Kaggle, or GitHub Releases.
- The final notebook should contain the full workflow: preprocessing, training, evaluation on the original dataset, and evaluation on the external test set.

## Limitations

This is a prototype, not a production-ready system. Its reliability depends heavily on dataset quality, class balance, image diversity, and correct labeling. Before business deployment, the model should be tested on a larger real-world dataset and monitored after deployment.

## Authors

This project was completed as a group computer vision project by under Daneshkar Academy supervison:


* Mohammadmahdi Moghaddasin
* Amirreza Noori
* Kamyar Goodarzi

The project includes model training, evaluation on the original dataset, evaluation on a separately collected external test set, output visualization, and technical/reporting deliverables.

