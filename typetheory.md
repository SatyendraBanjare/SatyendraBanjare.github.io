---
layout: default
title: PLT
permalink: /plt/
tags: plt
---

Here are some of my experiences and findings on the topics 
[Functional-Programming](https://en.wikipedia.org/wiki/Functional_programming),	
[type-theory](https://en.wikipedia.org/wiki/Type_theory),
[proof-assistants](https://en.wikipedia.org/wiki/Proof_assistant) and related fields.

* I have been reading about Type theory, logic systems and Proof Assistants these days and thus compiled a short eport on the same. It is avilable here [Type Theory notes](https://github.com/SatyendraBanjare/Type-Theory-notes).

* I have almost solved first part, Logic foundations of the 4 volume Software foundations book. My solutions are available here at [repo](https://github.com/SatyendraBanjare/software-foundations).

* I finished reading up Interactive Theorem Proving by Prof. Adam Chlipala [course](http://adam.chlipala.net/itp/) and also compiled small notes on the same which can be found here at [repo](https://github.com/SatyendraBanjare/itp) .

* I was reading about Abstract Interpretation,following this [course](http://web.mit.edu/afs/athena.mit.edu/course/16/16.399/www/)  and compiled short notes on the same which can be found here at :  [repo](https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399) . I have tried to implement my abstract interpreter whose code can also be found at the same place.


<h2>Programming Language Theory blog posts</h2>
{% for post in site.posts %}
  {% capture categories %}{{post.categories }}{% endcapture %}
  {% if categories == "plt" %}
    {% capture year %}{{currentyear}}{% endcapture %} 
  <a href="{{ post.url | prepend: site.baseurl }}" class="post-link"> {{ post.title }}</a> <ran style="color:#aaa;font-size:0.8em;">({{post.date | date_to_string}})</ran>
  {% endif %}   
{% endfor %}