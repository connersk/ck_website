---
title: Predicting transcription factor binding with convolutional neural networks
summary: Course project for MIT 6.867 Graduate Machine Learning. Co-authored with Ellen Zhong.
tags:
  - Deep Learning, Data Science, Computational Biology, 
date: '2022-08-26T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Created with biorender
  focal_point: Smart

links:
  # - icon: twitter
  #   icon_pack: fab
  #   name: Follow
  #   url: https://twitter.com/georgecushen
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

Transcription factors (TFs) are regulatory proteins in a cell that bind to DNA and turn genes on or off. Accurate prediciton of where TFs bind in the genome would enable harnessing these proteins for cellular engineering and therapeutic development. 

In this project for MIT 6.867 (Graduate Machine Learning) I worked with my project partner to implement convolutional neural networks (CNN) to predict transcription factor (TF) binding affinities, using data from the DREAM5 challenge https://www.synapse.org/#!Synapse:syn2887863/wiki/72185. We first performed architecture sweeps (filter width, number of feature detectors, number of nodes in the convolutational layer) and parameter sweeps (dropout rate, regularization strength) to identify an optimized network. We then used this optimized architecture to do two tasks 1) Directly predict TF binding affinities to DNA sequences (regression) and 2) predict whether a TF would have a high or low binding affinity for a given DNA sequence (classification). 

For our regression task, we found that our model displayed improved Pearson's correlation, AUC, and average precision over the existing state of the art model (DeepBind) (https://www.nature.com/articles/nbt.3300). In our classification model, we first tested our optimized architecture and found that due to the highly imbalanced nature of the classes in the data, it had a low average precisio of 0.24. Thus, we implemented three techniques for dealing with unbalanced classification: 1) oversampling data in the minority class 2) undersampling data in the majority class (low binder) data points 3) Using a loss function that was weighted by the number of data points in each class. We found that undersampling performed best, resulting in an average precision of 0.93 (a 0.69 improvement from our benchmark).