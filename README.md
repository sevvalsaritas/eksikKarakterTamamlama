# 🔤 Missing Character Completion in Turkish with RNN, LSTM and GRU

This project focuses on **missing character completion in Turkish text** using recurrent neural network architectures.  
The main goal is to reconstruct corrupted sentences where some characters are replaced with `_`.

Example:

- **Input:** `_u oy_nculara d_ b_ze d_ g_vensinler`
- **Output:** `Bu oyunculara da bize de güvensinler`

---

## 📌 Project Objective

In this study, Turkish sentences are artificially corrupted by masking some characters with `_`, and deep learning models are trained to recover the original text.

The following architectures are explored:

- RNN
- LSTM
- GRU
- BiLSTM / BiGRU (improved versions)

---

## 🗂 Dataset

Dataset source: **GEC-Turk / BOUN dataset**

This dataset contains Turkish sentences and their corrected forms.  
For this project, the clean target sentences are used to generate synthetic corrupted inputs for the missing character completion task.

### Preprocessing steps

- duplicate sentence removal
- text normalization
- removing or simplifying noisy characters
- splitting very long sentences into chunks of up to **10 words**
- generating corrupted input sentences by replacing some characters with `_`

---

## ⚙️ Methodology

The problem is modeled as a **character-level sequence prediction task**.

### Workflow

1. Read clean Turkish sentences
2. Normalize and clean the text
3. Remove duplicate lines
4. Split long sentences into shorter segments
5. Generate corrupted versions by masking characters
6. Build character vocabulary
7. Train recurrent neural network models
8. Evaluate generated outputs on sample inputs

---

## 🧠 Model Architecture

The model consists of:

- **Embedding layer**
- **Recurrent layer**  
  - RNN / LSTM / GRU
  - optionally bidirectional versions
- **Linear layer** for character prediction

The task is performed at the **character level**, meaning each input character corresponds to one output character.

---

## 🛠 Technologies Used

- Python
- PyTorch
- Google Colab
- Git / GitHub

---

## 🚀 Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/sevvalsaritas/eksikKarakterTamamlama.git
