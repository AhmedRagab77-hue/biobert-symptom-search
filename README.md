BioBERT Symptom Search

Graduation project: scrapes illness pages, matches symptoms with BioBERT + FAISS, and gives general guidance via Gemini.

Two notebooks:

Final_project_web_scraping.ipynb: scrapes illness pages into MongoDB.
final_proccessing.ipynb: extracts symptoms, builds a BioBERT + FAISS index and runs a Gradio app that suggests a matching condition and general guidance from Gemini.

⚠️ Educational project only. Not medical advice and not a diagnosis tool. In an emergency contact your local emergency services.

Setup
bash
pip install -r requirements.txt
cp .env.example .env     # then put your own GEMINI_API_KEY in .env

Requires a running MongoDB at mongodb://localhost:27017/. Run notebook 1, then notebook 2.

Data source

Illness information comes from NHS inform (nhsinform.scot), © NHS 24. This project is not affiliated with or endorsed by NHS 24. Scraped content is not included in this repository. Educational, non-commercial use only. Please read the source site's terms and conditions before collecting or sharing any of its content.

Notes
Never commit .env or API keys.
Clear notebook outputs before committing, since they can contain scraped content and local paths.
