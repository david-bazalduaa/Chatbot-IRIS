# Iris Assistant - Enterprise Custom AI Solution (Llama 3)

![Python Badge](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)
![Gradio Badge](https://img.shields.io/badge/Built%20with-Gradio-orange?style=flat-square&logo=gradio)
![Llama 3 Badge](https://img.shields.io/badge/Model-Llama%203-blueviolet?style=flat-square)

This repository hosts Iris Assistant, a specialized conversational interface designed to interact with a fine-tuned Llama 3.2 (3B) model.

The primary objective of this project is to demonstrate a complete pipeline for creating domain-specific Large Language Models (LLMs). While this demonstration model was trained on high-quality public instruction data, the architecture serves as a proof-of-concept for enterprises to securely fine-tune models on proprietary data and inject context in real-time.

---

## Live Demo

Interact with the fine-tuned model via the custom interface hosted on Hugging Face Spaces:

[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face-Open%20Demo-blue?style=for-the-badge)](https://huggingface.co/spaces/DavidBazaldua/iris)

---

## Interface Preview

The application features a minimalist, "glassmorphism" design focused on usability and parameter control.

> **Note:** Replace `screenshot.png` with the actual path to your image in the repository.

![Chatbot Interface]([screenshot.png])

---
## The Development Process

This solution was built following a structured pipeline to optimize a general-purpose model into a responsive assistant.

### 1. Model Selection and Optimization
We utilized the Llama 3.2 3B Instruct architecture as the base. To ensure efficient training without sacrificing performance, we employed the Unsloth library, which allows for faster backpropagation and lower memory usage.

### 2. Dataset and Fine-Tuning
The model was fine-tuned using the mlabonne/FineTome-100k dataset. This large-scale dataset was converted into the standard Conversation format to improve the model's ability to follow complex instructions and maintain coherent dialogue. We utilized QLoRA (Quantized Low-Rank Adaptation) with the following configuration to update specific model weights:
* Rank (r): 16
* LoRA Alpha: 16
* Target Modules: q_proj, k_proj, v_proj, o_proj, gate_proj, up_proj, down_proj

### 3. Quantization and Export
Post-training, the model was merged and exported to GGUF format using llama.cpp. This step ensures the model can be deployed in resource-constrained environments (CPU execution) while maintaining inference speed.

### 4. Interface and Dynamic Context
The frontend allows users to perform Retrieval-Augmented Generation (RAG) manually. By using the "Context" panel on the left, users can inject temporary data (documents, internal wikis, project notes) into the system prompt. This allows the model to answer questions based on information it was not originally trained on, simulating a private enterprise environment.

## Application Features

* Dynamic Context Injection: Real-time integration of user-provided text into the generation loop.
* System Prompt Configuration: Ability to override the base personality and instructions of the assistant.
* Inference Parameters: Granular control over Temperature, Max Tokens, and Top-P sampling.
* Visual Design: Custom CSS implementation for a modern, distraction-free environment.

## Tech Stack

* Base Model: Meta Llama 3.2 3B
* Training Framework: Unsloth (PyTorch, TRL)
* Interface: Gradio
* Deployment Format: GGUF / Transformers

## Installation and Local Usage

Prerequisites: Python 3.10+ and Git.

1. Clone the repository
git clone [INSERT_YOUR_GITHUB_REPO_URL_HERE]

2. Install dependencies
pip install torch transformers gradio

3. Run the application
python app.py

This project was built following a structured pipeline to transform a general-purpose model into a specialized assistant.

### 1. Data Curation and Formatting
The foundation of this project is **private data**. Raw unstructured data (documents, internal wikis, logs) was processed and converted into structured JSON/Text formats suitable for Supervised Fine-Tuning (SFT). This ensures the model learns the specific patterns and knowledge required by the business.

### 2. Fine-Tuning Llama 3
We utilized the **Llama 3** architecture as the base model. Using efficient training techniques (such as LoRA/QLoRA), the model was fine-tuned on the curated dataset. This process updated the model's weights to prioritize the domain-specific information over general internet knowledge.

### 3. Inference Engine Integration
The fine-tuned model (`DavidBazaldua/llama3_finetuned_transformes`) was integrated using the **Hugging Face Transformers** library. The inference pipeline was optimized for CPU execution to demonstrate cost-effective deployment capabilities.

### 4. Dynamic Context Injection (RAG-Lite)
While the model is fine-tuned, businesses often need to provide real-time updates without retraining. The interface includes a **Dynamic Context** system, allowing users to inject temporary data (via the "Context" panel) into the system prompt at runtime, combining the benefits of fine-tuning with Retrieval-Augmented Generation (RAG) principles.

---

## Tech Stack

* **Model Architecture:** Meta Llama 3 (Fine-tuned).
* **Interface:** Gradio (Custom CSS & Layout).
* **Backend:** PyTorch & Transformers.
* **Environment:** Python 3.10+.
