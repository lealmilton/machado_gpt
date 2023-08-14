# Bigram Language Model trained on Machado de Assis's full work
## Overview
This project uses a custom bigram language model, inspired by the transformer architectures as described in Andrej Karpathy's video tutorial "Let's build GPT: from scratch, in code, spelled out." The model is trained on the full literary works of Machado de Assis, a renowned Brazilian writer. The objective is to comprehend and generate text in the author's style based on a provided context.

## Dataset
File Location: all.txt
Description: Preprocessed texts from Machado de Assis's entire works.
Source: https://www.kaggle.com/datasets/luxedo/machado-de-assis

## Model Architecture
- Token and Positional Embeddings
- Stacked Transformer blocks, each comprising:
    - Multi-head attention mechanism 
    - Feed-forward neural network
- Final linear layer mapping to vocabulary size

## Prerequisites
Python 3
PyTorch
CUDA (for GPU acceleration)

# How to Run

### Setup & Installation

```bash
git clone https://github.com/lealmilton/machado_gpt.git
cd machado_gpt
python -m venv venv
pip install -r requirements.txt
```

### Preprocessing:

Within the processed folder, you'll find an all.txt file. This file contains preprocessed versions of Machado de Assis's complete works and is the default dataset used for training.

If you wish to train the model on a different dataset:

- Ensure your data is in a .txt format.
- Replace the all.txt file in the processed folder with your desired dataset (while still naming it all.txt).
- Any long .txt file is suitable for training, ensuring it adheres to the same format and encoding (utf-8) as the original.

By adjusting the all.txt file, you can customize the literary foundation on which the model trains, potentially adapting it to various authors, genres, or styles.

### Adjust Training Parameters:
Defaults:
batch_size: 8
context_len: 64
max_iters: 10000
... (Modify as needed)

### Model Training:

From your terminal, aftere activating the environment, just run:

```bash
python train.py
```

### Generating Text:
After training, it generates text of max_new_tokens length from a zero-context. Modify context or length as desired.

### Customization
Batch Size & Context Length: Set batch_size and context_len based on GPU memory.
Model Parameters: Adjust n_embd, n_head, n_layer, and dropout as needed.

## Credits & Inspiration
Inspired by transformer architectures, especially the tutorial "Let's build GPT: from scratch, in code, spelled out" by Andrej Karpathy on YouTube.