# Iris Assistant - Custom AI Chatbot (Llama 3)

![Python Badge](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)
![Gradio Badge](https://img.shields.io/badge/Built%20with-Gradio-orange?style=flat-square&logo=gradio)
![HF Transformers Badge](https://img.shields.io/badge/Transformers-yellow?style=flat-square)

This repository contains a modern, custom chat interface built with **Gradio**, designed to interact with a fine-tuned **Llama 3** model.

The primary objective of this application is to allow users to temporarily "train" the assistant by providing **custom context** and defining its behavior via a *System Prompt*, all within a clean and minimalist graphical interface.

---

## Live Demo

Try the application running on Hugging Face Spaces:

[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face-Open%20Demo-blue?style=for-the-badge)]([INSERT_YOUR_HUGGINGFACE_SPACE_URL_HERE])

---

## Screenshot

A preview of the custom user interface:

> **Note:** Replace `screenshot.png` with the actual path to your image in the repository.

![Chatbot Interface]([screenshot.png])

---

## Key Features

* **Base Model:** Utilizes `DavidBazaldua/llama3_finetuned_transformes`, an optimized Llama 3 model.
* **Dynamic Context (RAG-lite):** Allows users to input documents, notes, or data into the configuration panel for the model to use as immediate reference.
* **Customizable System Prompt:** Define the exact personality and instructions for the assistant.
* **Parameter Control:** Real-time adjustment of creativity (Temperature), response length (Max Tokens), and sampling (Top-P).
* **UI/UX Design:** Clean minimalist interface, forced light mode, and an optimized chat area with an internal scrollbar.
* **Optimization:** Configured for efficient CPU execution.

---

## Installation and Local Usage

Instructions to run the application in a local environment.

### Prerequisites

* Python 3.10 or higher.
* Git.

### Steps

1.  **Clone the repository:**
    ```bash
    git clone [INSERT_YOUR_GITHUB_REPO_URL_HERE]
    cd [REPO_DIRECTORY_NAME]
    ```

2.  **Create a virtual environment:**
    ```bash
    python -m venv venv
    # On Windows:
    .\venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install torch transformers gradio
    ```

4.  **Run the application:**
    ```bash
    python app.py
    ```

---

## Tech Stack

* [Gradio](https://www.gradio.app/) - Interactive web interface.
* [Hugging Face Transformers](https://huggingface.co/docs/transformers/index) - Language model inference.
* [PyTorch](https://pytorch.org/) - Deep learning framework.
