*∿*

**Audio Noise Reducer**Noise Reduction using Singular Value Decomposition

[Home](#home)[Process](#process)[Results](#results)[About](#about)

# Clean Your Audio with SVD

A noisy audio clip becomes a Time × Frequency matrix (STFT). SVD splits it into strong signal parts and weak noise parts. We drop the weak ones and rebuild a cleaner sound.

[⬆ Upload Audio](#upload)

## 1. Upload Audio

Supported formats: WAV, MP3 (first 5 seconds are processed in the browser)

🎵

**Drag & drop an audio file here**\
or click to browse · WAV, MP3

📄 File: **none**⏱ Duration: **–**

## 2. Processing Pipeline

Each step transforms the signal. The highlighted card shows the step currently running.

A = U Σ Vᵀ

Large singular values represent important signal information, while smaller singular values are treated as noise.

## 3. SVD Visualization

**Singular values kept (k):** –

### 📊 Original Matrix A

STFT magnitude (time → , frequency ↑)

### 📈 Singular Values σ

Sorted largest to smallest

### ✂ Filtered Singular Values

Small values set to zero

keptremoved

### 🔁 Reconstructed Matrix Aₖ

Spectrogram after rank reduction

### Before: Noisy Waveform

Original signal

### After: Clean Waveform

Reconstructed signal

## 4. Results

Listen and compare.

### 🔊 Original Noisy Audio

### ✅ Cleaned Audio

–

Noise Reduction (energy removed)

–

Signal Quality (energy kept by top-k σ)

–

Singular Values Removed

–

Processing Time

## 5. The Math, Simply

Five beginner questions.

A = U Σ Vᵀ

### What is STFT?

The Short-Time Fourier Transform cuts audio into tiny overlapping windows and finds which frequencies are present in each one. The result is a Time × Frequency matrix A.

### What is SVD?

Singular Value Decomposition writes any matrix as A = UΣVᵀ: a sum of simple layers, each with a strength (σ), a time pattern (column of U) and a frequency pattern (column of V).

### What are singular values?

They are the diagonal numbers of Σ, sorted σ₁ ≥ σ₂ ≥ … ≥ 0. Each tells how much of the matrix's energy its layer carries.

### Why remove small singular values?

Speech or music has structure, so a few layers carry most energy. Random noise spreads thinly over many layers with small σ. Dropping those removes most noise.

### How is the clean signal rebuilt?

Keep only the top k layers: Aₖ = σ₁u₁v₁ᵀ + … + σₖuₖvₖᵀ. Then combine Aₖ with the original phase and apply the inverse STFT (overlap-add) to get audio back.

**B.Tech Mathematics Mini Project**\
Audio Noise Reducer using SVD\
Student Project