# 🩺 Deep Learning for PPG Signal Analysis in Cardiac Abnormality Detection
🧑‍🤝‍🧑Thanks to [Andrea Bertogalli](https://github.com/andberto) and [Niccolò Balestrieri](https://github.com/NiccoloBalestrieri)
## Overview

This project explores the utilization of deep learning techniques in analyzing Photoplethysmography (PPG) signals to identify cardiovascular abnormalities, specifically Premature Atrial Complex (PAC) and Premature Ventricular Complex (PVC). By leveraging the power of neural networks, we aim to bypass traditional manual feature extraction methods, enhancing diagnostic accuracy and scalability.

![pipeline](https://github.com/tombinic/PPGAnalysis/assets/91635053/eb2e1496-98ae-4f54-b503-3a8456d41da3)


*Figure 1: Project Workflow Overview*

## Dataset

The dataset includes PPG signals from 105 patients, labeled into three categories: Normal (N), Premature Systole (S), and Premature Ventricular Contraction (V). The signals vary in sampling frequencies, primarily 128 Hz and 250 Hz.

## Preprocessing

Our preprocessing pipeline involves several key steps to ensure the data is primed for model training:

1. **Frequency Standardization**: Resampling all signals to a uniform frequency of 250Hz.
2. **Denoising**: Employing wavelet transform techniques to cleanse the signals of noise.
3. **Artifacts Removal**: Utilizing double soft thresholding and hard thresholding on the frequency spectrum to eliminate signal artifacts.
4. **Dataset Creation**: Constructing a balanced dataset by extracting windows around each signal peak.

![artifact2](https://github.com/tombinic/PPGAnalysis/assets/91635053/c893b61c-b2f7-4365-94a1-773d56b24a20)


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

## Explainability

To understand the decision-making process of our models, we employed Grad-CAM++, generating saliency maps that highlight the regions of the signal most influential in the model's predictions.

![0](https://github.com/tombinic/PPGAnalysis/assets/91635053/fbbc9d1a-4b13-49e8-8668-3937a7ed6d87)

*Figure 4: Grad-CAM++ Visualization for Class N*

## Conclusion

This project represents a significant step towards the application of deep learning in the domain of cardiac abnormality detection using PPG signals.

## How to Use

Detailed instructions on how to set up the environment, preprocess the data, train the models, and interpret the results can be found in the notebook in this folder. Just run the various cells.
Clearly could be some errors due to path or missing files.
