# Img2Latex: Image-to-LaTeX Converter

A deep learning project focused on converting images of mathematical formulas into structured LaTeX code. This repository explores various encoder-decoder architectures for image-to-sequence tasks, covering both digital and handwritten formulas.



---

## 📖 Project Overview
The goal of this project is to build a robust system capable of translating pixel data into LaTeX strings. I implemented an **Encoder-Decoder** architecture, experimenting with various visual backbones to find the optimal balance between feature extraction and sequence generation.

### Technical Approach
* **Encoder Experiments:** Evaluated multiple architectures including **ResNet-34**, **ResNet-50**, and **Vision Transformers (ViT)**.
* **Decoder:** Utilized a **Transformer-based decoder** to handle long-range dependencies in LaTeX syntax.
* **Training Strategy:** 1. Pre-trained on the base **Img2Latex** digital dataset from Hugging Face.
    2. Fine-tuned on the **Handwritten Img2Latex** dataset to improve generalization for real-world notes.

---

## Dataset
The project utilizes datasets hosted on Hugging Face. These provide a diverse mix of standardized digital formulas and variable handwritten styles.

* **Source:** Use the `load_dataset` method from the Hugging Face `datasets` library to pull the Img2Latex collections.

---

## How to Run

To rerun the code or test the model, follow this sequence:

### 1. Preprocessing
Run the `preprocessing.py` script to handle image resizing and filtering.
```bash
python preprocessing.py
```

### 2. Model Configuration
The different encoder implementations (ResNets and ViT) can be found in the models/ directory. You can toggle between them in the training configuration.

### 3. Training
To start the training or fine-tuning process, execute:

```bash
python train.py
```

### 4. Inference (Web App)
I have built a Streamlit interface for easy testing. Launch it via:

```bash
streamlit run webapp.py
```

## ⚠️ Current Limitations & Challenges
Validation Metrics: Currently, validation is performed through manual inspection of generated LaTeX outputs.

Computational Constraints: Calculating the BLEU score is currently omitted during the training loop as it is computationally expensive given my current hardware resources.

## 🛠️ Repository Structure
preprocessing.py: Logic for image normalization and filtering.

- models/: Contains the various Encoder and Transformer Decoder scripts.
- train.py: The main training and fine-tuning loop.
- webapp.py: Streamlit application for real-time inference.
