# Part-of-Speech (POS) Tagging using Hidden Markov Model (HMM) and Viterbi Algorithm

This repository contains the implementation of a **Part-of-Speech (POS) tagging system** using a **Hidden Markov Model (HMM)** and the **Viterbi Algorithm**. The project was developed as part of the NLP course at IIIT Bangalore.

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Preprocessing](#preprocessing)
4. [Model Implementation](#model-implementation)
5. [Evaluation](#evaluation)
6. [How to Run the Code](#how-to-run-the-code)

## Introduction
The goal of this project is to develop a POS tagging system that accurately assigns POS tags to words in sentences using the Viterbi Algorithm. The model is trained on a dataset of sentences where each word is paired with its corresponding POS tag. The system learns transition and emission probabilities from the dataset and uses them to predict POS tags for unseen sentences.

## Dataset
The dataset consists of sentences where each word is labeled with its corresponding POS tag. The dataset is split into training and testing sets. Key insights from the dataset include:
- Most sentences are short, with a peak around 10-25 words.
- The most frequent POS tags are **NOUN**, **VERB**, and **ADP**.
- There is a significant overlap between the training and testing datasets, with 44.51% common rows.

## Preprocessing
The following preprocessing steps were applied to the dataset:
1. **Text Cleaning**: 
   - Converted text to lowercase.
   - Removed URLs and non-word characters.
   - Applied lemmatization to reduce words to their base forms.
2. **Handling Rare Words**: 
   - Used smoothing techniques to handle rare POS tags.
   - Augmented the lexicon to better capture infrequent words.

## Model Implementation
The POS tagging model is implemented using a **Hidden Markov Model (HMM)** with the **Viterbi Algorithm**. Key components of the model include:
- **Transition Probabilities**: Calculated using Laplace smoothing to handle sparse data.
- **Emission Probabilities**: Computed with smoothing to avoid zero probabilities for unseen words.
- **Initial Probabilities**: Determined using the frequency of tags at the start of sentences.

The Viterbi Algorithm is enhanced with:
- **Lexicon-based Heuristic**: Assigns high probability to known words based on a predefined lexicon.
- **Handling Unknown Words**: Uses a smoothing factor to handle words not seen during training.

## Evaluation
The model achieved an overall accuracy of **89.0%**. Key evaluation metrics include:
- **Precision**: 82% (macro average)
- **Recall**: 65% (macro average)
- **F1-Score**: 67% (macro average)

The model performs well on high-frequency tags like **NOUN** and **VERB** but struggles with rare tags like **PROPN** and **SCONJ**.

## How to Run the Code
Follow these steps to run the code:

### Prerequisites
- Python 3.x
- Required Python libraries: `numpy`, `pandas`, `nltk`, `sklearn`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/pos-tagging-hmm.git
   cd pos-tagging-hmm
   ```
2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
    ```
### Running the Code
```bash
python main.py
```
