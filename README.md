# Fine-Tuning Qwen2-1.5B for Math Equation Correction Using LoRA

## Overview
This project fine-tunes **Qwen2-1.5B** using **LoRA (Low-Rank Adaptation)** to correct mathematical equations efficiently. The model learns from a dataset of incorrect and corrected equations and is deployed via **Gradio** for interactive testing.

## Features
- **Efficient Fine-Tuning:** Utilizes LoRA to adapt a large-scale transformer model with minimal computational resources.
- **Dataset Integration:** A custom dataset of incorrect and corrected equations.
- **Interactive Demo:** Deployed using **Gradio** for real-time testing.

## Installation
```bash
pip install datasets peft transformers gradio bitsandbytes
```

## Usage
```python
from transformers import AutoModelForCausalLM, AutoTokenizer, TrainingArguments, Trainer
from peft import LoraConfig, get_peft_model
from datasets import Dataset

# Load model and tokenizer
model_name = "Qwen/Qwen2-1.5B"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

# Apply LoRA
lora_config = LoraConfig(r=8, lora_alpha=32, lora_dropout=0.1)
model = get_peft_model(model, lora_config)
```

## Future Plans
- Expand the dataset to include more complex mathematical problems.
- Experiment with different fine-tuning techniques.
- Deploy as an API for seamless integration.

## Contributions
Contributions are welcome! Feel free to open an issue or submit a pull request.

## License
This project is licensed under the MIT License.

---
Let's push the boundaries of **AI-driven equation correction**! 🚀

