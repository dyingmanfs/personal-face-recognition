# Personal Face Recognition

A coursework project exploring transfer learning for binary face classification: **YOU** versus **NOT YOU**. It combines a pretrained ResNet18 model, a training and evaluation workflow, and a Gradio image-upload interface.

## Stack
Python, PyTorch, torchvision, scikit-learn, Pillow, Matplotlib, Jupyter, Gradio.

## Features
- Fine-tuning a pretrained CNN for two-class classification.
- Separate training, validation, and test datasets.
- Precision, recall, and F1 evaluation.
- Interactive prediction with class probabilities.

## Run locally
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebook.ipynb
```
Run the notebook from the repository root, in section order. Prepare images under `data/positive/{train,val,test}` and `data/negative/{train,val,test}`. See `src/dataset.py` for the negative dataset loader and `config.json` for training settings. The original experiment uses 20 training, 5 validation, and 5 test images per class.

Train locally to create `checkpoints/best_model.pt`, then launch the Gradio interface through the notebook using `build_app(config_path='config.json')`. The standalone app has relative-path assumptions; the notebook is the documented entry point.

## Repository contents
`src/` contains dataset, model, training, evaluation, and interface code. `notebook.ipynb` orchestrates the workflow; its saved outputs have been cleared for publication.

## Scope and limitations
This is a small-data educational classifier. It has no liveness detection or production authentication guarantees. Personal face photographs, screenshots, trained weights, and generated logs are excluded. No independently verified performance claim is made here.

## Attribution
Developed as part of CNG403 Assignment 2. The supplied scaffold and dataset-loading code are retained; comments identify provided sections and implementation tasks. This repository contains both coursework scaffolding and completed implementation.
