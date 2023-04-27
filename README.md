# Adv-SQuAD-ELECTRA

This repository is a fork of the original [CS378 project code](https://github.com/utcsnlp/cs378_fp), modified to work with the SQuAD and Adv-SQuAD datasets for question-answering tasks. Credit to Kaj Bostrom, Jifan Chen, and Greg Durrett for the original project and code.

This Project was done as part of the course CS 378: Natural Language Processing at the University of Texas at Austin by Amog Iska.

## Introduction

Adv-SQuAD (Adversarial SQuAD) is a dataset derived from the original SQuAD (Stanford Question Answering Dataset) by introducing more challenging and adversarial questions. These questions are designed to exploit the weaknesses of the ELECTRA model, such as questions requiring multi-step reasoning, containing lexical or syntactic ambiguity, and having distractor information in the context. The aim is to improve the model's performance on question-answering tasks by incorporating these difficult instances into the training process.

For more information about Adv-SQuAD, visit the dataset's [Hugging Face page](https://huggingface.co/amogiska/adv-SQuAD).

Please refer to the original repository for basic setup instructions and dependencies installation.

## Training and Evaluating on SQuAD and Adv-SQuAD

To train and evaluate the model specifically on SQuAD and Adv-SQuAD datasets, follow the instructions below:

1. Make sure the Adv-SQuAD dataset (test.json) is included in the repository.

2. Run the training command:
```bash
python3 run.py --do_train --task qa --dataset combined_squad_adv_squad --output_dir ./trained_model/
```

3. Run the evaluation command:
```bash
python3 run.py --do_eval --task qa --dataset squad --output_dir ./trained_model/
```
Replace `squad` with `combined_squad_adv_squad` to evaluate on Adv-SQuAD as well.

For a detailed description of other arguments, refer to the comments in run.py.

If you wish to use different pretrained models, modify the --model argument. 

Data and models will be automatically downloaded and cached in ~/.cache/huggingface/. To change the caching directory, modify the shell environment variables HF_HOME or TRANSFORMERS_CACHE. 