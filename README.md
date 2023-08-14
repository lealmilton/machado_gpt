# Bigram Language Model trained on Machado de Assis's full work
## Overview
Welcome to this repository, my working playground for exploring transformer architectures during my undergraduate thesis. Transformer architectures, with their ability to handle sequential data in various domains, have gained significant traction in the field of deep learning. Their applications span from language modeling, machine translation, to even image classification tasks.

Currently, I am training a custom bigram language model, inspired by the transformative transformer architectures and guided by the insights provided in Andrej Karpathy's video tutorial "Let's build GPT: from scratch, in code, spelled out." The model's primary aim is to understand and reproduce the unique writing style of Machado de Assis, a renowned Brazilian writer, who wrote in Portuguese but had work translated into dozens of languages. In this project we will use Machado's work in Portuguese. 

### Initial Results
The first foray into training this model was using a CPU. Admittedly, the results were less than stellar. Here's an example of text generated on 14/08:

```
Sample:

ag pqi,litiandiuera anrado dasostbdela maSa. demant.má cpCelanqro áo, o pa oqicteitora s dou dve ábO, Qo.s dam  c-io edomoo,.;o 
su than mr e aooamesto, as uobttoc erão dia a ca as Oa vorras  que omoa má orTiio $r litzã, áreocêr 7cntu ha aMmbepae o e dG.mo 
cítguão a, Ha to peua
iá Piaruquce
elolatet$ Ûa g dto óque preqo ào, e;o.b sameio+e tio puãaca

gca eçhe sieso
 ool de o, eopeammoand? dmacosma
 m5anoitá deemT addaEspOte,tiubo e,
 vÉe qarro.
ia a dar doosoéj ols
 (ncoré m e putoa ggu? ntoos. om , as t lea
```

While these initial generations may appear disjointed and nonsensical, they mark the beginning of this exploration. I believe in the potential of this model, and my journey will involve refining and improving it.

### Moving Forward
I plan on experimenting with GPUs to accelerate the training process and hope to enhance the model's performance significantly. With the power of parallel processing that GPUs offer, I expect to see more coherent text generations and faster convergence.

#### Timeline of Generations
14/08: (as shown above)
Future dates will be added as the model is trained and refined further.
Each update in this timeline will serve as a testament to the advancements made, and I hope to witness the transformative power of deep learning as this project evolves.

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