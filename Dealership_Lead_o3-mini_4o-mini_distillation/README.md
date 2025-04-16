# Dealership Support Agent – O3-Mini to 4o-Mini Distillation

This repository contains code and configuration files for generating training data from dealership conversation logs and distilling a teacher model (o3-mini) into a fine-tuned, compact 4.1-mini model. The system is built to assist dealerships by providing a conversational AI that can help answer customer inquiries, handle appointment scheduling, and provide vehicle information.


## Overview

This project demonstrates a complete process, from ingesting conversation logs and metadata to training a refined conversational model for a dealership support context. The key components include:

- Extracting and formatting conversation histories from dealership logs.
- Generating training data by sampling conversation stages.
- Distilling a larger teacher model into a compact 4.1-mini model.
- Testing the fine-tuned model using sample conversation scenarios.

## Features

- **Training Data Extraction:** Extracts conversation history stages and formats them into a context string.
- **Randomized Stage Selection:** Selects a random complete conversation stage (excluding the final stage) to serve as the target training example.
- **Teacher Model Integration:** Uses a pre-trained teacher model (`o3-mini-2025-01-31`) as a reference during distillation.
- **Metadata Handling:** Embeds metadata in the training dataset with a key-value pair (`test`: `A001`).
- **Distillation Process:** Distills the teacher model into a compact 4.1-mini model to optimize performance while retaining essential conversational capabilities.
- **Testing Framework:** Provides a methodology for testing the fine-tuned model using predefined conversation histories.


## Setup and Requirements

### Prerequisites

- **Python:** Version 3.8 or higher is recommended.
- **OpenAI API Key:** Make sure to set your OpenAI API key in the environment variable `OPENAI_API_KEY`.
- **Dependencies:** Install the required packages from `requirements.txt`.

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/Dealership_Lead_o3-mini_4o-mini_distillation.git
   cd Dealership_Lead_o3-mini_4o-mini_distillation
   ```

2. **Set up the Python environment:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Configure the OpenAI API Key:**

   Ensure the API key is available in your environment:

   ```bash
   export OPENAI_API_KEY=your_api_key_here
   ```

## Training Data Generation

- Parsing conversation logs and ordering them by stage.
- Randomly selecting a complete conversation stage (except the last stage) to act as the training example.
- Building a conversation context from previous stages to append to the selected stage's assistant message.
- Formatting the conversation history and the target user message, which is then used as input to the teacher model during the fine-tuning process.

This process is illustrated with code that orders the conversation stages, selects a stage, and builds a formatted prompt message.

## Fine-Tuning Process

The fine-tuning process involves two main steps:

1. **Training Data Preparation:**  
   The OpenAI Dashboard is used to create a training dataset from our logs. In this process, the logs are appended with metadata that includes a key `test` and the value `A001`.  
   
   After preparing the training data, the teacher model (`o3-mini-2025-01-31`) is used as a base for the following step.

2. **Model Distillation:**  
   Using the training data, we distill a more compact 4.1-mini model. This step compresses the original model while maintaining its performance in handling customer support interactions.  


## Testing the Fine-Tuned Model

The notebook includes a testing script to evaluate the performance of the fine-tuned model. The test conversation history replicates a typical dealership interaction scenario:

- Initial greetings.
- Inquiries related to vehicle purchases.
- Appointment scheduling requests.

The scripts are designed to showcase the end-to-end flow of conversation data processing, fine-tuning a model using distilled knowledge, and validating its performance in real-world dealership interactions.

## License

This project is licensed under the [MIT License](LICENSE).
