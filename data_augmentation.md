---
layout: default
---

## NLP Data Augmentation

Data augmentation in NLP is a rather troublesome task, however, it is possible to augment a dataset containing sentences using a translator such as Google Translate. Process is quite simple: Translate the sentence into another language from the base then translate back, e.g. EN -> DE -> EN. This will replace certain words in the sentence with other words of equal meaning.

For example:

* Original Sentence

> Wikipedia is full of fools. Who takes money and makes people work for free? Wikipedia!!! You might as well ban me, > you fool. What's taking so long? Wiki is a stupid place, it's Jimbo's Cult.

* Sentence After Translation

>Wikipedia is full of dumbbells. Who takes money and lets people work for free? Wikipedia !!! You could ban me, you >idiot. What does it take so long? Wiki is a stupid place, it's Jimbo's Cult.

[googletrans](https://pypi.org/project/googletrans/) for python can be employed to do this task in bulk.

* Credits goes to Mr. Pavel Ostyakov at [Kaggle.](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/discussion/48038)

[Back]({{ site.url }}/)
