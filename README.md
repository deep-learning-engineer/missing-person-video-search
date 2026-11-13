# MPVS (Missing Person Video Search)

**Searching for people in video footage using natural-language descriptions**

A research and engineering project exploring how deep learning and multimodal retrieval can help locate missing persons in video data based on textual bulletins (descriptions). The repository combines source code, trained models, evaluation pipelines, and research documentation.

---

## Overview

Searching for a missing person in hours of video footage is traditionally a manual, time-consuming task. This project investigates whether modern computer vision and vision-language architectures can automate the retrieval process end-to-end, using natural-language descriptions (e.g., clothing, age, gender, context) as queries.

Every major architectural choice is documented as an Architecture Decision Record (ADR) in `docs/adr/`.

**Key goals:**
* Build a reproducible pipeline: `text description → person detection/tracking → feature extraction → retrieval`.
* Train and evaluate neural models on curated video datasets with person annotations.
* Document the research process and decisions.
* Provide a modular foundation that can be extended to real-world missing-person search scenarios.

---

## Project Structure

```text
missing-person-video-search/
├── data/
│   ├── raw/                     # Original, unmodified data (source videos, annotations)
│   └── processed/               # Cleaned and preprocessed data ready for training/evaluation
├── src/
│   ├── models/                  # Neural network architectures
│   ├── training/                # Training loops, loss functions, hyperparameter configs
│   ├── evaluation/              # Metrics, evaluation scripts, retrieval benchmarks
│   └── utils/                   # Shared utilities (data loading, logging, visualization, ...)
├── models/
│   └── checkpoints/             # Trained model weights and checkpoints
├── docs/
│   ├── adr/                     # Architecture Decision Records
│   └── research/                # Research materials (problem statement, SOTA review, ...)
├── results/
│   ├── figures/                 # Generated plots, visualizations, retrieval examples
│   └── tables/                  # Generated result tables (metrics, comparisons)
└── LICENSE
```

**Note:**
* `data/raw/`, `data/processed/`, and `models/checkpoints/` are excluded from Git (see `.gitignore`). Only `.gitkeep` placeholders are tracked. A public link to the full dataset and trained checkpoints will be added here when available.
* `results/figures/` and `results/tables/` **are** tracked, so that experimental results can be inspected directly in the repository.
* The research documentation is written in Markdown and maintained inside `docs/research/`.

---

## Getting Started

> The project is in early development. Setup instructions will be expanded as the pipeline is implemented.

```bash
# Clone the repository
git clone https://github.com/deep-learning-engineer/missing-person-video-search.git 
cd missing-person-video-search

# (Optional) Create a virtual environment
python -m venv .venv
source .venv/bin/activate   # on Windows: .venv\Scripts\activate

# Install dependencies (requirements.txt to be added)
# pip install -r requirements.txt
```

---

## Intended Use & Ethical Guidelines

This project is intended **exclusively** to assist search-and-rescue teams and law enforcement in locating missing persons. 

The author strictly prohibits any use of this software for unauthorized surveillance, stalking, tracking individuals without consent, or any other malicious purposes. 

---

## License

This project is licensed under the **Mozilla Public License 2.0 (MPL-2.0)**.  
See the [`LICENSE`](./LICENSE) file for the full text.

---

## Author

**Ganzha Eduard**
* Research topic: _Missing Person Video Search_
* Contact: [edik.ganzha.05@gmail.com](mailto:edik.ganzha.05@gmail.com)

