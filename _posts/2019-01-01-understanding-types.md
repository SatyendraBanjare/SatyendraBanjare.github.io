---
layout:     post
comments:   true
title:      Understanding Types
date:       2019-01-01 11:21:29
summary:    More formal application of Types.
categories: plt
keywords: type theory types haskell typesystem logic system early works
---

This post should serve as a basic mathematical introduction of type theory for people new to types or even a functional language programming.

Let's start from the programming perspective, types are fundamentally important aspect of designing any program behaviour. Both Imperative and functional languages provide the feature of self-defining the types. In 'C' , you can perform this using `typedef` . Taking Haskell as an example, the type structure is found to be a bit 'conventionally' different. For example, defining a circle data type this way 

```Haskell
data Shape = Circle Float Float Float
```
would produce this type definition : 

```bash
ghci> :t Circle  
Circle :: Float -> Float -> Float -> Shape 
```
This definition reads that circle has parameters float, float and float.This is a very basic examples and this is extended to defining type classes as well.

Lets get back to mathematical relevance of this. The broader area is called type theory. Type Theory is closely related to and is often served as the basis of modern computer’s type systems, which are a programming  language  feature for common bug reduction.

A computer’s typesystem is essentially a logic system. The logic system's use is to derive a conclusion based in some given constraints called rules, the immediate level to which final conclusion depends on basic/earliest rules of derivation defines that logic systems complexity and we say that more complex system as higher order logic systems.

Simplest understanding of types suggest that all operations (programming logic operations and mathematical operations) must happen in a type safe envirionment between terms of similar types. Having said that the other thing that comes to our mind is type modification. Clearly, the signature of differnt function objects contribute to making a new object with differnt signature. This modification in mathematics is carries out using what is called as **Lambda-Calculus**. That is a whole another story but the thing to consider is that it helps in fast reduction of signature-wise complex terms.

The bifurcations in this field result from the type system used. Briefly these are :
- Dependent Types : A dependent type is a type that depends on a term or on another type. Thus, the type returned by a function may depend upon the argument to the function. 
- Equality Types : Many systems of type theory have a type that represents equality of types and of terms.
- Inductive Types : A system of type theory that requires some basic terms and types to derive the later relations on. 

## Current Areas of Research

- Homotopy Type theory
- Proof Assistants
- Developing Type system for new Programming languages 