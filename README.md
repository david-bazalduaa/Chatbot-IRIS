# Iris Assistant - Custom AI Chatbot (Llama 3)

![Python Badge](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)
![Gradio Badge](https://img.shields.io/badge/Built%20with-Gradio-orange?style=flat-square&logo=gradio)
![HF Transformers Badge](https://img.shields.io/badge/Transformers-yellow?style=flat-square)

Este repositorio contiene una interfaz de chat moderna y personalizada construida con **Gradio**, diseñada para interactuar con un modelo **Llama 3** ajustado (fine-tuned).

El objetivo principal de esta aplicación es permitir a los usuarios entrenar temporalmente al asistente proporcionando **contexto personalizado** y definiendo su comportamiento a través de un *System Prompt*, todo dentro de una interfaz gráfica limpia y minimalista.

---

## Demo en Vivo

Prueba la aplicación funcionando en Hugging Face Spaces:

[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face-Open%20Demo-blue?style=for-the-badge)]([PON_AQUI_LA_URL_DE_TU_ESPACIO_DE_HUGGINGFACE])

---

## Captura de Pantalla

Vista previa de la interfaz de usuario personalizada:

> **Nota:** Reemplaza `screenshot.png` con la ruta real de tu imagen en el repositorio.

![Interfaz del Chatbot]([screenshot.png])

---

## Características Principales

* **Modelo Base:** Utiliza `DavidBazaldua/llama3_finetuned_transformes`, un modelo Llama 3 optimizado.
* **Contexto Dinámico (RAG-lite):** Permite ingresar documentos, notas o datos en el panel de configuración para que el modelo los use como referencia inmediata.
* **System Prompt Personalizable:** Define la personalidad y las instrucciones exactas del asistente.
* **Control de Parámetros:** Ajuste de creatividad (Temperature), longitud de respuesta (Max Tokens) y muestreo (Top-P) en tiempo real.
* **Diseño UI/UX:** Interfaz limpia estilo minimalista, modo claro forzado y área de chat optimizada con barra de desplazamiento interna.
* **Optimización:** Configurado para ejecución eficiente en CPU.

---

## Instalación y Uso Local

Instrucciones para ejecutar la aplicación en un entorno local.

### Requisitos Previos

* Python 3.10 o superior.
* Git.

### Pasos

1.  **Clonar el repositorio:**
    ```bash
    git clone [URL_DE_TU_REPO_DE_GITHUB_AQUI]
    cd [NOMBRE_DE_LA_CARPETA_DEL_REPO]
    ```

2.  **Crear un entorno virtual:**
    ```bash
    python -m venv venv
    # En Windows:
    .\venv\Scripts\activate
    # En macOS/Linux:
    source venv/bin/activate
    ```

3.  **Instalar dependencias:**
    ```bash
    pip install torch transformers gradio
    ```

4.  **Ejecutar la aplicación:**
    ```bash
    python app.py
    ```

---

## Tecnologías Utilizadas

* [Gradio](https://www.gradio.app/) - Interfaz web interactiva.
* [Hugging Face Transformers](https://huggingface.co/docs/transformers/index) - Inferencia del modelo de lenguaje.
* [PyTorch](https://pytorch.org/) - Framework de aprendizaje profundo.
