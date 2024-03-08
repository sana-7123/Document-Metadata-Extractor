

This Python script showcases the implementation of Named Entity Recognition (NER) using BERT (Bidirectional Encoder Representations from Transformers), a state-of-the-art transformer-based model. The script covers various stages, including dataset loading, text tokenization, model definition, and training with the goal of identifying and classifying entities within a given text.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Explanation](#explanation)


## Installation

1. Clone the repository:

   ```b
   git clone https://github.com/sana-7123/ner-with-bert.git
   ```

2. Navigate to the project directory:

   ```
   cd ner-with-bert
   ```

3. Install the required dependencies:

   ```
   pip install -r requirements.txt
   ```

## Usage

Run the main script to perform Named Entity Recognition using BERT.

```
python ner_with_bert.py
```

Ensure the script is customized with your dataset path, and adjust hyperparameters if necessary.

## Dataset

The script assumes a CSV dataset (`train.csv`) containing text data and corresponding token-level labels for Named Entity Recognition. The dataset structure should include at least the following columns:

- `text`: Represents the input text data.
- `labels`: Provides token-level labels indicating the entities present in the text.

It is imperative to ensure that your dataset contains the required `labels` column with token-level annotations, crucial for training a successful NER model.

## Dependencies

The script relies on two essential libraries:

- **datasets:** This library, provided by Hugging Face, facilitates easy loading and management of datasets.
- **transformers:** Developed by Hugging Face as well, this library includes pre-trained transformer-based models, such as BERT, for various natural language processing tasks.

## Explanation

### 1. Loading the Dataset

The script incorporates the Hugging Face `datasets` library to efficiently load a CSV dataset (`train.csv`). The dataset should contain text data and associated token-level labels, necessary for the supervised training of a NER model.

### 2. Tokenizing the Dataset

Tokenization is a fundamental step in natural language processing tasks. The `BertTokenizerFast` from the `transformers` library is employed to tokenize the input text data. Tokenization involves breaking down the text into smaller units, such as words or subwords, to create a tokenized representation suitable for model input.

### 3. Model Definition

The script defines a BERT-based token classification model (`BertForTokenClassification`) using the `transformers` library. The choice of the number of labels (`num_labels`) is crucial and should align with the specific requirements of the NER task. This model is designed to predict entity labels for each token in the input sequence.

### 4. Training

The training process is configured using the `TrainingArguments` class, which allows the specification of various training parameters. These include output directories for model checkpoints, batch sizes for training and evaluation, training epochs, warm-up steps, and weight decay. The `Trainer` class, also from the `transformers` library, is initialized with the model, training arguments, and tokenized datasets. The model is then trained using the `train()` method, leveraging the power of BERT's contextual embeddings to capture intricate relationships within the input text.

### 5. Evaluation

After training, the script evaluates the model's performance on the evaluation dataset using the `evaluate()` method of the `Trainer`. This step provides valuable insights into the model's ability to correctly identify and classify entities within unseen text.
