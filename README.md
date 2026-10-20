# Brain Tumour MRI Classification: CNN vs Vision Transformer

A small, honest study of deep learning for classifying brain MRI slices into four classes (glioma, meningioma, no tumour, pituitary), comparing a convolutional network (ResNet-18) with a Vision Transformer (ViT-Small), with explainability and a data-leakage check.

> Status: work in progress. Built as preparation for PhD study in multimodal and explainable medical image analysis.

## Questions
1. How does a pretrained ViT compare with a pretrained CNN on this task?
2. Where in the image do the models look when they decide? (Grad-CAM)
3. How much do near-duplicate images between train and test inflate the reported accuracy?

## Data
[Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) (M. Nickparvar, Kaggle), about 7,000 2D MRI slices in four classes, supplied with a Training/Testing split. The data is not stored in this repository; the notebooks download it.

**Known limitations:** no patient identifiers, so a patient-level split is impossible; mixed scan orientations and contrasts; 2D slices rather than 3D volumes; a single modality.

## Notebooks
| Notebook | What it does | Open |
|---|---|---|
| `01_baseline_classifier.ipynb` | Train and evaluate ResNet-18 / ViT-Small | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]
(https://colab.research.google.com/github/lorawe473/brain-tumour-mri-classifier/blob/main/01_baseline_classifier.ipynb)
 ||
| `02_gradcam.ipynb` | Explanation heatmaps (planned) | |
| `03_leakage_check.ipynb` | Duplicate detection and clean re-split (planned) | |

## Results log
Every run, including bad ones. Test accuracy is measured once per run on the held-out Testing folder.

| Date | Model | Epochs | LR | Seed | Best val acc | Test acc | Notes |
|---|---|---|---|---|---|---|---|

## How to run
Open a notebook in Google Colab, choose `Runtime → Change runtime type → T4 GPU`, then `Runtime → Run all`.

## Acknowledgements
Models from [timm](https://github.com/huggingface/pytorch-image-models). Dataset by Masoud Nickparvar on Kaggle.
