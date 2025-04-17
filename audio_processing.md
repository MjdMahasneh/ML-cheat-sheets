# Audio Processing Cheatsheet

---

## 1. Time-Domain Operations
- **Waveform:** amplitude vs time
- **Silence Removal:** energy thresholding

---

## 2. Frequency-Domain
- **STFT:** frames, window, hop  
  `librosa.stft(y, n_fft=2048, hop_length=512)`
- **Spectrogram:** |STFT|^2

---

## 3. Filtering
- **Lowpass/Highpass:** FIR/IIR design via SciPy or custom kernels.
- **Mel Filterbank:** map FFT bins to mel scale.

---

## 4. Features
- **MFCC:**  
  `librosa.feature.mfcc(y, sr)`
- **Chromagram:**  
  `librosa.feature.chroma_stft(y, sr)`

---

## 5. Applications
- **Voice Activity Detection (VAD)**
- **Pitch Detection:** autocorrelation or cepstrum.
