# Speech Emotion Recognition
The project leverages Librosa for audio feature extraction, including MFCCs and spectral features and uses TensorFlow to develop a deep learning model for classifying emotions like happiness, sadness and anger. It incorporates spectrogram analysis for visual insights and supports real-time emotion recognition for practical applications.

## Execution Guide:
1. Run the following command line in the terminal:
   ```
   pip install numpy pandas librosa matplotlib seaborn tensorflow keras sounddevice
   ```

2. Download the dataset (link to the dataset: **https://www.kaggle.com/datasets/ejlok1/toronto-emotional-speech-set-tess**)

3. Upon running the code, it also saves an addition file named `model.keras` (this file stores the trained model)

4. Enter the path of the audio file in the code.

## Accuracy & Loss Over Epochs:

![image](https://github.com/user-attachments/assets/e338a8ab-2a28-48ed-869a-ef683602cbc5)

![image](https://github.com/user-attachments/assets/95158724-54a8-4734-a009-72510c038877)

## Model Prediction:

   ![image](https://github.com/user-attachments/assets/1609e53a-ac10-46f6-8ddd-c413baddc4d1)

## Overview:
The code is a complete implementation for **Speech Emotion Recognition (SER)**. The goal of this project is to predict the emotional state (e.g., happy, sad, angry) of a speaker based on their speech audio files. Below is an overview of the code's key components:


### **1. Dataset Handling**
- **Dataset**: The Toronto Emotional Speech Set (TESS), downloaded from Kaggle, contains labeled speech audio files corresponding to various emotions.
- **Labels**: The emotions include *fear, sad, angry, disgust, pleasant surprise (ps), neutral*, and *happy*. The labels are extracted from file names.
- **MFCC Features**: 
  - The **Mel-frequency cepstral coefficients (MFCC)**, which are widely used for speech processing, are computed for each audio file. MFCCs capture the frequency distribution of the audio signal in a way that reflects how humans perceive sound.

### **2. Data Preparation**
- **Feature Extraction**: 
  - A function is defined to compute 40 MFCC coefficients for each audio file. These coefficients are averaged over time for dimensionality reduction.
  - The MFCCs are stored in a numpy array, reshaped into `(2800, 40, 1)` for compatibility with neural networks.
- **Label Encoding**: 
  - Labels are one-hot encoded (e.g., `[1, 0, 0, 0, 0, 0, 0]` for the emotion "fear").
- **Train-Test Split**: The dataset is divided into 80% training and 20% testing.

### **3. Model Architecture**
The model is a **Sequential Neural Network** with the following layers:
- **LSTM Layer**: A Long Short-Term Memory (LSTM) layer processes sequential MFCC features to capture temporal dependencies in the speech data.
- **Batch Normalization**: Stabilizes and accelerates training by normalizing intermediate layer outputs.
- **Dense Layers**: Fully connected layers with decreasing units (256 → 128 → 64 → 32) for feature transformation.
- **Dropout Layers**: Applied after each dense layer to reduce overfitting.
- **Output Layer**: A dense layer with 7 units (one for each emotion) and a softmax activation to produce probabilities.

### **4. Model Training**
- **Loss Function**: Categorical crossentropy, used for multi-class classification.
- **Optimizer**: Adam optimizer for adaptive learning rate adjustments.
- **Evaluation Metrics**: Accuracy is used to monitor training and validation performance.
- **Visualization**:
  - Training and validation accuracy and loss are plotted over epochs.

### **5. Model Evaluation**
- The trained model achieves a high **validation accuracy of 97.86%**.
- The model is saved as a `.keras` file for future use.

### **6. Prediction and Visualization**
- **Emotion Prediction**: 
  - A function predicts the emotion of a given audio file using the trained model and provides a confidence score.
- **Audio Playback and Visualization**:
  - The `play_audio()` function plays the audio file.
  - The `display_audio_visuals()` function generates waveforms and spectrograms of the audio signal, providing insights into its structure and intensity.

### **Key Features of the Code**
- **End-to-End Pipeline**: Covers data loading, preprocessing, feature extraction, model training, evaluation, and prediction.
- **Visualization**: Includes spectrograms and waveforms for intuitive understanding of audio signals.
- **Scalability**: The modular structure allows easy experimentation with different datasets, features, or models.

This project highlights how deep learning can be applied to **audio signal processing** for practical applications like human-computer interaction, mental health monitoring, and emotion-aware systems.
