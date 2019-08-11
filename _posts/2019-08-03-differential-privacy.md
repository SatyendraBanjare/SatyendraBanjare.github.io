---
layout:     post
comments:   true
title:      Differential Privacy
date:       2019-08-03 11:21:29
summary:    Explainatory blog on differential privacy with real world examples 
categories: plt
keywords: Differential Privacy security databases big data Linkage Attacks, Risk Anonymity, De-anonymization. epsilon systems, data security
---

> “<u>Privacy means people know what they’re signing up for, in plain language, and repeatedly. I believe people are smart. Some people want to share more than other people do. Ask them.</u>” – Steve Jobs

As the world becomes more and more data driven, there is even more growing need of more secure systems to carefully meet the objectives of all the participants. There is a security and privacy need of every form, starting from a secure form response submission to data anonymization, there is work required in almost every area. In this blog we will discuss on a particular kind of attack called **Linkage Attacks** and the role of **Differential Privacy** methods to overcome them. Consequently we will try to extend the idealogy for differentially private programs.

<hr>

Differential Privacy is a <b><i>probability based</i></b> concept of guaranteeing the data anonymization upon its usage for analysis. This <i>Data Anonymization</i> is a security technique that is used to preserve sensitive data. It states that addition of one more data point to the dataset would be <i>differntially</i> insignificant to the net inference drawn. This measure of insignificance is often measured in terms of what is called **Privacy Budget**. At times Differential Privacy is also understood as providing only specific information or rather incomplete information. This however may not be true. An anonymized dataset may  contain all the information and still being differentially private. 

<img src="{{ site.baseurl }}/images/diffpriv/diffpriv.jpg" style="height: 220px;width: auto;">

<div style="border: thin black;border-style: dashed;padding: 5px;">
It is studied mostly for large datasets. On small datasets this kind of privacy may not be achieved. Also its been proved that if used, this method is totally cost ineffective for small datasets.
</div>

<br>

The way this method works is by adding noise <b><i>evenly</i></b> to raw data in such a way that the overall probability distribution is not affected. The noise addition is done by using some randomization algorithms. These algorithms are consequently probabilistic and statistical. A very good discussion on this topic can be found here [Privacy Book](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf). The development of these randomization algorithms is a hot research topic.

The anonymization achieved by usage of randomization algorithms can be generalized into two forms :

- **Local Privacy** : 

<img src="{{ site.baseurl }}/images/diffpriv/dplocal.jpg">

- **Global Privacy**

<img src="{{ site.baseurl }}/images/diffpriv/dpglobal.jpg"> 

privacy budget.  \\( \epsilon \\) 

<img src="{{ site.baseurl }}/images/diffpriv/diffpriv2.jpg">


the netflix prize challenge & taxi dataset example.

applications and where is it used. - apple & google.



<hr>

### Differentially Privacy in Computer Programs

<hr>

### Formal Verification Techniques and Differential Privacy

Works

<hr>

### Differential Privacy in Deep Learning

https://ai.google/research/pubs/pub45428

<hr>

## References

- [Algorithmic Foundations of Differential Privacy](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf)
- [CS5436 - Cornell](http://www.cs.cornell.edu/~shmat/courses/cs5436/anonymization.pdf)
- [Robust De-anonymization of Large Datasets (How to Break Anonymity of the Netflix Prize Dataset)](https://arxiv.org/pdf/cs/0610105.pdf)
- [USENIX Enigma 2018 - Differential Privacy at Scale: Uber and Berkeley Collaboration](https://youtu.be/pk_DCSUayDA)
- [Uber - SQL differntial privacy](https://github.com/uber/sql-differential-privacy)
- [Chorus - Differential Privacy via Query Rewriting](https://arxiv.org/pdf/1809.07750.pdf)
- [RAPPOR - Google](https://github.com/google/rappor)
- [Differential Privacy - Apple](https://www.apple.com/privacy/docs/Differential_Privacy_Overview.pdf)