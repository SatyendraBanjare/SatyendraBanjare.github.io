---
layout:     post
comments:   true
title:      Probabilistic Programming
date:       2019-08-02 11:21:29
summary:    An attempt to understand Probabilistic programming using first principles of Programming Language theory.
categories: plt
keywords: probabilistic programming model programming languages theory
---
> " <u><i> Probabilistic programming is one of most promising areas at the frontier of AI since the advent of deep learning.</i></u> " - Zoubin Ghahramani, chief scientist and vice president of AI at Uber and a professor at Cambridge University. (Published at [MIT News](http://news.mit.edu/2019/ai-programming-gen-0626))

In this neoliberal economy, the market capitalism is often expressed in terms of how much data a company holds. There is recorded information about anything and almost everything that steers current market and at times creates a new market. Content consumption has thus become most important driving factor. Fine ability to accurately model data and draw inferences has developed industry giants. 

This modelling is studied as being of a deterministic nature or Probabilistic nature. Most of Machine learning advancements till now follow a deterministic approach to create inferences. However, the probabilistic systems follow a probability based approch, where there is added uncertainity about occurence of a particular event. Probabilistic algorithms are still being developed to craft the real world uncertainity. 

The recommendation systems is one of the basic application of machine learning develpment and are continuously developed and studied. The authors of **[The Netflix Effect](https://books.google.de/books?id=MhBNDAAAQBAJ&printsec=frontcover#v=onepage&q&f=false)** explain that recommendation systems tend to "<u><i><b>steer the user towards this content, thus ghettoizing the user in a prescribed category of demographically classified content.</b></i></u>" Precisely the recommendation system following a deterministic approach do not care about the undeterminism and uncertainity of a user's mood and it tries to present him/her a recommendation that is based on several other users of alike tasefulness. It needs to be clearly understood that deterministic methods foloow a total maximum number of liked/disliked content to present a suggestion whereas a probabilistic methods would recommend on the basis of probability. This would thus create an immediate shift in the recommendations. This is beautifully explained in this [video](https://youtu.be/6ZJMtgQOgEY) talk by [Prof. Christopher Bishop](https://www.microsoft.com/en-us/research/people/cmbishop/), where he explains that "<u><i><b>getting causality from data is really a subtle and a really hard problem</b></i></u>". Such aspects become more and more prevalent, thus determinism may be harmful. Probabilty based machine learning development may therefore help in advancing this.

### Current Works :

- [Problog](https://dtai.cs.kuleuven.be/problog/index.html)
- [Gen - MIT](http://probcomp.csail.mit.edu/software/gen/)
- [Pyro - Uber](https://pyro.ai/)
- [TensorFlow Probability (TFP) - Google](https://www.tensorflow.org/probability/overview)

### Example Uses :

- Recursive Multi-Agent Reasoning

- Constrained Simulation

- **Breaking Captchas** : A non-probabilistic programming approach would require gathering a very large number of Captchas, hand-labeling them all, then designing and training a neural network to regress from the image to a text string (Bursztein et al., 2014). The probabilistic programming approach in contrast merely requires one to write a program that generates Captchas that are stylistically similar to the Captcha family one would like to break – a model of Captchas – in a probabilistic programming language.


<hr>

## Let's now discuss on the development of such probabilistic programs.

Starting off with a simple comparison of probabilistic programs with simple computer programs, We have :

<table class="tg">
  <tr>
    <th class="tg-c3ow"><b>Classical Computer Programs</b></th>
    <th class="tg-c3ow"><b>Probabilistic Programs</b></th>
  </tr>
  <tr>
    <td class="tg-c3ow">Parameters</td>
    <td class="tg-c3ow">Parameters  (probably in form of  probability Distributions)</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Parameter Analysis and Algorithm Implementation</td>
    <td class="tg-c3ow">Observe and Query</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Checking Conditions</td>
    <td class="tg-c3ow">Check the Conditions (bottleneck &amp;  impossible conditions)<br></td>
  </tr>
  <tr>
    <td class="tg-baqh">Program Output</td>
    <td class="tg-baqh">Inferences</td>
  </tr>
</table>

<br>

and a simple Semantic comparison would be something like :

<table class="tg">
	<tr >
		<th class="tg-c3ow">Probabilistic Progams</th>
		<th class="tg-c3ow" >Simple Imperative Programs</th>
	</tr>
	<tr> 
		<td class="tg-c3ow"><img src="{{ site.baseurl }}/images/prob.png"></td>
		<td class="tg-c3ow"><img src="{{ site.baseurl }}/images/imperative.jpg"></td>
	</tr>
</table>

<br>

Now taking the example of coin toss with a model based reasoning approach, there are two outcomes of a coin toss, a Head or Tail. Now let's assume that the outcome is biased and the biasing function is a constructed off by a given number of variables. Then outcome may be understood as :

<div class="shaky-container" style="overflow-x: scroll;" ><pre class="shaky" >

+-------------+      +-------------------------+  
|             |      |                         | 
| variables --+------+-&gt; Biasing function      |
+-------------+      +-----------+-------------+   
                                 |
                                 |
                            +----+-------+
                            |    |       |
                            | Outcome    |
                            +------------+     
</pre></div>

<br>

We know that the likeliness of happening of an event is attributed to its Probability Distribution Function (PDF). We can asses a certain kind of outcome by <u>querying</u> and <u>Observing</u> the Probability Distribution.





syntactical analysis.

<hr>

#### References :

- [Algorithmic Determinism & limits of AI](https://medium.com/@drpolonski/algorithmic-determinism-and-the-limits-of-artificial-intelligence-d32397b8f618)
- [Probabilistic Programming - MS Research](http://delivery.acm.org/10.1145/2600000/2593900/p167-gordon.pdf?ip=103.37.200.227&id=2593900&acc=ACTIVE%20SERVICE&key=045416EF4DDA69D9%2EFF729110AC6131B9%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1565167106_0d17d94e423b06a716de3857520bb149)
- [An introduction to probabilistic programming](https://arxiv.org/pdf/1809.10756.pdf)
- [MIT News](http://news.mit.edu/2019/ai-programming-gen-0626)
- [On Abstraction of Probabilistic Systems](https://link.springer.com/chapter/10.1007/978-3-662-45489-3_4)
- [Semantics of Probabilistic Programs - Kozen](https://www.sciencedirect.com/science/article/pii/0022000081900362)
- [Semantics for probabilistic programming: higher-order functions, continuous distributions, and soft constraints](https://arxiv.org/pdf/1601.04943.pdf)