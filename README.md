# Distillation & Fine-Tuning Projects Repository

This repository hosts several projects focused on model distillation and fine-tuning. The projects demonstrate techniques from training data generation to the distillation of larger teacher models into more compact, task-specific models. Each project is built around specific use cases, including dealership lead management, IT support, and more.

## Overview

This repository is a collection of projects that showcase the process of:

- **Extracting and processing conversation logs:** Generating structured training data from raw logs.
- **Distillation:** Compressing a larger teacher model into smaller, fine-tuned models for specific tasks.
- **Fine-Tuning:** Applying task-specific adjustments to the distilled models to enhance their performance in real-world applications such as customer support (for dealerships, IT support, etc.).

These projects serve as examples of how to leverage model distillation techniques to optimize machine learning models for efficiency while maintaining high performance.

## Projects

The repository currently includes multiple projects, including:

- **Dealership Lead Distillation:**  
  A project that processes dealership conversation logs, generates training data with embedded metadata (e.g., `test: A001`), and distills a teacher model into a compact 4.1-mini model tailored for customer support in automotive contexts.

- **IT Support Distillation:**  
  A project that focuses on IT support interactions, following similar principles of conversation history extraction, training data generation, and model distillation/fine-tuning to create a responsive, domain-specific assistant.

Additional projects can be added following the same structure to further showcase the techniques of disaggregation, distillation, and fine-tuning across various domains.

Each project folder contains its own set of scripts, notebooks, or configuration files specific to that task.

## Setup and Requirements

### Prerequisites

- **Python 3.8+** is recommended.
- **OpenAI API Key:** Required for model calls and fine-tuning. Ensure this is set in your environment (`OPENAI_API_KEY`).
- **Dependencies:** Install necessary packages by running:

  ```bash
  pip install -r requirements.txt
  ```

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Create and activate a Python virtual environment:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set your OpenAI API key:**

   ```bash
   export OPENAI_API_KEY=your_api_key_here
   ```

## Training Data Generation & Distillation Process

For each project, the workflow typically involves the following steps:

- **Conversation Log Processing:**  
  Extract and order conversation stages, format the training context, and identify target messages.

- **Training Data Generation:**  
  Build prompts by combining conversation context with specific metadata (e.g., `test: A001`).

- **Model Distillation:**  
  Use the prepared training dataset to distill a larger teacher model (e.g., `o3-mini-2025-01-31`) into a smaller, task-specific model (e.g., 4.1-mini).


## Testing the Fine-Tuned Models

Each project provides its own testing framework to evaluate the performance of the fine-tuned model. Testing usually involves:

- Simulating realistic conversation scenarios.
- Sending conversation history to the model.
- Displaying model responses for analysis.

## License

This project is licensed under the [MIT License](LICENSE).

