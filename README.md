# 🩺 MedBot - NLP-Based Medical Assistant Chatbot

MedBot is an NLP-powered symptom analysis chatbot that predicts potential diseases based on user-reported symptoms. Built using a variety of NLP models ranging from Bag of Words to Fine-Tuned BERT, MedBot serves as a proof-of-concept for how Natural Language Processing can improve preliminary diagnostics in healthcare.

---

## 🚑 Problem Statement

Traditional symptom checkers rely on rule-based systems that often fail with nuanced or ambiguous inputs. MedBot tackles this by applying NLP to understand free-text symptoms and match them to possible diseases—improving accessibility, efficiency, and accuracy in preliminary diagnosis.

---

## 🎯 Objectives

- **Compare NLP Models**: Evaluate BoW, TF-IDF, Word2Vec, FastText, BERT, and Fine-Tuned BERT.
- **Develop MedBot**: Create a chatbot that takes natural language symptoms and predicts possible diseases.
- **Assess Interpretability and Efficiency**: Focus on transparency and real-world viability.

---

## 💡 Motivation

- **Accessibility**: Reduces unnecessary hospital visits by offering early diagnosis.
- **Scalability**: Supports healthcare professionals in triaging patients.
- **Innovation**: Explores cutting-edge NLP techniques in the medical domain.

---

## 🗂️ Dataset

- **Source**: `medical_symptoms_100.csv`
- **Entries**: 100
- **Fields**:
  - `Disease`: e.g., *Migraine*, *Influenza*
  - `Symptoms`: e.g., `["headache", "nausea"]`
  - `Description`: Brief description of the disease

### 🔧 Preprocessing

- Tokenization of symptom text
- Label encoding of disease names
- Vector embedding generation (for Word2Vec, FastText, etc.)

---

## 🧠 NLP Models Used

| Model             | Description |
|------------------|-------------|
| **BoW**           | Basic word frequency model |
| **TF-IDF**        | Weighted term frequency model |
| **Word2Vec**      | Semantic vector representation |
| **FastText**      | Subword-level embeddings |
| **BERT**          | Pretrained transformer for contextual embeddings |
| **Fine-Tuned BERT** | BERT adapted to our symptom dataset |

---

## 🏗️ Model Architectures

- **BoW/TF-IDF**: Cosine similarity to match input symptoms with known disease vectors.
- **Word2Vec/FastText**: Sentence embeddings + cosine similarity.
- **BERT**: Fine-tuned with a classification head (`Dropout + Linear`) using:
  - Optimizer: `AdamW`
  - Loss: `CrossEntropy`
  - Epochs: `7`
  - Batch size: `2`
  - Learning rate: `3e-5`

---

## 📊 Evaluation Metrics

- **Accuracy**
- **Interpretability** (model explainability)
- **Computational Efficiency**

---

## ✅ Results

| Model             | Accuracy      | Strengths                             | Limitations                               |
|------------------|---------------|---------------------------------------|-------------------------------------------|
| **BoW**           | Moderate      | Fast, Simple                          | No context, struggles with ambiguity      |
| **TF-IDF**        | Moderate      | Highlights rare terms                 | No semantic understanding                 |
| **Word2Vec**      | High          | Semantic understanding                | Requires large corpus                     |
| **FastText**      | High          | Handles misspellings, rare terms      | Overfits on subwords                      |
| **BERT**          | Highest       | Deep context, transformer-based       | High compute requirements                 |
| **Fine-Tuned BERT** | **90.62% (Migraine)** | Excellent with nuanced inputs   | Needs labeled medical data                |

---

## 🔍 Key Findings

- **Fine-Tuned BERT** performed best with 90.62% accuracy.
- **FastText** was robust to typos and rare word forms.
- **BoW/TF-IDF** offered solid baselines, but lacked semantic depth.

---

## ⚠️ Challenges

- **Ambiguity** in user input (e.g., "feeling off").
- **Synonymy** and **Polysemy** (e.g., "high temperature" vs. "fever").
- **Small Dataset** limiting generalization.
- **Resource-Intensive** models like BERT require GPUs and time.

---

## 🔮 Future Work

- 📈 **Expand Dataset**: More diseases, more symptoms.
- 🔀 **Hybrid Models**: Combine BERT’s depth with FastText’s robustness.
- 🌐 **Multilingual Support**: Accept symptom descriptions in multiple languages.
- 📱 **User Interface**: Build a responsive web/mobile chatbot.
- 🧪 **Clinical Validation**: Compare results with real diagnoses.

---
