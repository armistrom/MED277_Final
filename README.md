# Clinical Trial Patient Matching with LLMs (RAG)

Built a **retrieval-augmented generation (RAG)** pipeline to match patients to clinical trial eligibility criteria using **unstructured EHR notes**. Evaluated **similarity-based retrieval** vs **hybrid retrieval** (keywords + **UMLS synonym expansion**) for both **Boolean** and **numeric** criteria on the **MIMIC-IV Apixaban trial criteria questions** dataset. :contentReference[oaicite:0]{index=0}

## What’s inside
- Note chunking with sentence overlap
- Embedding + FAISS indexing
- Retrieval strategies: Similarity-RAG, Keyword-RAG, UMLS-RAG
- LLM inference via AWS Bedrock (Llama 3 8B Instruct, Amazon Nova Pro, Claude 3.5 Haiku)
- Evaluation: Accuracy / F1 / AUC (Boolean), RMSE (Numeric) :contentReference[oaicite:1]{index=1}

## Key takeaway
Hybrid retrieval improves numeric extraction substantially (Similarity-RAG < Keyword-RAG < UMLS-RAG), while Boolean screening is already strong and benefits modestly from keyword signals. :contentReference[oaicite:2]{index=2}

## Dataset
MIMIC-IV patient notes (100 notes) + 23 eligibility questions derived from ARISTOTLE-like apixaban criteria (15 Boolean, 8 numeric). :contentReference[oaicite:3]{index=3}

## Run (template)
```bash
pip install -r requirements.txt
python run_experiments.py
