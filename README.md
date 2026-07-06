# Audio Encryption Using EMD and 2D Cosine Logistic Map

## Overview

This project implements a secure audio encryption and decryption scheme based on:

- Empirical Mode Decomposition (EMD)
- 2D Cosine Logistic Map (2DCLM)
- SHA3-512 Hashing

The encryption process is inspired by the research paper:

**"An Audio Encryption Scheme Based on Empirical Mode Decomposition and 2D Cosine Logistic Map"**
by Alenrex Maity and Bibhas Chandra Dhara.

The objective is to provide a robust audio encryption mechanism that offers high security, plaintext sensitivity, large key space, and resistance against statistical and differential attacks.

---

## Features

- Audio file encryption and decryption
- SHA3-512 based key generation
- Audio-dependent encryption key
- Chaotic sequence generation using 2DCLM
- Empirical Mode Decomposition (EMD)
- Audio scrambling and diffusion
- High sensitivity to plaintext and encryption keys
- Secure against brute-force and statistical attacks

---

## Encryption Workflow

1. Load input audio file.
2. Generate SHA3-512 hash of the audio signal.
3. Extract chaotic parameters from the hash.
4. Generate chaotic sequences using 2D Cosine Logistic Map.
5. Scramble the audio samples.
6. Convert the signal into a 2D matrix.
7. Apply Empirical Mode Decomposition (EMD).
8. Encrypt residue components using chaotic keystream.
9. Reconstruct encrypted audio.
10. Save encrypted output.

---

## Decryption Workflow

1. Load encrypted audio.
2. Generate the same key parameters.
3. Generate identical chaotic sequences.
4. Apply reverse diffusion process.
5. Recover residue components.
6. Reconstruct original audio using EMD.
7. Unscramble audio samples.
8. Recover original audio signal.

---

## Project Structure

```text
.
├── audioencryption_updated.ipynb
├── data/
├── results/
└── README.md
```

---

## Requirements

Install the required Python packages:

```bash
pip install numpy
pip install scipy
pip install librosa
pip install soundfile
pip install pyemd
pip install matplotlib
pip install hashlib
```

---

## Usage

### Run the Notebook

Open Jupyter Notebook:

```bash
jupyter notebook
```

Then execute:

```text
audioencryption.ipynb
```

### Encryption

- Provide an input audio file.
- Run all notebook cells.
- The encrypted audio file will be generated automatically.

### Decryption

- Use the same key/hash parameters.
- Run the decryption section.
- The original audio will be reconstructed.

---

## Security Characteristics

### Large Key Space

- SHA3-512 generates a 512-bit key.
- Key space size:

```text
2^512
```

which is significantly larger than the minimum requirement against brute-force attacks.

### Plaintext Sensitivity

A single-bit modification in the original audio produces a completely different encrypted output.

### Key Sensitivity

Even a tiny modification in the key results in failed decryption.

### Statistical Resistance

The encrypted audio exhibits:

- Near-uniform histogram
- Low correlation between adjacent samples
- High entropy

---

## Results

The encryption process successfully:

- Hides audio content completely.
- Produces noise-like encrypted signals.
- Recovers the original signal accurately using the correct key.
- Fails to decrypt when incorrect keys are used.

---

## Research Reference

Maity, A., & Dhara, B. C. (2024).

**An Audio Encryption Scheme Based on Empirical Mode Decomposition and 2D Cosine Logistic Map**

IEEE Latin America Transactions, Vol. 22, No. 4.

---

## Future Improvements

- Faster EMD implementation
- Real-time audio encryption
- GUI-based application
- Support for audio streaming
- Extension to image and video encryption

---

## Author

Pragadheesh Chandramohan

Computer Science Engineering Student

---

## License

This project is intended for educational and research purposes.
