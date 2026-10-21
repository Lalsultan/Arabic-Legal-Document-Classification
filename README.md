# Arabic Legal Document Classification

A team academic project exploring Arabic NLP for two classification tasks on the ALARB Saudi commercial-court dataset:

- **Verdict prediction:** maps the source verdict text into a smaller set of outcome labels.
- **Legal-topic classification:** derives topic labels from cited laws using rule-based mapping.

## Methods

The notebook includes Arabic text normalization, removal of diacritics and tatweel, stopword removal, optional ISRI stemming, bag-of-words and TF-IDF features, word/character n-grams, Logistic Regression, Linear SVM, a feed-forward neural network, and optional AraVec/AraBERT experiments. It also includes error analysis and an optional Gradio demo.

## Dataset

The notebook loads `THIQAH-RD/ALARB` from Hugging Face Datasets. Review the dataset card and its terms before using or redistributing the data. The dataset itself is not bundled in this repository.

## Setup

Use Python 3.10 or 3.11 in a virtual environment, then install dependencies from `requirements.txt`. The original notebook was developed in a hosted notebook environment; local execution may require package-version adjustments and sufficient memory.

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Open `arabic_legal_document_classification.ipynb`. Run cells in order. The notebook installs some packages itself; consolidate these installs before a final release.

### Optional AraVec experiment

The pretrained AraVec model is not included. Obtain it only from an authorized source and set `ARAVEC_PATH` to the local model file. The notebook no longer contains a personal Google Drive path.

### Optional AraBERT and demo

AraBERT fine-tuning and the Gradio demo are disabled by default to avoid unexpectedly long runs or public hosting. Enable them only when intentionally running those sections. The demo is configured not to create a public share link.

## Evaluation and limitations

The original saved notebook reported a best cross-validated weighted F1 score of about **0.695** for the tuned SVM configurations, with additional error analysis. These are historical notebook outputs, not independently reproduced results; outputs were removed from this prepared copy. Re-run the full pipeline before quoting metrics. Topic labels are derived from cited laws using hand-written rules, and verdict labels are mapped from source text, so label quality depends on those rules. This is a research prototype, not a legal decision-making tool.

## Attribution and release status

This originated as a collaborative academic project. Final contributor credits and permission to publish the derived code/materials must be confirmed before release. The original report, personal identifiers, notebook outputs, and temporary runtime URLs are intentionally excluded. No open-source license has been added.
