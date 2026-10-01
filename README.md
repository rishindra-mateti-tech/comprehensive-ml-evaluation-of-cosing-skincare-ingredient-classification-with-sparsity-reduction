# A Comprehensive Evaluation of Machine Learning Models for CosIng Skincare Ingredient Classification with Class Sparsity Reduction

This repository is the reproducible research companion to [CUTIeS-IQ](https://github.com/rishindra-mateti-tech/CutisIQ), a product-oriented skincare ingredient analysis application. It contains the research artifacts only: the CosIng data snapshot, training notebook, exported notebook, paper PDF, and a standalone training script.

> This work predicts cosmetic **ingredient functions** from CosIng metadata. It is not a medical, dermatological, safety, or product-recommendation system.

## Research question

How well can multi-label machine-learning models classify cosmetic ingredient functions from ingredient names and descriptions when rare classes are handled through class-sparsity reduction?

## Reported work

- Curated a reproducible snapshot of CosIng ingredient and fragrance-inventory data.
- Formulated ingredient-function prediction as a multi-label classification task.
- Applied class-sparsity reduction by retaining functions with at least 20 occurrences.
- Built TF-IDF features from INCI ingredient names and chemical/IUPAC descriptions.
- Evaluated the model pipeline documented in the notebook and accompanying paper.

The research artifacts report an overall accuracy of **78.6%** and a post-reduction improvement of **21.4 percentage points**. These are project-reported experimental results, not independently reproduced benchmark claims.

## Repository map

| Path | Contents |
| --- | --- |
| [`paper/`](paper) | Original project paper and a one-page research project summary |
| [`notebooks/`](notebooks) | Executable Jupyter notebook and its HTML export |
| [`data/raw/`](data/raw) | CosIng source snapshot and supporting annex files |
| [`src/train.py`](src/train.py) | Standalone, repo-relative training entry point |
| [`src/artifacts/`](src/artifacts) | Saved label binarizer, vectorizers, and class labels |

## Reproduce the training pipeline

```bash
python -m venv .venv
.venv\\Scripts\\activate        # Windows PowerShell
pip install -r src/requirements.txt
python src/train.py
```

By default, model outputs are written to `src/artifacts/`. A full run trains a multi-output random-forest model and can take several minutes, depending on hardware.

```bash
python src/train.py --data-dir data/raw --output-dir artifacts/run-1
```

## Data and provenance

The checked-in files are a project snapshot of the European Commission CosIng data used for this work. See [`data/README.md`](data/README.md) for provenance and responsible reuse notes. Re-check the current source and its terms before redistributing or using the data beyond research and reproducibility work.

## Relationship to CUTIeS-IQ

This is deliberately not the application repository. For the deployed/product engineering context, user interface, and service integration, see [CUTIeS-IQ](https://github.com/rishindra-mateti-tech/CutisIQ). Keeping the two repositories separate lets research reviewers inspect the evidence and lets engineering recruiters evaluate the product independently.

## Authors

Rishindra Mateti, Surya Thota, and Tejaswi Reddy Kancharla

## Citation

Use GitHub's **Cite this repository** panel for software/artifact citation. The included project paper is retained in [`paper/CUTIeS_V2_Paper_Rishindra.pdf`](paper/CUTIeS_V2_Paper_Rishindra.pdf).
