# Visual Imagery EEG BCI (Microsoft Research Internship Project)

![Real-Time Visual Imagery BCI System](system_diagram.png)

This repository contains code and tutorials for investigating **visual imagery as a control paradigm for EEG-based brain-computer interfaces (BCIs)**.

The project is based on the following publication:

**Kilmarx, J., Gamper, H., Emmanouilidou, D., Johnston, D., Cutrell, E., Wilson, A., & Tashev, I. (2022, February). Investigating visual imagery as a BCI control strategy: A pilot study. In 2022 10th International Winter Conference on Brain-Computer Interface (BCI) (pp. 1-6). IEEE.**

---

## 🎥 Project Overview & Live Demo

This project includes a full end-to-end pipeline for **real-time EEG decoding and closed-loop BCI control**.

The demo below shows:

- Real-time EEG acquisition

- Online preprocessing and feature extraction

- Live classification of visual imagery (face / scene / rest)

- Closed-loop feedback to the user

[Visual Imagery EEG BCI – System Demo](https://www.youtube.com/watch?v=oazo3n4echQ)

---

## 🚀 Overview

Most EEG-based BCIs rely on:
- External stimuli (e.g., P300, SSVEP)
- Motor imagery (sensorimotor rhythms)

This project explores **visual imagery** as an alternative control strategy, where users imagine visual concepts (e.g., faces vs scenes) to drive classification.

Key findings:
- ~64% accuracy for face vs scene imagery (offline)
- ~60% cross-session generalization
- ~47% accuracy in real-time 3-class BCI (face / scene / rest)

These results demonstrate that visual imagery is a **feasible and intuitive BCI control paradigm**, with potential advantages in scalability and usability.

---

## 📊 Repository Contents

### 🧪 Tutorial Notebook
`analysis_tutorial.ipynb`

Step-by-step walkthrough of:
- EEG preprocessing
- Feature extraction (power spectrum)
- Classification (SVM)
- Cross-validation

---

### ⚙️ Analysis Utilities
`analysis_functions.py`

Helper functions for:
- Filtering (bandpass + notch)
- Epoching EEG data
- Power spectral feature extraction
- Model training and evaluation

---

### ⚡ Real-Time Pipeline
`main_realtime_nk.py`  
`processing_nk.py`

Example implementation of a **real-time EEG decoding system**, including:
- Streaming data processing
- Online feature extraction
- Real-time classification
- Feedback loop

---

## 🧠 Method Summary

### Data Acquisition
- 32-channel EEG (10–20 system)
- Sampling rate: 500 Hz
- Dry electrode system

### Preprocessing
- Bandpass filtering:
  - 1–40 Hz (observation)
  - 1–125 Hz (imagery)
- Notch filtering at 60 Hz (and harmonic)
- Epoching into overlapping windows

### Features
- Power spectrum (1–100 Hz)

### Model
- Linear SVM
- Leave-one-run-out cross-validation

### Real-Time Inference
- Single-epoch classification from mid-trial window
- Closed-loop feedback

---

## 🧪 Key Insight

Visual imagery performance depends strongly on **representational separability**:

- Faces vs scenes → strong separability → better decoding
- Objects (e.g., flower vs hammer) → higher similarity → worse decoding

---


