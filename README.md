# LLM Assignment: Investigating the Internal State of Large Language Models  

This project delves into the intricate workings of Large Language Models (LLMs) by reproducing the paper **"The Internal State of an LLM Knows When It’s Lying"** by Amos Azaria and Tom Mitchell. This repository also includes original enhancements, detailed error analysis, and experiments involving perturbations to assess model behavior under varied inputs, demonstrating a comprehensive understanding of LLMs and their behavior.  

---

## Project Overview  
This project explores the ability of LLMs to identify when they are providing false information. By reproducing the research paper and adding original contributions, we investigate how the internal states of LLMs correlate with their confidence in truthfulness, shedding light on their interpretability. Additionally, we induced input perturbations to evaluate the robustness and adaptability of the model under altered conditions.  

---

## Key Features  
- **Reproduction of Research:** Faithfully implemented experiments based on the referenced paper.  
- **Enhanced Insights:** Introduced modifications and additional experiments to build upon the original findings.  
- **Error Analysis:** Conducted detailed evaluation of errors to understand the limitations and scope of the model.  
- **Input Perturbation Experiments:** Evaluated how model performance is impacted by minor changes in input, shedding light on sensitivity and robustness.  

---

## Technologies Used  
- **Python**: Core programming language for experiments.  
- **PyTorch**: Framework for implementing and fine-tuning LLMs.  
- **Hugging Face Transformers**: For pre-trained model integration and customization.  
- **Jupyter Notebooks**: Used for data analysis and visualization.  

---

## Getting Started  
To replicate the experiments in this repository:  
1. Clone the repository:  
   ```bash
   git clone https://github.com/SrikithaKandra/InternalStateofLLM.git
   cd LLM_Assignment

## Usage

### 1. **Embedding Generation**
To extract embeddings for the last token at specific layers of a selected model:
- Use either `GenerateEmbeddings.py` or `LLaMa_generate_embeddings.py`.
- Configure parameters via `config.json` or command-line arguments.
- The embeddings are saved as CSV files for further use.
- Ensure labeled datasets are used for training purposes.

### 2. **Probe Training**
To train probes on the generated embeddings:
- Run `TrainProbes.py`, which allows parameter customization via `config.json` or command-line options.
- The probes are tested on a separate evaluation dataset.
- The best-performing probes are saved based on accuracy metrics.

### 3. **Applying Probes to New Datasets**
To use trained probes on new datasets:
- Execute `Generate_Embeddings.py` on the new dataset, ensuring consistency in model, layer, and other parameters with the training setup.
- Predictions and average predictions are saved for further analysis.

### 4. **Model Comparisons**
The performance of the **SAPLMA** model was benchmarked against:
- **BERT** (evaluated using `Bert.py`).
- **3-shot and 5-shot learning models** (evaluated using `train_few-shot.py`).

### 5. **Robustness Evaluation**
To evaluate model robustness:
- Use `perturbations.py` to generate perturbed datasets from original ones.
- Perturbations include:
  - Adding fillers to sentences.
  - Introducing typos.
  - Altering word order.
- These tests assess the models' ability to handle input variations and maintain performance.
