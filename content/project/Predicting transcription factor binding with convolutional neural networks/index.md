---
title: Predicting transcription factor binding with convolutional neural networks
summary: Course project for MIT 6.867 Graduate Machine Learning. Co-authored with Ellen Zhong.
tags:
  - Deep Learning, Data Science, Computational Biology, 
date: '2016-04-27T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Photo by rawpixel on Unsplash
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

Implemented convolutional neural networks (CNN) to predict transcription factor (TF) binding affinities, using data from the DREAM5 challenge https://www.synapse.org/#!Synapse:syn2887863/wiki/72185.

Performed architecture sweeps (filter width, number of feature detectors, number of nodes in the convolutational layer) and parameter sweeps (dropout rate, regularization strength) to identify an optimized network.

Developed a regression CNN for predicting transcription factor binding with improved Pearson's correlation, AUC, and average precision over the DeepBind CNN architecture (https://www.nature.com/articles/nbt.3300).

Developed classification CNNs to predict whether a given TF is a low or high affinity binder. As this is a highly unbalanced classification problem (high affinity binders are very rare), we implemented three techniques for dealing with unbalanced classification: 1) oversampling data in the minority class 2) undersampling data in the majority class (low binder) data points 3) Using a loss function that was weighted by the number of data points in each class.