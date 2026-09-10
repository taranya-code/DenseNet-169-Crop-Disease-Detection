# DenseNet-169 — Crop Disease Detection

Transfer-learning pipeline using **DenseNet-169** to classify healthy vs. diseased crop leaves, benchmarked across four public Kaggle datasets. Companion notebook to the [ResNet-50 version](https://www.kaggle.com/code/taranyasaravanan/resnet-50-crop-disease-detection).

🔗 Notebook: https://www.kaggle.com/code/taranyasaravanan/densenet-169-crop-disease-dectection

## Results

| Dataset | Source | Accuracy | F1-score |
|---|---|---|---|
| New Plant Diseases Dataset | [vipoooool](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset) | 99.81% | 99.81% |
| PlantVillage Dataset | [abdallahalidev](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) | 99.72% | 99.59% |
| PlantDoc | [nirmalsankalana](https://www.kaggle.com/datasets/nirmalsankalana/plantdoc-dataset) | 99.64% | 99.65% |
| PlantVillage Dataset | [emmarex/plantdisease](https://www.kaggle.com/datasets/emmarex/plantdisease) | 90.21% | 89.54% |

## Approach

- Backbone: DenseNet-169 (ImageNet-pretrained), fine-tuned per dataset in two phases (initial head training, then full fine-tune)
- Data augmentation applied to training images before fine-tuning
- Evaluated on a held-out test split for each dataset, with confusion matrices and accuracy/loss curves logged per run
- Strong, consistent performance across three of the four datasets; the emmarex/plantdisease split shows more train/val divergence than the others, suggesting it may benefit from further regularization or more epochs

## Notes

- PlantVillage Dataset appears twice (rows 2 and 4) sourced from two different Kaggle uploads of the same underlying data, evaluated separately for consistency.
