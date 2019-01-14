---
layout: default
---

## NLP Data Augmentation with Thesaurus

This approach relies on replacing words or phrases with their synonyms for data augmentation.
Using a thesaurus, every synonym to a word or phrase is ranked by the semantic closeness to the most
frequently seen meaning. To decide on how many words to replace, all replaceable words are extracted from
from the given text and a set of them are randomly chosen to be replaced. The probability of number
of words to be replaced is determined by a geometric distribution. The index of the synonym chosen 
given a word is also determined by a another geometric distribution. This way, the probability of a 
synonym chosen becomes smaller when it moves distant from the most frequently seen meaning.

* Credits goes to publication: [Character-level Convolutional Networks for Text
Classification](https://papers.nips.cc/paper/5782-character-level-convolutional-networks-for-text-classification.pdf)

[Back]({{ site.url }}/)
