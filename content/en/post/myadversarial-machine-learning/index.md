---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Adversarial Machine Learning"
subtitle: ""
summary: "Despite DNNs imperessive performance in wide variety of fields, they are easy to fool with carefully designed small perturbations to their input which is imperceptible to humans."
authors: [admin]
tags: []
categories: []
date: 2020-05-25T14:31:54-07:00
lastmod: 2020-05-25T14:31:54-07:00
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Machine learning and especially deep learning have gained significant attention with the advance in the parallel computation units (GPU, TPU, etc). Higher computational power allowed us to be able to train more complex and expressive neural networks which perform even better than human experts in a number of fields. AlphaGo which is developed by deepmind to play the game of Go was able to beat 18-time world champion Lee Sedol on March 2016. Furthermore, in a well known image classification benchmark imagenet DNNs have already surpassed human performance. All these successes boosted research on DNNs even further.

Nowadays we use many DNN empowered applications in our every day life. Despite deep networks incredible performance in classification tasks, they have recently been shown that they are easy to fool with carefully designed small perturbations to their input which is imperceptible to humans. Recent studies show that most of the well-performing neural networks can succesfully be fooled with a tiny perturbation. With these results, a great effort put forward by the research community to account for this phenomenon. 

On this blog, i will try to summarize the most recent adversarial attack and adversarial defense methods. Moreover, I will try to give the intuituion behind all these methods so that reader can develop its own ideas on top of the state of the art methods. Here I need to note that there is no simple defense mechanism which is robust to all kind of adversarial examples like human visual system. One can say that even human visual system is not a robust one since it can be easily fooled by illusions. However, our main goal in deep neural networks is that we want to make sure they work similar to human visual system so that they will not be fooled by any kind of perturbations that are imperceptible to humans.

## **Problem Definition** #

TODO




