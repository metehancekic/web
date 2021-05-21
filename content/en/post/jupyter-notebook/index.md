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

If you are interested in using jupyter notebook through a specific port (8888 for instance):

```bash
jupyter notebook --port 8888
```

If everything goes smooth, after running the command, the main browser should open a tab for your notebooks. On the other hand, if it doesn't happen, you can just copy and paste the link printed in the command-line.

<img src="jupy-term.png" alt="An example" width="600"
         height="320">

## Remote

If you want to access the notebooks in a remote machine, you need to forward everything on the port 8888 (the port you use for jupyter-notebook) of the server (in 127.0.0.1:8888) to local machine on the port 1234 (again this can be any port). This can be done by connecting to server with a small addition to the original ssh command.

```bash
ssh -L 1234:127.0.0.1:8888 acc_name@server_ip
```

Here, "-L" option allows you to map a specific port on the server machine to your local machine's port.

Then you will be able to connect the jupyter-notebook of interest through the following [link](http://127.0.0.1:1234) (http://127.0.0.1:1234) from your local device.


Congratulations, you can enjoy your notebook.





