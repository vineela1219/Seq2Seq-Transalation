# Seq2Seq-Transalation
# Dakshina Transliteration using Seq2Seq RNNs with Attention

## Project Overview
This project implements a character-level sequence-to-sequence (Seq2Seq) neural network for transliterating Romanized Hindi words into Devanagari script using the Dakshina dataset.

The objective is to compare different recurrent neural network architectures (RNN, GRU, and LSTM) and analyze the impact of attention mechanisms on transliteration performance.

## Dataset
Dataset: Dakshina Hindi Transliteration Dataset

Files used:

* hi.translit.sampled.train.tsv
* hi.translit.sampled.dev.tsv
* hi.translit.sampled.test.tsv

Each record contains:
* Native Hindi word (Devanagari)
* Romanized Hindi word
* Frequency count
## Model Architecture
### Encoder
* Character Embedding Layer
* Recurrent Neural Network (RNN / GRU / LSTM)
* Multiple hidden layers
* Dropout regularization
### Attention Mechanism
* Bahdanau-style additive attention
* Computes alignment scores between decoder hidden states and encoder outputs
### Decoder
* Character Embedding Layer
* Attention Context Vector
* Recurrent Neural Network (RNN / GRU / LSTM)
* Fully Connected Output Layer
## Hyperparameters
| Parameter           | Value |
| ------------------- | ----- |
| Embedding Dimension | 128   |
| Hidden Dimension    | 256   |
| Number of Layers    | 2     |
| Dropout             | 0.3   |
| Batch Size          | 64    |
| Learning Rate       | 0.001 |
| Epochs              | 3     |

## Experiments
The following recurrent cells were evaluated:
1. Vanilla RNN
2. GRU
3. LSTM
Performance metrics:
* Validation Loss
* Validation Accuracy
* Training Time

## Attention Visualization

Attention heatmaps were generated to visualize the alignment between:
* Input Romanized characters
* Output Devanagari characters
This helps understand how the model learns character-level mappings during transliteration.
## Hyperparameter Optimization
Weights & Biases (W&B) Sweeps were used for hyperparameter tuning.
Parameters explored:
* Embedding Dimension
* Hidden Size
* Encoder Layers
* Decoder Layers
* Cell Type
* Dropout
* Learning Rate
* Beam Size
Optimization Method:
* Bayesian Search
## Results

The models were compared based on:
* Validation Accuracy
* Validation Loss
* Training Efficiency
The best-performing model was selected and used for final test predictions.
## Generated Outputs
The project produces:
* Trained model checkpoints
* Attention heatmaps
* Validation metrics
* Test set predictions (test_predictions.csv)

## Libraries Used

* PyTorch
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Weights & Biases (W&B)
* Google Colab

## Running the Project

Install dependencies:

pip install torch torchvision torchaudio

pip install pandas numpy matplotlib seaborn scikit-learn tqdm wandb

Mount Google Drive and place dataset files inside Google Drive before execution.

Run all notebook cells sequentially to:

1. Build vocabularies
2. Train models
3. Evaluate performance
4. Generate attention visualizations
5. Perform hyperparameter sweeps
6. Save predictions

## Author

Dakshina Transliteration Assignment implemented using Seq2Seq RNNs with Attention in PyTorch.

Report link:
https://api.wandb.ai/links/models-jawaharlal-nehru-technological-university/a1edj1xp

