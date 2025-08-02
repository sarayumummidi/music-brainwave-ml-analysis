# EEG Brainwave Analysis During Music Listening

This project analyzes EEG (electroencephalography) brainwave data collected from participants while they listen to music in different auditory conditions such as shuffled, reverbed, reversed, and original forms. The goal is to investigate how the brain's electrical activity varies across these different listening experiences.

---
## Dataset

This project uses the EEG dataset from Stanford's Stacks repository. It contains raw EEG recordings of participants listening to music in various auditory conditions.

- **File used:** `S1_1_raw.mat`
- **Size:** ~88 MB
- **Format:** MATLAB `.mat` file with multi-channel EEG data, event triggers, and sampling frequency.

You can download the dataset directly using:

```bash
wget https://stacks.stanford.edu/file/druid:sd922db3535/S1_1_raw.mat
```
---

## Project Overview

- Load and preprocess raw EEG data using Python libraries:
  - `scipy.io` for reading `.mat` files.
  - `mne` for EEG-specific data handling and preprocessing.
- Extract event triggers and onsets, map them to integer event IDs.
- Apply bandpass filtering (e.g., 1–50 Hz) to isolate relevant brainwave frequencies.
- Epoch the continuous EEG data around event onsets to analyze brain responses.
- Compute power spectral density (PSD) for each epoch using multitaper methods.
- Calculate band power features across canonical frequency bands:
  - Delta (1–4 Hz)
  - Theta (4–8 Hz)
  - Alpha (8–13 Hz)
  - Beta (13–30 Hz)
  - Gamma (30–50 Hz)
- Visualize data including raw signals, event distributions, and band power heatmaps.
- Experiment with noisy data simulation to assess robustness of spectral features.

---

## Usage

1. Clone the repository.
2. Install dependencies:

   ```bash
   pip install mne scipy matplotlib seaborn numpy
   ```
3. Place your `.mat` EEG data files in the project directory.

4. Run the main analysis script (e.g., `Music_EEG_Analysis.ipynb`) to:
   - Load and preprocess data
   - Generate epochs
   - Compute and visualize band powers

---

## Visualizations

- Time series plots of EEG channels during different auditory conditions.
- Heatmaps of log-transformed band power across epochs and channels.
- Comparative plots of original vs noisy EEG data spectral features.
