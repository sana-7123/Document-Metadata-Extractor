# Document Metadata Extractor

This repository contains a Python-based project designed to extract specific metadata from documents, regardless of their format (docx or scanned images). The system leverages Named Entity Recognition (NER) with spaCy for text documents and OCR with Tesseract for scanned images. The extracted metadata includes Agreement Value, Agreement Start Date, Agreement End Date, Renewal Notice (Days), Party One, and Party Two.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Data Preparation](#data-preparation)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Contributing](#contributing)
- [License](#license)

## Installation

Ensure you have Python 3.6 or higher installed. Then, install the required libraries:

```bash
pip install spacy transformers pytesseract opencv-python-headless
```

Download the English model for spaCy:

```bash
python -m spacy download en_core_web_sm
```

## Usage

1. **Preprocess Data**: Run the `preprocess_data` function to extract text from your documents. This function supports both `.docx` and `.png` files.

2. **Train the Model**: Use the provided script to train the NER model on your dataset. Ensure you have a labeled dataset ready for training.

3. **Evaluate the Model**: After training, evaluate the model's performance on a test set to ensure it meets your requirements.

## Data Preparation

The `preprocess_data` function is designed to handle both `.docx` and `.png` files. For `.docx` files, it extracts text using the `python-docx` library. For `.png` files, it uses OCR with Tesseract to convert images to text.

## Model Training

The model is trained using spaCy's NER capabilities. You'll need a labeled dataset for training. The training script demonstrates how to add labels to the NER component and train the model on your dataset.

## Evaluation

The evaluation script calculates the recall for each field as per the criteria provided. It compares the model's predictions against the true values in the test set.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
