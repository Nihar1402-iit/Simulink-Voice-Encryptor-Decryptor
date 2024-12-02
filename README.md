# Simulink Voice Encryption App

This project demonstrates a Simulink-based Android/iOS application for secure voice message transmission between two mobile phones over Bluetooth. The app implements two encryption methods to scramble or obscure audio signals on Phone A, transmits the encrypted signal, and decrypts and plays it on Phone B.

---

## Features
- **Encryption Methods on Phone A:**
  - **Method 1:** Scramble the spectrum of the audio signal to make it unintelligible.
  - **Method 2:** Add noise signals (e.g., pure tones) to obscure the audio.
- **UI Options on Phone A:**
  - Select Encryption Method 1 or 2.
- **Decryption on Phone B:**
  - Receive and process the transmitted audio signal.
  - Play encrypted or decrypted audio with UI options:
    - Play Encrypted Audio.
    - Play Decrypted Audio (Method 1).
    - Play Decrypted Audio (Method 2).

---

## Demonstration Video
Watch the video demonstrating the functionality of the application:

[![Simulink Voice Encryption App](https://github.com/user-attachments/assets/6b88f9b5-3da6-4508-826c-17e033e8352d)](https://drive.google.com/file/d/15KiptKElkYoHw33UZ_5sMiU2KeJ5KjNq/view?usp=sharing)

---

## How It Works
1. **Phone A:**
   - Captures the voice message.
   - Encrypts the audio using the selected method.
   - Transmits the encrypted signal over Bluetooth.

2. **Phone B:**
   - Receives the encrypted signal via Bluetooth.
   - Decrypts the signal using the corresponding decryption algorithm.
   - Plays either the encrypted or decrypted audio based on user choice.

---

## Application Design
The application is developed using Simulink with MATLAB Mobile Support for Android/iOS. It utilizes Bluetooth communication blocks for signal transmission and filtering blocks for encryption and decryption.

### Encryption Methods
- **Method 1 (Spectrum Scrambling):** 
  - Applies a frequency domain transformation to scramble the audio signal.
  - Designed using FFT-based spectrum manipulation.
  
- **Method 2 (Noise Addition):**
  - Adds carefully designed noise signals (e.g., sine waves or white noise) to mask the original audio.
  - Noise is generated using signal generator blocks in Simulink.

### Decryption
- Decryption filters reverse the transformations applied during encryption:
  - **For Method 1:** Inverse frequency transformation restores intelligibility.
  - **For Method 2:** Subtracts or cancels out the added noise signals.
