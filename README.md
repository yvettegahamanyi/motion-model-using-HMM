# Human Activity Recognition using Hidden Markov Models (HMM)

This repository contains the implementation of a complete Hidden Markov Model (HMM) pipeline to classify four human activity states — **Walking**, **Standing**, **Jumping**, and **Still** — from accelerometer and gyroscope sensor data.

## Overview
This project was developed as part of **ALU MLTech — Formative 2**. The model uses sensor data collected with the Sensor Logger app to estimate the underlying activity state. It builds Gaussian HMMs for each activity and uses the Viterbi algorithm and log-likelihood comparisons to decode and classify sequences.

## Features
- **Data Source**: Sensor Logger app accelerometer and gyroscope readings.
- **Model**: Gaussian HMM (`hmmlearn`).
- **Hidden States**: 2 intra-activity sub-states per model.
- **Algorithm**: Baum-Welch EM (`tol=0.0001`, `max_iter=200`).
- **Decoding**: Viterbi (log-likelihood comparison across models).
- **Extracted Features**: 67 statistical and frequency-domain features per window (100 samples per window, 50% overlap).
- **Performance**: Achieved 100% (1.0) Macro-avg accuracy across all four classes on the test set.

## Project Structure
- `Formative_2_HMM_Activity_Recognition.ipynb`: Main Jupyter Notebook containing the full pipeline including data loading, preprocessing, model training, evaluation, and analysis.
- `Data/`: Directory containing the preprocessed feature sets and raw labeled session files.
- `Visualization/`: Directory containing plots and visual results (e.g., transition matrices, class accuracies).

## Prerequisites and Configuration
If you download or clone the project, you will need to set up your Python environment with the necessary dependencies.

1. Ensure you have Python 3 installed.
2. Install the required packages using pip:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn hmmlearn scipy joblib
```

## Running the Project
1. Clone the repository to your local machine:
```bash
git clone https://github.com/yvettegahamanyi/motion-model-using-HMM.git
cd motion-model-using-HMM
```

2. Open the Jupyter Notebook:
```bash
jupyter-notebook Formative_2_HMM_Activity_Recognition.ipynb
```

3. Run the cells in order. The notebook is configured to automatically stream the required dataset directly from the `Data/dataset` directory in the GitHub repository, so no manual data downloading is required.

## Results Analysis
Based on the test set evaluation, the model achieved perfect separation:
- **Walking**: 100% Accuracy
- **Standing**: 100% Accuracy
- **Jumping**: 100% Accuracy
- **Still**: 100% Accuracy
