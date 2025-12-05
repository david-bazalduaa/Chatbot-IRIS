# Iris Assistant - Enterprise Custom AI Solution (Llama 3)

![Python Badge](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)
![Gradio Badge](https://img.shields.io/badge/Built%20with-Gradio-orange?style=flat-square&logo=gradio)
![Llama 3 Badge](https://img.shields.io/badge/Model-Llama%203-blueviolet?style=flat-square)

This repository hosts **Iris Assistant**, a specialized conversational interface designed to demonstrate the capabilities of **fine-tuning Large Language Models (LLMs) on private, domain-specific data.**

### The Business Value
In the current enterprise landscape, generic models often fail to capture the nuances of internal business operations, proprietary terminology, or specific brand voices.

**Iris Assistant** serves as a proof-of-concept for businesses looking to:
1.  **Secure Proprietary Data:** Create internal LLMs that understand sensitive company data without relying on external, public APIs.
2.  **Enhance Accuracy:** Drastically reduce hallucinations by training the model on a curated dataset of verified company knowledge.
3.  **Automate Domain-Specific Tasks:** Deploy an assistant capable of drafting reports, answering technical queries, or managing customer support with the specific tone and knowledge of the organization.

---

## Live Demo

Interact with the fine-tuned model via the custom interface hosted on Hugging Face Spaces:

[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face-Open%20Demo-blue?style=for-the-badge)]([INSERT_YOUR_HUGGINGFACE_SPACE_URL_HERE])

---

## Interface Preview

The application features a minimalist, "glassmorphism" design focused on usability and parameter control.

> **Note:** Replace `screenshot.png` with the actual path to your image in the repository.

![Chatbot Interface]([screenshot.png])

---

## The Development Process

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
