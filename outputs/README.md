# Organized Notebook Outputs

This folder contains the final output figures and metrics extracted directly from `Final_Notebook.ipynb`.

## Structure

```text
## Output files

The `outputs/` folder contains the final visual and numerical results generated from the completed notebook.

```text
outputs/
├── figures/
│   ├── confusion_matrices/
│   │   ├── original_test/
│   │   └── external_test/
│   ├── dataset_overview/
│   ├── error_analysis/
│   │   ├── original_test/
│   │   └── external_test/
│   ├── external_test_predictions/
│   ├── model_comparison/
│   ├── sample_predictions/
│   │   └── original_test/
│   └── training_curves/
└── metrics/
    ├── classification_reports/
    │   ├── original_test/
    │   └── external_test/
    ├── training_logs/
    ├── extraction_summary.txt
    ├── final_metrics.csv
    ├── notebook_output_manifest.csv
    └── outputs_tree.txt
```

The figures include dataset overview plots, training curves, confusion matrices, random prediction examples, external test-set predictions, and misclassified examples. These files support the notebook evaluation and the error analysis required for the project.

```

## What each folder contains

- `dataset_overview/`: class distribution and sample training images.
- `training_curves/`: accuracy and loss curves from model training.
- `confusion_matrices/original_test/`: confusion matrices from the original test split.
- `confusion_matrices/external_test/`: confusion matrices from the new external/unseen test set.
- `sample_predictions/original_test/`: sample predictions on the original test set.
- `external_test_predictions/`: sample predictions on the external/unseen test set.
- `error_analysis/`: wrong predictions and misclassified examples.
- `model_comparison/`: final comparison chart of model accuracy on original test data and external unseen data.
- `metrics/final_metrics.csv`: summary of original-test and external-test accuracy.
- `metrics/notebook_output_manifest.csv`: mapping between notebook cells and renamed output files.

## Key result summary

The final comparison extracted from the notebook shows that `ResNet50 with fine-tuning` achieved the highest original-test accuracy, while `ResNet50 no fine-tuning` achieved the highest external unseen-test accuracy among the final comparison models.
