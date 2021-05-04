---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Jupyter Notebook"
subtitle: ""
summary: "Get started with jupyter notebook and utilize it in your work."
authors: [admin]
tags: []
categories: []
date: 2021-05-03T17:19:51-07:00
lastmod: 2021-05-03T17:19:51-07:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

# Introduction to Jupyter Notebook


Personally, I like jupyter notebook a lot, since it offers plenty of useful tools to work on your code. Specifically, it enables you to test your code on the run by providing multiple cells which can be used to run specific parts of the code. In case, there are errors in some parts of the code, then you don't need to rerun the whole code but only the part you have errors. Moreover, it offers a convenient way to visualize your code, to inspect the variables.

<img src="ex.png" alt="An example" width="600"
         height="320">

## Installation

For conda users following command is good to go:

```bash
conda install -c conda-forge notebook
```

For old-school pip:

```bash
pip install notebook
```

## Usage

In order to launch the notebook:

```bash
jupyter notebook
```

If you are interested in using jupyter notebook through a specific port (9999 for instance):

```bash
jupyter notebook --port 9999
```

After running the command, the main browser should open a tab for your notebooks, in case it doesn't happen, you can just copy and paste the link printed in the command-line.

## Remote

If you want to access the notebooks in a remote machine, you need to forward everything on the port 9999 (the port you use for jupyter-notebook) of the server (in 127.0.0.1:9999) to local machine on the port 19999 (again this can be any port). This can be done by connecting to server with a small addition to the original ssh command.

```bash
ssh -L 19999:127.0.0.1:9999 acc_name@server_ip
```

Then you will be able to connect the jupyter-notebook of interest through the following [link](http://127.0.0.1:19999) (http://127.0.0.1:19999) from your local device.


Congratulations, you can enjoy your notebook.





