---
layout: default
title: PLT
permalink: /plt/
tags: plt
---

<h1>Programming Languages Theory</h1>

Here are some of my experiences and findings on the topics 
[Functional-Programming](https://en.wikipedia.org/wiki/Functional_programming),	
[type-theory](https://en.wikipedia.org/wiki/Type_theory),
[proof-assistants](https://en.wikipedia.org/wiki/Proof_assistant) and related fields.

<h2>Readings</h2>

<div style="overflow-x:auto;">
<table id="plt-table" style="width:100%">
  <tr>
  	<th>Name/Topic</th>
    <th>Description</th>
    <th>Link(s)</th> 
    <th>Other Link(s)</th>
  </tr>
  <tr>
  	<td>Type Theory Notes</td>
    <td>I have been reading about Type theory, logic systems and Proof Assistants these days and thus compiled a short report on the same. It is avilable here</td>
    <td><a href="https://github.com/SatyendraBanjare/Type-Theory-notes">type theory notes</a></td> 
  </tr>
  <tr>
    <td>Software Foundations</td>
    <td>I have almost solved first part, Logic foundations of the 4 volume Software foundations book. My solutions are available here at: </td>
    <td><a href="https://github.com/SatyendraBanjare/software-foundations">My Software Foundations Solutions link</a></td> 
  </tr>
  <tr>
    <td>Interactive Theorem Proving</td>
    <td>I finished reading up Interactive Theorem Proving by Prof. Adam Chlipala <a href="http://adam.chlipala.net/itp/">slides</a> 
    	 and also compiled small notes on the same which can be found here at :
    </td>
    <td><a href="https://github.com/SatyendraBanjare/itp">ITP Solutions link</a></td> 
  </tr>
  <tr>
  <td>Abstract Interpretation</td>
    <td>I was reading about Abstract Interpretation,following this <a href="http://web.mit.edu/afs/athena.mit.edu/course/16/16.399/www/">slides</a>  and compiled short notes on the same which can be found here .
    </td>
    <td><a href="https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399">Abstract Interpretation</a></td> 
  </tr>
  <!-- <tr>
	  <td>Understanding Computation</td>
    <td>short compiled notes for this book by XYZ.</td>
    <td><a href="https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399">Abstract Interpretation</a></td> 
  </tr> -->
  <!-- <tr>
	<td>Differential Privacy</td>
    <td>short compiled notes for this book by XYZ.</td>
    <td><a href="https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399">Abstract Interpretation</a></td> 
  </tr>
  <tr>
	<td>Verified Quantum Systems</td>
    <td>short compiled notes for this book by XYZ.</td>
    <td><a href="https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399">Abstract Interpretation</a></td> 
  </tr>
  <tr>
	<td>Verified ML</td>
    <td>short compiled notes for this book by XYZ.</td>
    <td><a href="https://github.com/SatyendraBanjare/MIT-Abstract-Interpretation-16.399">Abstract Interpretation</a></td> 
  </tr> -->
</table>
</div>



<h2>Related blog posts</h2>
{% for post in site.posts %}
  {% capture categories %}{{post.categories }}{% endcapture %}
  {% if categories == "plt" %}
    {% capture year %}{{currentyear}}{% endcapture %} 
  <a href="{{ post.url | prepend: site.baseurl }}" class="post-link"> {{ post.title }}</a> <ran style="color:#aaa;font-size:0.8em;">({{post.date | date_to_string}})</ran>
  {% endif %}   
{% endfor %}

<h2>Related Projects</h2>

{% for project in site.data.projects %}
<ul>
	{% if project.github.plt %}
	<li>
		<a href="{{project.url}}">{{project.name}}</a>
	</li> 
	{% endif %}
</ul>
{% endfor %}

