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

## Linkage Attacks

Linkage attacks are powerful privacy attacks on datasets that unveils identity of private and sensitive data about individuals (like name & address) by *Linking* few pieces of the data points, called **Quasi-identifiers** of one dataset with other datasets. This is just a statistical analysis method and thus one requires only dataset and potentially he/she can recover important data about people no matter how secure the system is. 

One of most common example of such attacks is called **Netflix Prize attack** where a group of researchers were able to uniquely identify **87%** of the US population whose movie ranking statistics were made avilable by Netflix. The combined the data with Census data to achieve this. More information can be found here [Robust De-anonymization of Large Datasets (How to Break Anonymity of the Netflix Prize Dataset)](https://arxiv.org/pdf/cs/0610105.pdf). There are several other examples that are brutul as well as funny, find more information over here [CS5436 - Cornell](http://www.cs.cornell.edu/~shmat/courses/cs5436/anonymization.pdf).

There is a need to minimize privacy risks while maximizing data utility. One way to achieve this is to *anoymize* such Quasi-identifiers. Scientists have thus devised method of Differential privacy to help counter such attacks. 

<hr>

## Differential Privacy

Differential Privacy is a <b><i>probability based</i></b> concept of guaranteeing the data anonymization upon its usage for analysis. This <i>Data Anonymization</i> is a security technique that is used to preserve sensitive data. It states that addition of one more data point to the dataset would be <i>differntially</i> insignificant to the net inference drawn. At times Differential Privacy is also understood as providing only specific information or rather incomplete information. This however may not be true. An anonymized dataset may  contain all the information and still being differentially private. 

<center>
<img src="{{ site.baseurl }}/images/diffpriv/diffpriv.jpg" style="height: 220px;width: auto;">
</center>

<br>

The way this method works is by adding noise <b><i>evenly</i></b> to raw data in such a way that the overall probability distribution is not affected. The noise addition is done by using some randomization algorithms. These algorithms are consequently probabilistic and statistical. A very good discussion on this topic can be found here [Privacy Book](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf). The most common one being **Laplacian Mechanisms** and **Gaussian Mechanisms** can be looked in here [Wiki-link](https://en.wikipedia.org/wiki/Additive_noise_mechanisms). The development of these randomization algorithms is a good research topic.

More Formally, a system is called \\(\epsilon\\)-loss differentially private if, given two datasets A and B differing by only 1 data field, and R be randomization algorithm whose output is query result on the anonymized database.

\\[ Pr(R(A)) \leq e^{\epsilon} * Pr(R(B)) \\]

The anonymization achieved by usage of randomization algorithms can be generalized into two forms :

- **Local Privacy** : The randomization is added to every response during the data generation only. The final database is anonymized. Finally this database is queried upon as wish to one's need. There is supposed to be no backtrack to the true user's response.
	+ It is used by Google in uses this method to collect statics from Chrome. 
	+ [RAPPOR](https://github.com/google/rappor) is developed by google to implement local differential privacy.
	+ Apple uses it to collect emoji usage data of iphone users.

<center>
<img src="{{ site.baseurl }}/images/diffpriv/dplocal.jpg">
</center>

- **Global Privacy** : The randomization is added to the whole raw database created. There is a possible space of data leaks in this case, if there is an access to the raw database.

<center>
<img src="{{ site.baseurl }}/images/diffpriv/dpglobal.jpg"> 
</center>

## Privay Budget  (\\( \epsilon \\) )

There is a tradeoff performed between privacy and accuracy to meet a practical application. The most important caveats of differential privacy technology are :

- The more information is *asked*, more the amount of randomization / noise is required.
- Once an information is leaked, its public forever.

The measure of information leak which is thought of being insignificant is measured in terms of *Privacy Budget*. This is the limit of privacy loss that is allowed for a private database.	Apple uses a privacy budget with \\( \epsilon \\) = 4  for lookup hints and \\( \epsilon \\) = 8 for QuickType. More information can be found here [Differential Privacy - Apple](https://www.apple.com/privacy/docs/Differential_Privacy_Overview.pdf).

<center>
<img src="{{ site.baseurl }}/images/diffpriv/diffpriv2.jpg">
</center>

Upon Adding more data fields, the privacy budget is assumed to be constant but however it is not the case always. The data anonymization is statistically better with more number of data fiels.

For a practical application, it may be understood as max number of queries allowed on a database. Now as number of queries is decided, the total dependence on the noise creation by randomization algorithms can be decided and hence the privacy loss limit be decided too.

<div style="border: thin black;border-style: dashed;padding: 5px;">
It is studied mostly for large datasets. On small datasets this kind of privacy may not be achieved. Also its been proved that if used, this method is totally ineffective for small datasets.
</div>

<hr>

### Programming Language analysis of Differentially Privacy

DP is originally developed by the Cryptography community. People in programming language research community are actively combining ideas of formal analysis to prove the robustness of DP techniques. Research on development of Type system based approach is going on to create *securely private* randomizations by computer programs.

The recent works that I found out are :

- [Fuzzi: A Three-Level Logic for Differential Privacy](https://arxiv.org/abs/1905.12594)
- [Programming language techniques for differential privacy](https://dl.acm.org/citation.cfm?id=2893591)

<hr>

### Differential Privacy in Deep Learning

Application of DP is not only limited to Creating secure Databases. Some researchers at Google have implemented the idea of DP in Deep Learning to demonstrate that we can train deep neural networks with non-convex objectives, under a modest privacy budget, and at a manageable cost in software complexity, training efficiency, and model quality. Paper can be found here : [Deep Learning with Differential Privacy - Ian GoodFellow](https://ai.google/research/pubs/pub45428).

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