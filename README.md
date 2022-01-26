# FullGD for non vision tasks

The idea of this project is to test to what extent are results in paper https://arxiv.org/abs/2109.14119 are applicable on other tasks in different area from CV.
Three experiments were conducted:
1. Name classification (NLP task)
2. KeyWord Spotting (KWS) classification, 3 vs other (DLA task)
3. KWS binary classification, 1 vs other (DLA task)

Experiments are conducted in Natural Language Processing and Depp Learning in Audio areas. 
Tasks were chosen to be quite simple to be able to run on Google Colab resources. Thus tasks with small datasets and small
Neural Networks were chosen.

Experiment training process can be seen here: https://wandb.ai/artgoldman/FullGD-HSE-RS

# Brief description

Same validation accuracy was achieved on FullGD training as on simple SGD run, using only more epochs for training and 
gradient clipping. Regularizer from paper was not used.

In third experiment (KWS binary classification) not only high validation accuracy was achieved, but also 
AUC-FA-FR (similar to AUC-ROC metric in KWS) was achieved comparable to SGD run. 

These results show, that it is possible to achieve accuracy value, set in advance for simple runs. 
Though it is not clear to what extent FullGD training can achieve generalisation properties for much harder tasks
comparable with different optimisers (e.g. Adam)

# Things noticed

- Gradient clipping is a good regularization technique. It is very useful to use it even with Stochastic training.
- It is important to measure not only quality of predictions, but confidence in them (e.g. not only accuracy, but AUC-ROC)
- Overcoming bias-variance tradeoff threshold was noticed in experiments, described in https://arxiv.org/pdf/1912.02292.pdf


# Credits
NLP experiment is a modified version of [this official PyTorch tutorial](https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html)

DLA experiments are heavily based on [this seminar](https://github.com/markovka17/dla/blob/2021/week06/seminar.ipynb)
from [HSE DLA course](https://github.com/markovka17/dla)

This project was conducted for [HSE Research Seminar](https://github.com/bayesgroup/HSE_ML_research_seminar/tree/master/2021-2022),
see materials of the talk here.
