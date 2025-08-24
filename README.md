# Persian Question Answering (ParsQA) Project

**Author:** Mehdy Mokhtari
**Internship Project – Roshan Company**
**Dataset:** [PersianQA (PQuAD)](https://github.com/sajjjadayobi/PersianQA)

---

## Overview

This repository implements a **Persian Machine Reading Comprehension (MRC) system**. The goal is to answer natural language questions by extracting exact spans from Persian text. The project evaluates **Transformer-based models**:

* **ParsBERT-QuestionAnswering-PQuAD** – Persian-specific BERT variant.
* **XLM-RoBERTa-Large** – multilingual model fine-tuned for Persian QA.

The workflow follows a **SQuAD-style extractive QA setup**.

---

## Dataset

* **Format:** JSON/CSV with `context`, `question`, `answer_text`, `answer_start`.
* **Splits:** `train`, `validation`, `test`.
* **Challenges:** Right-to-left text, tokenization, and answer span alignment.

**Example:**

```json
{
  "title": "خوب، بد، زشت",
  "context": "خوب، بد، زشت یک فیلم در ژانر وسترن اسپاگتی ...",
  "question": "در فیلم خوب بد زشت شخصیت ها کجایی صحبت می کنند؟",
  "answer": "مخلوطی از ایتالیایی و انگلیسی"
}
```

---

## Pipeline

1. Dataset loading & exploration
2. Preprocessing & cleaning
3. Tokenization & feature preparation
4. ParsBERT setup, baseline evaluation, fine-tuning
5. XLM-RoBERTa-Large setup, evaluation, fine-tuning
6. Postprocessing, metrics calculation (EM, F1), error analysis
7. Results visualization and reporting

---

## Challenges & Notes

* Persian text preprocessing (diacritics, half-spaces)
* Right-to-left handling
* Large model GPU memory requirements
* Tokenized answer span alignment

---

## Applications

* Persian search engines with direct answer retrieval
* Intelligent tutoring systems and educational QA
* Customer support chatbots for Persian users

---

## Usage

```bash
git clone https://github.com/MahdyMokh7/ParsQA.git
cd ParsQA
jupyter notebook PersianQA.ipynb
```

Install dependencies:

```bash
pip install transformers datasets torch matplotlib
```

Run notebook cells sequentially to reproduce dataset preprocessing, model fine-tuning, and evaluation.

