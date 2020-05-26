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

Despite deep networks incredible performance in classification tasks, they have recently been shown that they are easy to fool with carefully designed small perturbations to their input which is imperceptible to humans. Recent studies show that most of the well-performing neural networks can succesfully be fooled with a tiny perturbation. With these results, a great effort put forward by the research community to account for this phenomenon in recent years. 

On this blog, we summarize the most recent adversarial attack and adversarial defense methods. Moreover, we try to give the intuituion behind all these methods so that reader can develop his/her own ideas on top of the state of the art methods. Here we need to note that there is no simple defense mechanism which is robust to all kind of adversarial examples like human visual system. It's been shown that defending against threat models is not an easy task. One can say that even human visual system is not a robust one since it can be easily fooled by illusions. However, our main goal in deep neural networks is that we want to make sure they work similar to human visual system so that they will not be fooled by any kind of perturbations that are imperceptible to humans.

## **Neural Networks** #

One needs to understand how deep neural networks are trained to perform a wide variety of tasks to be able to digest how threat models are developed and performed. Bear with me, I will try to give quick summary of neural networks. Deep neural networks consist of serially connected layers which are simply connected by nonlinear activation functions (ReLU, sigmoid, tanh, etc.). These layers are nothing but matrix multiplications which are specifically tuned for the task at hand. 

$$
 out=f_L(...f_1(W_1 * f_0(W_0 * x+b_0))+b_1)...) \quad \quad \text{: Neural network as a function}
$$
Where $W_l$ and $b_l$ corresponds to the parameters of $l$th layer and $f_l$ corresponds to the $l$th layer activation function.

In order to train neural network we need labels and a well-defined loss function to approximate these labels. Labels are basically class names for a clasification task (imagine a binary classification with 2 labels: cat, dog) which are expressed as one hot vectors ([1,0] for cat, [0,1] for dog). Output of the neural net will be an array consisting of scalar numbers corresponding to the probabilities of each class (for our example cat and dog e.g [0.9, 0.1] => probability of cat and dog for given image respectively). Computation of loss is rather easy, we need to define loss function such that if our predictions are close to the original label loss should be small else it hould be high. There are a number of different loss functions one of which (the most popular one) is cross entropy loss defined as:

$$
Loss = -\sum_{c=1}^{M} y_c \log(out_c) \quad \quad \text{: Cross entropy loss for multiclass}
$$

where $c$ corresponds for the class index, $y$ corresponds for the one hot label and out corresponds for the prediction propabilities of our neural network. If given label is corresponding to class c then we want to make sure prediction of class c is close to one (1 means neural net thinks that the given image is 100% from that class) so that loss decreased. Observe that negative sign in front of the loss is there to make Loss function positive because we have prediction probabilities in between 0 and 1 which makes $log$ output negative. On the other hand if $y$ corresponding to class c is zero we don't care about the prediction of that class at all. 

Now we need to train our neural network so that we can decrease loss and predict close to the original labels. How can we do that? The answer is simple, and comes from the calculus. All we need to do is that taking derivative of loss with respect to the parameters of the neural network and subtract it from the parameters to decrease loss function. This operation is called gradient descent. First question comes into mind after all these explanition is that how can one compute the derivatives after all serially connected layers, especially for intermediate layers. Don't worry about this though, because back-propagation algorithm is doing the magic for us, and calculate all the derivatives (gradients). We will not discuss the details of back-propagation algorighm since it is beyond the scope of this talk. With the help of back-propagation and gradient descent we train our network with training dataset to decrease loss. 

$$
W = W - \nabla_{W}(Loss) \quad \quad \text{: Gradient step for all parameters}
$$

$$
w_{il} = w_{il} - \frac{\partial Loss }{\partial w_{il}} \quad \quad \text{: Partial derivative wrt a specific parameter}
$$

Where $w_{il}$ corresponds to layer $l$s $i$th parameter. To summarize, since gradient gives the direction to increase the given function, by subtracting it, we are able to decrease loss (thanks calculus). 

After a number of iterations (epochs), neural network becomes ready to perform classification task. With a distinct test set one can evaluate the trained model to see the performance of it. So far, we learned how the standard training work let us dive into how we generate adversarial examples which fool the neural network we trained.

## **Generating Adversarial Examples** #

We mentioned the power gradient descent, and how it is able to decrease loss function significantly over training process. Can you believe gradient descent is also a tool to create adversarial images for our neural network? Things are getting excited now, ...




