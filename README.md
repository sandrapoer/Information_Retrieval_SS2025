# Information Retrieval and Ranking on "Bones"

A hybrid Retrieval-Augmented Generation (RAG) system built around the TV series *Bones*, combining semantic (dense) and keyword-based (sparse) retrieval to answer user queries through a simple Streamlit interface.

> This project is forked from my dear colleague Martina with whom I did the project together

## Overview

The app lets a user type a natural-language question about *Bones*, retrieves relevant passages using a hybrid retrieval approach, and generates an answer from the retrieved context. The core logic lives in a `HybridRetriever` class (`Retrieval_ranking_answer/hybrid_retr.py`), which the Streamlit frontend (`app.py`) loads and queries.

Pipeline:
- **Semantic/dense retrieval** via the `ChromaDB_semantic/` component
- **Keyword/structured retrieval** via the `SQLite/` component
- **Preprocessing** of the source data (`Preprocessing/`)
- **Evaluation** against a set of test queries (`Evaluation_queries/`)


## Requirements

The app is built with [Streamlit](https://streamlit.io/). 

```bash
pip install streamlit
```

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/sandrapoer/Information_Retrieval_SS2025.git
   cd Information_Retrieval_SS2025
   ```
2. Install the required dependencies (see [Requirements](#requirements)).
3. Run the Streamlit app:
   ```bash
   streamlit run app.py
   ```
4. Open the local URL shown in the terminal, enter a query about *Bones* in the text box, and the app will retrieve relevant context and generate an answer.
