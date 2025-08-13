# Meal-Suggestion-Bot
"Three AI-powered recipe generation notebooks using different LLM architectures."
# 🍳 AI-Powered Recipe Generation Models

This repository contains **three Jupyter notebooks** implementing **AI-powered recipe generation** using different Large Language Models (LLMs) and retrieval techniques.  
Each notebook demonstrates how to take user input (ingredients or dish name), search a dataset of Indian recipes, and generate accurate, dataset-based recipe suggestions.

---

## 📜 Table of Contents
- [Overview](#-overview)
- [Notebooks](#-notebooks)
- [Dataset](#-dataset)
- [How It Works](#-how-it-works)
- [Model Comparison](#-model-comparison)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Results](#-results)
- [Future Improvements](#-future-improvements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 📖 Overview
Recipe recommendation systems can often **hallucinate** (invent recipes) when using LLMs directly.  
To solve this, these notebooks combine **information retrieval** with **generative AI** in a Retrieval-Augmented Generation (RAG) pipeline.

We explore **three approaches**:
1. **Deepseek LLM 7B Chat** – Basic RAG implementation.
2. **GPT-2 Meal Suggestion Bot** – Lightweight model with simple retrieval.
3. **Deepseek LLaMA 8B** – Improved prompt engineering for minimal hallucinations.

---

## 📂 Notebooks

| Notebook | Description | Model Used |
|----------|-------------|------------|
| `Deepseek_LLM_7B_Recipe_Generation_Bot.ipynb` | Uses **Deepseek LLM 7B Chat** with FAISS retrieval on recipe dataset. | `deepseek-ai/deepseek-llm-7b-chat` |
| `Meal_Suggestion_Bot.ipynb` | Simple retrieval using SentenceTransformer + GPT-2 for text generation. | `gpt2` |
| `Deepseek_Llama_Recipe_Generation_Bot.ipynb` | Advanced RAG with **DeepSeek LLaMA 8B** and explicit anti-hallucination prompts. | `deepseek-ai/DeepSeek-R1-Distill-Llama-8B` |

---

## 📊 Dataset
We use the **Indian Food Dataset** containing:
- Recipe names
- Ingredients
- Cooking time
- Step-by-step instructions

**Preprocessing**:
- Removed missing values
- Combined name, ingredients, and instructions for retrieval
- Created vector embeddings using `all-MiniLM-L6-v2`

Dataset source (example):  
[Indian Food Dataset on Kaggle](https://www.kaggle.com/datasets/nehaprabhavalkar/indian-food-101) *(replace with actual source if different)*

---

## ⚙ How It Works

1. **User Input**  
   The user types ingredients or a dish name.
   
2. **Retrieval**  
   - The query is converted into embeddings using SentenceTransformer.
   - FAISS or cosine similarity is used to find the most relevant recipes.

3. **Context Building**  
   - Retrieved recipes are compiled into a context block.

4. **Generation**  
   - LLM uses the context to create structured recipe suggestions.
   - In LLaMA version, prompts explicitly forbid hallucinations.

---

## 🏆 Model Comparison

| Rank | Model | Pros | Cons |
|------|-------|------|------|
| 1️⃣ | Deepseek LLaMA 8B | Best accuracy, least hallucination, clear output | Slightly heavier model |
| 2️⃣ | Deepseek LLM 7B | Faster than LLaMA, decent accuracy | Some hallucination |
| 3️⃣ | GPT-2 Bot | Lightweight, simple | Outdated model, weaker language generation |

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/Recipe_Generation_Models.git
cd Recipe_Generation_Models
