---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Deep Illusion (Adversarial ML toolbox)"
summary: "Created and published an adversarial ML toolbox 'deepillusion'"
authors: [admin]
tags: [Deep Learning]
categories: [Deep Learning]
date: 2020-05-03T13:36:47-07:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Fooled AI"
  focal_point: "bottom"
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

<br/>

## Deep Illusion #

Deep Illusion is a toolbox for adversarial attacks in machine learning. Current version is only implemented for Pytorch models. DeepIllusion is a growing and developing python module which aims to help adversarial machine learning community to accelerate their research. Module currently includes complete implementation of well-known attacks (PGD, FGSM, R-FGSM, CW, BIM etc..). All attacks have an apex(amp) version which you can run your attacks fast and accurately. We strongly recommend that amp versions should only be used for adversarial training since it may have gradient masking issues after neural net gets confident about its decisions. All attack methods have an option (Verbose: False) to check if gradient masking is happening. 

All attack codes are written in functional programming style, therefore, users can easily call the method function and feed the input data and model to get perturbations. All codes are documented, and contains the example use in their description. Users can easily access the documentation by typing "??" at the and of the method they want to use in Ipython (E.g FGSM?? or PGD??). Output perturbations are already clipped for each image to prevent illegal pixel values. We are open to contributers to expand the attack methods arsenal.

We also include the most effective current approach to defend DNNs against adversarial perturbations which is training the network using adversarially perturbed examples. Adversarial training and testing methods are included in torchdefenses submodule. 

To standardize the arguments for all attacks, methods accept attack parameters as a dictionary named as attack_params which contains the necessary parameters for each attack. Furthermore, attack methods get the data properties such as the maximum and the minimum pixel value as another dictionary named data_params. These dictinaries make function calls concise and standard for all methods.

Current version is tested with different defense methods and the standard models for verification and we observed the reported accuracies.

Code can be installed via PyPi:
```bash
pip install deepillusion
```

[PyPi page for the code](https://pypi.org/project/deepillusion/)

[Git repo for the code](https://github.com/metehancekic/deep-illusion)



