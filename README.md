---
title: Sentence Similarity
emoji: 🏃
colorFrom: green
colorTo: indigo
sdk: streamlit
sdk_version: 1.21.0
app_file: app.py
pinned: false
license: openrail
---
## Knowledge-Based Question Answering System

This repository contains code for a knowledge-based question answering system service. 

### Overview

The system is built using BERT (Bidirectional Encoder Representations from Transformers) for natural language understanding. It is pretrained on a large corpus of Arabic text data and then fine-tuned on domain-specific question-answer pairs. 

The service matches user questions to the most similar question in the database and returns the corresponding answer. This allows it to have conversational abilities and provide relevant responses based on its knowledge.

### Contents

- `data/`: Contains the Arabic preprocessed text corpus for BERT pretraining and domain-specific question-answer datasets 
- `models/`: Saved BERT models
- `src/`: Source code for model training, evaluation, and deployment
- `scripts/`: Scripts for data preprocessing and model training
- `adapters.py`: Implementation of parallel training using adapters
- `api.py`: REST API endpoint for question answering

### Setup

Requirements:
- Python 3.6+
- PyTorch 
- Transformers

To install requirements:

```
pip install -r requirements.txt
```

Pretrain BERT on the Arabic corpus:

```
python pretrain.py
``` 

Fine-tune on question-answering data: 

```
python finetune.py
```

Start the API server:

```
python api.py
```

The API will now be live on http://localhost:5000. Send JSON requests to the `/ask` endpoint with a `question` field to get responses.

### Documentation

See the [docs](docs/) folder for more details on training, evaluation, deployment, and usage.
