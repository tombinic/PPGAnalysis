# 🩺 Deep Learning for PPG Signal Analysis in Cardiac Abnormality Detection

## Overview

This project explores the utilization of deep learning techniques in analyzing Photoplethysmography (PPG) signals to identify cardiovascular abnormalities, specifically Premature Atrial Complex (PAC) and Premature Ventricular Complex (PVC). By leveraging the power of neural networks, we aim to bypass traditional manual feature extraction methods, enhancing diagnostic accuracy and scalability.

![Project Workflow](path/to/figure1.png)

*Figure 1: Project Workflow Overview*

## Dataset

The dataset includes PPG signals from 105 patients, labeled into three categories: Normal (N), Premature Systole (S), and Premature Ventricular Contraction (V). The signals vary in sampling frequencies, primarily 128 Hz and 250 Hz.

## Preprocessing

Our preprocessing pipeline involves several key steps to ensure the data is primed for model training:

1. **Frequency Standardization**: Resampling all signals to a uniform frequency of 250Hz.
2. **Denoising**: Employing wavelet transform techniques to cleanse the signals of noise.
3. **Artifacts Removal**: Utilizing double soft thresholding and hard thresholding on the frequency spectrum to eliminate signal artifacts.
4. **Dataset Creation**: Constructing a balanced dataset by extracting windows around each signal peak.

![Denoised Signal Example](path/to/figure6.png)

*Figure 2: Example of a Denoised Signal*

## Models

We experimented with several deep learning models, notably:

- **VGG with Conv1D**
- **ResNet + CBAM with Conv1D**
- **EfficienNetB7 with Conv2D**
- **CNN + Bidirectional LSTM**

Our models were trained to perform both binary classification (N vs. S-V) and multi-class classification (N vs. S vs. V).

## Results

Our models demonstrated promising results in distinguishing between normal and abnormal PPG signals. The binary classifier achieved a Recall of 0.72, while the multi-class classifier showcased a Macro F1-Score of 0.65.

![Confusion Matrix](path/to/figure14.png)

*Figure 3: Confusion Matrix for the Multi-Class Classifier*

## Explainability

To understand the decision-making process of our models, we employed Grad-CAM++, generating saliency maps that highlight the regions of the signal most influential in the model's predictions.

![Grad-CAM++ for Class N](path/to/figure18.png)

*Figure 4: Grad-CAM++ Visualization for Class N*

## Conclusion

This project represents a significant step towards the application of deep learning in the domain of cardiac abnormality detection using PPG signals. Our approach not only improves diagnostic accuracy but also lays the groundwork for future research in this field.

## How to Use

Detailed instructions on how to set up the environment, preprocess the data, train the models, and interpret the results can be found in the subsequent sections of this README.
