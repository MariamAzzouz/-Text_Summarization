# Text Summarization System

This project focuses on developing an automated text summarization system leveraging state-of-the-art natural language processing (NLP) techniques. The system utilizes transformer-based models to generate concise and meaningful summaries from textual content, including articles and PDFs.

## Table of Contents
1. [Overview](#overview)
2. [Techniques and Models Used](#techniques-and-models-used)
   - [Transformer Architecture](#1-transformer-architecture)
   - [Dataset](#2-dataset)
   - [Preprocessing](#3-preprocessing)
   - [Fine-Tuning](#4-fine-tuning)
   - [Summarization Process](#5-summarization-process)
   - [Hardware Optimization](#6-hardware-optimization)
3. [Functionalities](#functionalities)

---

## Overview
The goal of this project is to:
- Fine-tune a summarization model using the `cnn_dailymail` dataset.
- Generate summaries for articles, paragraphs, or PDFs with high efficiency and accuracy.

---

## Techniques and Models Used

### 1. Transformer Architecture
- **Model:** `facebook/bart-large-cnn`
  - A fine-tuned version of BART for summarization tasks.
  - **Functionality:** Processes long text inputs and generates accurate and coherent summaries.

### 2. Dataset
- **Name:** `cnn_dailymail`
- **Version:** 3.0.0
- **Purpose:** Used to train and fine-tune the summarization model with real-world news articles and summaries.

### 3. Preprocessing
- **Input Truncation:** Articles truncated to a maximum of 1024 tokens.
- **Label Preparation:** Highlights tokenized to a maximum of 128 tokens to align with the model's output.

### 4. Fine-Tuning
- **Framework:** Hugging Face's Transformers library.
- **Trainer API:**
  - Configured with parameters like batch size, learning rate, and evaluation strategy.
  - Uses `DataCollatorForSeq2Seq` to handle dynamic padding during training.
- **Objective:** Fine-tune the BART model for domain-specific summarization.

### 5. Summarization Process
- **Inference Pipeline:**
  - Input text is tokenized and fed into the model.
  - Beam search is used to generate summaries, ensuring quality and coherence.
- **PDF Summarization:** 
  - Text extracted from PDFs using `PyPDF2`.
  - Extracted paragraphs are summarized individually.

### 6. Hardware Optimization
- Utilizes GPU (if available) for accelerated model training and inference.

---

## Functionalities
1. **Training and Fine-Tuning:**
   - Adapts the summarization model to specific domains using the `cnn_dailymail` dataset.
2. **Text Summarization:**
   - Generates summaries for articles, paragraphs, or documents with adjustable parameters.
3. **PDF Summarization:**
   - Integrates text extraction and summarization for efficient document processing.


