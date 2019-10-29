---
layout: post
title:  "Code Sense (basic): A good IF is a balanced IF"
date:   2019-04-18 08:45:54 -0700
categories: code-sense basic
---

## Terminology

{% highlight python %}
if condition_a:
  # THEN branch
else:
  # ELSE branch
{% endhighlight %}

## Good Code should look like

Typical IF statement:

{% highlight python %}
if condition_a:
  # Handle the case where Condition A is met
else:
  # Handle the case where Condition A is not met
{% endhighlight %}


Early exit is a special form of balanced IF.

{% highlight python %}
if error_condition:
  return
# normal condition logic

{% endhighlight %}


## Ugly Code looks like

{% highlight python %}
if condition_a:
  # Handle the case where Condition A is met
# Possible bug: did not handle the case where Condition A is not met
{% endhighlight %}


## The logic behind a balanced IF statement

Looking at Software Engineering Axiom 2: "Software is correct if and only if it behaves correctly in all permitted input, environment and dependency responses."

The two branches of an IF statement represents two situations.
The THEN branch should produce the desired behavior where the condition is met.
The ELSE branch should produce the desired behavior where the condition is NOT met.

Therefore only if you have logic handling both branches in an IF statement, your code could even have a chance of producing correct behavior in all possible situations, and therefore, have a chance of being correct.
