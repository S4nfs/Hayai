# Hayai
早い (hayai) means fast in Japanese

## Overview

Building and training models is complex-data collection, cleaning, formatting, model choice, and training logic all add friction, even in ideal conditions. This project experiments with a streamlined training workflow aimed at producing strong, task-focused models with minimal manual effort. The objective is to reduce overhead so you can move quickly from concept to a fully trained, usable model.

**Provide a clear task description, and the system will automatically create training data, format it correctly, and fine-tune either a LLaMA 3 or GPT-5 model.**

**In short:** *Describe the task → auto-generate datasets → fine-tune the model.*

## Objective
Solving problems for millions of users through innovation, rather than building solely for the corporate world.

## Features

- **Automatic Dataset Creation**  
  Uses Claude 4 or GPT-5 to generate diverse prompt–response pairs tailored to your use case.

- **System Prompt Design**  
  Automatically produces an optimized system message aligned with the task.

- **End-to-End Fine-Tuning**  
  Handles dataset splitting, model training, and preparation for inference without manual setup.

## Setup

1. Open the notebook in **Google Colab** or run it locally via **Jupyter**:  
   https://colab.research.google.com/drive/[redacted]?usp=sharing

2. If using Colab, enable the most powerful GPU/TPU available  
   *(Runtime → Change runtime type)*.

3. Insert your OpenAI API key in:  
   `openai.api_key = "YOUR KEY HERE"`

## How to Use

1. Write your `prompt`, clearly defining the behavior you want from the model.  
   Tune:
   - **temperature** (higher = more creative, lower = more exact)
   - **number_of_examples** (100 is a solid baseline)

   Example:
   ```python
   prompt = "A model that optimizes autonomous vehicle routing and driving behavior to minimize energy consumption and reduce emissions at population scale."
   temperature = 0.4
   number_of_examples = 100
   ```

2. Run all the notebook cells  
   *(If you are using the LLaMA 3 notebook, stop once you reach **“Merge the model and store in Google Drive”**.)*

   ⏳ Execution time can range from **10 minutes to several hours**, depending on the number of generated examples and available compute.

3. Test the trained model  
   - Use **Run Inference** in the LLaMA 3 notebook  
   - Or use **Let’s try it out!** in the GPT-5 notebook  

   For LLaMA models, you can save and reload weights directly from Google Drive.  
   For GPT-5, the fine-tuned model becomes available through the OpenAI API and Playground.

## Epilogue 

Ideas for extending or improving the project:
- Optimize example generation to reduce cost and latency
- Add more prompt templates to increase dataset diversity
- Prune highly similar samples to improve generalization
- Use GPT-5 to auto-select hyperparameters or even the target model
- Train multiple variants and automatically select the best-performing one

## License

This project will be released under the **proprietory License** 
