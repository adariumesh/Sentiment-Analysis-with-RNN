# RNN Sentiment Classification Project

A comprehensive sentiment analysis project comparing RNN, LSTM, and BiLSTM architectures on the IMDb movie review dataset.

## 🛠 Setup Instructions
* **Python Version**: 3.9+
* **Dependencies**: Install from `requirements.txt`
  ```bash
  pip install -r requirements.txt
  ```
* **NLTK Data**: The 'punkt' tokenizer should be pre-downloaded
* **Dataset**: Uses `torchtext.datasets.IMDB` (downloads automatically)

## 🚀 How to Run

### Step 1: Training
Run the main training script to execute all experimental configurations:
```bash
python src/train.py
```

This will:
- Test 54 different hyperparameter combinations
- Train models for 5 epochs each
- Save results to `results/metrics.csv`
- Take approximately 30-60 minutes depending on hardware

### Step 2: Evaluation & Analysis
Generate plots and analysis after training completes:
```bash
python src/evaluate.py
```

This will:
- Load results from `results/metrics.csv`
- Generate performance plots in `results/plots/`
- Print best/worst performing configurations
- Display performance analysis summary

## 📂 Expected Output
* **`results/metrics.csv`**: Complete experimental results with accuracy, F1-score, and timing data
* **`results/plots/`**: Visualization plots including:
  - `accuracy_vs_sequence_length.png`
  - `f1_vs_sequence_length.png` 
  - `performance_by_optimizer.png`
  - `training_time_analysis.png`

## 🔧 Project Structure
```
src/
├── utils.py          # Utility functions (seeds, device selection)
├── preprocess.py     # Data loading and preprocessing
├── models.py         # RNN model architectures
├── train.py          # Main training script
└── evaluate.py       # Analysis and plotting script

results/
├── metrics.csv       # Experimental results (generated)
└── plots/           # Performance visualizations (generated)
```

## 📊 Experimental Design
- **Architectures**: RNN, LSTM, BiLSTM
- **Optimizers**: Adam, SGD, RMSprop
- **Sequence Lengths**: 25, 50, 100 tokens
- **Gradient Clipping**: Enabled/Disabled
- **Activation Functions**: ReLU, Tanh (RNN only)
- **Total Configurations**: 54 unique combinations