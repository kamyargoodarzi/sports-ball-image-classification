# Model Card: Sports Ball Classifier

## Intended use

This model is intended as a prototype for classifying sports ball product images into predefined categories.

## Not intended for

- Fully automated production deployment without human review
- Images outside the trained class list
- Product images with severe occlusion, extremely low resolution, or ambiguous visual content

## Training data

The model was trained on the original sports ball dataset provided for the AI bootcamp project.

## Evaluation data

The model was evaluated on:

1. The original test set
2. A new external test set collected outside the original dataset

## Metrics

Update with final values.

| Metric | Value |
|---|---:|
| Original test accuracy | TODO |
| External test accuracy | TODO |
| Best model | TODO |

## Main limitations

- Similar ball types can be confused.
- Real-world images may differ from the training distribution.
- The external test set is relatively small.
- More data is needed before production deployment.

## Recommended next steps

- Collect more real product images from the company workflow.
- Improve class balance.
- Add more difficult examples from real-world conditions.
- Test the model continuously after deployment.
- Use human review for low-confidence predictions.
