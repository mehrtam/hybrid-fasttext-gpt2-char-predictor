# Hybrid Next-Character Prediction (FastText + GPT-2)

This project implements a hybrid character-level next-character predictor using **FastText** and **GPT-2**. It combines the **speed of FastText** with the **contextual understanding of GPT-2**, dynamically switching between them based on prediction confidence. Designed for character-level language modeling and real-time interactive input.

---

##  Features

- Trains a **character-level FastText classifier** on Shakespeare and Wikipedia data.
- Uses **confidence thresholding** to switch from FastText to GPT-2 when needed.
- **Interactive real-time typing** loop for next-character prediction.
- Evaluates using **Top-1 / Top-3 accuracy** and **average latency**.
- Saves models for reuse: `FastText (.ftz)` and `GPT-2` from Hugging Face.

---

##  Model Pipeline

### 1. Data Preprocessing
- Downloads and cleans **Shakespeare** and **Wikipedia** datasets.
- Converts text into labeled sequences for **FastText** training.

### 2. FastText Training
- Trains a **supervised FastText model** on the generated character sequences.
- Optionally uses **quantization** for faster inference.

### 3. Hybrid Prediction
- Uses **FastText** for initial prediction.
- If FastText confidence is below a threshold, it **falls back to GPT-2**.

### 4. Evaluation
- Calculates **Top-1 and Top-3 accuracy**.
- Measures **average prediction latency** across test samples.

### 5. Interactive Typing
- User types any sentence.
- The model predicts the **next character in real time** with explanation.

---

## 📦 Requirements

Install all required libraries using:

```bash
pip install fasttext torch transformers datasets
