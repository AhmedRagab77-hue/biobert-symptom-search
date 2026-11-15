# Symptom Matching Agent (final project)

Two notebooks:

1. `Final_project_web_scraping.ipynb` scrapes the A–Z illness pages from NHS Inform and stores them in MongoDB.
2. `final_proccessing.ipynb` extracts symptom text, builds a BioBERT + FAISS index and serves a small Gradio app
   that matches symptoms to conditions and asks Gemini for general guidance.

> ⚠️ **Disclaimer:** educational project only. It is **not** a medical device, does not provide diagnoses or
> medical advice, and must not be used to make health decisions. In an emergency contact your local emergency services.

## Setup

```bash
pip install -r requirements.txt
cp .env.example .env      # then edit .env and add your own GEMINI_API_KEY
```

You also need a running MongoDB (default `mongodb://localhost:27017/`).
Run notebook 1 first, then notebook 2.

## Security notes

- Secrets are read from environment variables / `.env` (git-ignored). Never commit real keys.
- The Gradio app is local-only by default. Public sharing needs `GRADIO_SHARE=true` plus `GRADIO_USER` / `GRADIO_PASSWORD`.
- Clear notebook outputs before committing (they can contain paths, links and scraped content).

## Data & copyright

The scraped NHS Inform content is **not** included in this repo. Check the site's terms of use before
redistributing any scraped data.