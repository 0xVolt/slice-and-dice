# Multi-Source Summarization Suite

A modular, full-stack web application for intelligent multi-source text summarization powered by transformer-based models. Designed to handle both raw text and document inputs, the system dynamically evaluates and selects the most effective summarization model, offering a seamless and accurate user experience.

## Key Features

- **Multi-Input Summarization Modes**  
  - Summarize free-form text blobs  
  - Extract and summarize content from PDF documents  
  - Hybrid mode for combined inputs

- **Dynamic Model Selection**  
  The backend evaluates generated summaries across multiple transformer-based models and selects the optimal one based on evaluation metrics (ROUGE scores, loss curves).

- **Transformer Models Integrated**  
  - T5 — Fine-tuned on XSum  
  - BART — Fine-tuned on CNN/DailyMail  
  - GPT-2 — Adapted for abstractive summarization tasks  
  - Pegasus — State-of-the-art summarization on long documents  
  - ProphetNet — Tailored for sequence-to-sequence summarization

- **Streamlit Frontend**  
  - Clean UI with tabs for different input types  
  - Model selection dropdown with evaluation-based ranking  
  - Interactive outputs with click-to-copy summaries  
  - Optional keyword-based summarization via speech or text input

- **User History and Analytics**  
  - User authentication and login system  
  - Summary history logging via database  
  - Comparative analytics dashboard (Training/Validation Loss, Model Comparison)

## Model Training Workflow

- Custom dataset loader class with integrated train/test splitting
- Tokenization using Hugging Face `encode_plus()` with:
  - Attention masks for padded tokens  
  - Truncation and padding to manage input lengths
- Evaluation using:
  - ROUGE-N for n-gram precision and recall  
  - ROUGE-L for longest common subsequence matching

## Evaluation Metrics

- Training and validation loss tracking  
- ROUGE score comparison across models  
- Real-time model performance ranking displayed in UI

## Tech Stack

- Transformers: Hugging Face (T5, BART, Pegasus, etc.)  
- PDF Handling: PyPDF2  
- Frontend: Streamlit  
- Backend: Python with optional Flask integration  
- Database: SQLite or PostgreSQL for user login and summary history

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/your-username/multisource-summarizer.git
cd multisource-summarizer
```

2. Set a Virtual Environment
   ```bash
   python -m venv env
   source env/bin/activate  # or env\Scripts\activate on Windows
   ```

3. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Launch the application:
    ```bash
    streamlit run app.py
    ```