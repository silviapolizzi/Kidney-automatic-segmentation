# Kidney Automatic Segmentation

This repository contains a complete pipeline for the automatic segmentation of the kidney and its possible carcinoma from medical images, developed for the Kidney Cancer Challenge.

## Objective

The goal is to implement an automatic segmentation method for the kidney and its possible carcinoma, providing support for the identification of tumor masses and speeding up subsequent procedures of diagnosis, preoperative planning, and therapy.

## Methodology

The proposed method consists of a **cascade of two U-Net networks**:
- The first network (**2D**) provides a pre-segmentation of the kidney-tumor complex, which is then used to train the second network.
- The second network (**3D**) outputs the separate segmentation of kidney and tumor.

## Results

The results obtained in terms of Dice Similarity Coefficient (DSC) are:
- **Training Set**: 95.75% for the kidney-tumor complex, 76.42% for the tumor
- **Validation Set**: 94.46% for the kidney-tumor complex, 36.03% for the tumor

## Conclusions

The proposed method achieves satisfactory results, considering the limited computational resources available. However, the performance on the Validation Set highlights the need for improvements to enhance the generalization capability of the classification algorithm.

## Project Structure

- **ROI_preparation.ipynb**: Preparation of Regions of Interest (ROI) and data pre-processing.
- **Rete_2D.ipynb**: Implementation and training of a 2D convolutional neural network for segmentation.
- **Rete_3D.ipynb**: Implementation and training of a 3D convolutional neural network for volumetric segmentation.
- **Testing.ipynb**: Evaluation of model performance and comparison between 2D and 3D approaches.

## Requirements

The notebooks use Python and require the following main libraries:
- numpy, matplotlib, scikit-image, nibabel, SimpleITK
- tensorflow, keras, tqdm, plotly

Some notebooks are designed to be run on Google Colab and require connecting to Google Drive for data loading.

## Usage

1. Run `ROI_preparation.ipynb` to prepare the data.
2. Choose and train a model with `Rete_2D.ipynb` or `Rete_3D.ipynb`.
3. Evaluate the results with `Testing.ipynb`.

## Notes

Make sure you have the data in NIfTI format (.nii) and modify the paths in the notebooks according to your data structure.

**Note:** This is a group project for the "Elaborazione di Immagini Mediche" exam at Politecnico di Torino.
