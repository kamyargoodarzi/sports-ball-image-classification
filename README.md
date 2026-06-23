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


The following models were evaluated on both the original test set and the external test set.

| Model             | Fine-tuning | Original test accuracy | External test accuracy | Notes                                                                                       |
| ----------------- | ----------: | ---------------------: | ---------------------: | ------------------------------------------------------------------------------------------- |
| ResNet18 baseline |          No |                 85.00% |                 71.43% | Lightweight baseline model                                                                  |
| EfficientNetB0    |          No |                 77.46% |                 63.03% | Base EfficientNetB0 model                                                                   |
| EfficientNetB0    |    4 layers |                 87.13% |                 75.63% | Fine-tuning improved performance over the base version                                      |
| EfficientNetB0    |    5 layers |                 88.59% |                 75.63% | Best EfficientNetB0 result on the original test set                                         |
| EfficientNetB2    |          No |                 82.30% |                 68.91% | Larger EfficientNet variant without fine-tuning                                             |
| ResNet50          |          No |                 87.29% |                 80.67% | Best model on the external test set                                                         |
| ResNet50          |         Yes |                 91.63% |                 77.31% | Best model on the original test set, but weaker generalization than non-fine-tuned ResNet50 |
| VGG16             |          No |                 75.94% |                 54.24% | Weakest external-test performance                                                           |

## Main findings

The best original test-set performance was achieved by **ResNet50 with fine-tuning**, reaching **91.63% accuracy**. However, on the external test set, the best result came from **ResNet50 without fine-tuning**, with **80.67% accuracy**. This difference suggests that fine-tuning improved performance on the original dataset but did not generalize as well to newly collected real-world images.

All models showed lower accuracy on the external test set compared with the original test set. This confirms that the external images were more challenging because they included different lighting conditions, backgrounds, camera angles, and image quality levels. The result is important because the company scenario requires reliable performance on real product-upload conditions, not only on the original dataset.

Among the tested models, **ResNet50 without fine-tuning** is the strongest candidate for the prototype because it produced the best external-test accuracy. **ResNet50 with fine-tuning** remains useful as the strongest original-dataset model, but its external-test drop indicates possible overfitting or sensitivity to dataset distribution. **VGG16** performed the weakest and is not recommended for the final prototype.

The main error sources were visually similar ball categories, small external-test class sizes, background variation, and image-quality differences. Before real deployment, the model should be tested with more company-specific product images and should include confidence-based human review for uncertain predictions.


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
jupyter notebook notebooks/Final_Notebook.ipynb```

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

