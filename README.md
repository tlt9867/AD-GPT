# ADGPT1 — Bioinformatics Task Routing Conversational System

ADGPT1 is a multi-turn conversational system designed for **Alzheimer’s disease–oriented bioinformatics research**.  
The system classifies incoming user questions into **three study types** and dynamically routes them to **specialized fine-tuned models** to generate accurate, context-aware responses.

> ⚠️ This project is intended for **academic and research use only**.

---

## ✨ Key Features

- Three-task expert routing architecture (Gene / Association / Other study)
- Fine-tuned LLaMA3-based expert models
- BERT-based task classifier (router)
- Multi-turn conversational memory per session
- Modular FastAPI backend + lightweight frontend
- Designed for gene–disease (Alzheimer’s) reasoning tasks

---

## 🧠 Supported Tasks (Updated ADGPT1)

| Task ID | Study Type | Description |
|---:|---|---|
| 1 | **Gene study** | Gene-centric biological knowledge (e.g., gene function, chromosome location, expression context, OMIM-style summaries) |
| 2 | **Association study** | Gene–Alzheimer’s disease association confirmation based on curated molecular genetics evidence |
| 3 | **Other study** | Other AD-related bioinformatics questions not covered by task 1–2 (e.g., workflow, dataset interpretation, cross-modal analysis) |

Each task is handled by a **dedicated fine-tuned model** optimized for that reasoning style.

---

## 🏗️ System Architecture

```text
User Query
    ↓
Task Classifier (BERT, 3-way)
    ↓
┌─────────────┬─────────────────┬─────────────────┐
│ Gene Study  │ Association     │ Other Study     │
│ Model       │ Study Model     │ Model           │
└─────────────┴─────────────────┴─────────────────┘
    ↓
Context-Aware Response


## 🗃️ Directory Structure

```plaintext
.
├── app1.py                     # FastAPI chat server
├── chat1.html                  # Simple frontend chat UI
├── llama3_training.py          # LLaMA3 training script for Task 1
├── llama3_task3.py             # LLaMA3 training script for Task 3
├── llama3_task4.py             # LLaMA3 training script for Task 4
├── task_classification_pipeline.py  # BERT training pipeline
├── utils.py                    # Utility functions (assumed external)
├── models/                     # Saved models (referenced by FastAPI)
│   ├── base_model/
│   └── adapters/
├── data/
│   ├── task1_combined.parquet
│   ├── task2_test_v4.parquet
│   ├── gene_database_v2.db
│   └── task34_dataset_V3/


