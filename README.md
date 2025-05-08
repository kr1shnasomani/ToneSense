<h1 align="center">ToneSense</h1>
<p align="center" style="margin-top:30px;">
  <img src="https://github.com/user-attachments/assets/7358a08c-5d57-4bec-98c8-dfbb28733604" height="150cm"/>
</p>
The project leverages Librosa for audio feature extraction, including MFCCs and spectral features and uses TensorFlow to develop a deep learning model for classifying emotions like happiness, sadness and anger. It incorporates spectrogram analysis for visual insights and supports real-time emotion recognition for practical applications.

## Execution Guide:
1. Clone the repository:
   ```
   git clone https://github.com/kr1shnasomani/ToneSense.git
   cd ToneSense
   ```

2. Download the dependencies:
   ```
   pip install -r requirements
   ```

3. Run the code and it will save the model with the name `model.keras`

## Accuracy & Loss Over Epochs:

![image](https://github.com/user-attachments/assets/e338a8ab-2a28-48ed-869a-ef683602cbc5)

![image](https://github.com/user-attachments/assets/95158724-54a8-4734-a009-72510c038877)

## Model Prediction:

   Input (the file is in `.mp4` format as GitHub doesn't support audio files):
   
   https://github.com/user-attachments/assets/d74d7fdf-802e-4742-8cde-9e434c969e32

   Output:
   
   ![image](https://github.com/user-attachments/assets/1609e53a-ac10-46f6-8ddd-c413baddc4d1)
