# Llama-3.2-11B-Vision-Instruct on Google Colab

This repository provides a Colab-ready implementation to run the `meta-llama/Llama-3.2-11B-Vision-Instruct` model for visual instruction tasks such as extracting structured text and flow diagrams from images.

## Overview

The `Llama-3.2-11B-Vision-Instruct` model is part of Meta's Llama 3.2 series and is fine-tuned for multimodal instruction-following tasks. This notebook enables you to interact with this model using visual inputs (e.g., scanned documents, flowcharts, etc.) and text prompts.

## Features

- Uses **BitsAndBytes** for efficient 4-bit quantization.
- Processes and analyzes images with layout-structured prompts.
- Compatible with **Google Colab GPU runtime**.
- Easily extendable for other visual-language tasks.

## Requirements

- Google Colab with GPU enabled.
- A Hugging Face account and access token with permission to use Llama models.
- A sample image file located at `/content/images/page_4.png`.

## Setup Instructions

1. **Install Dependencies**  
   The script installs `bitsandbytes` and `accelerate` to enable 4-bit quantization.

2. **Authenticate with Hugging Face**  
   Use your Hugging Face token to authenticate via `huggingface_hub.login`.

3. **Model Loading**  
   The model `meta-llama/Llama-3.2-11B-Vision-Instruct` is loaded using the `transformers` library with 4-bit quantization enabled for efficient inference.

4. **Image Processing**  
   A sample image is loaded using `PIL.Image`.

5. **Running Inference**  
   A utility function `chat_with_mllm` is defined to:
   - Apply the chat template with both image and text prompt.
   - Generate a response using the model.
   - Maintain context with a message history.

6. **Prompt Used**
   The default prompt extracts structured text and flow diagram steps from an image, suitable for further downstream processing by LLMs.

## Use Case Example

The current setup is ideal for:
- Document parsing and layout-aware OCR tasks.
- Extracting structured content from flowcharts.
- Feeding extracted information into downstream LLMs for further analysis or QA.

## Notes

- Ensure your image path is valid and points to a properly formatted image file.
- For best results, use high-resolution images with clear text and diagrams.
- Hugging Face access to Meta's Llama models may require joining their licensing program.

## License

This project is provided for educational and research purposes. Usage of the model is subject to Meta's Llama license and Hugging Face terms of service.
