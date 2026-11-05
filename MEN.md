---
layout: page
title: The MEN Test Collection
description: "A word similarity test collection: 3,000 English word pairs with human-assigned relatedness judgments."
permalink: /MEN/
---

**Version:** 0.2 &middot; **Release date:** April 30, 2012 &middot; **Maintained by:** [Elia Bruni]({{ site.baseurl }}/) ([{{ site.author.email }}](mailto:{{ site.author.email }}))

### Overview

The **MEN Test Collection** contains two sets of English word pairs (one for training and one for testing) together with human-assigned similarity judgments, obtained by crowdsourcing using [Amazon Mechanical Turk](https://www.mturk.com/) via the [CrowdFlower](https://en.wikipedia.org/wiki/Figure_Eight_Inc.) interface. The collection can be used to train and/or test computer algorithms implementing semantic similarity and relatedness measures.

### Description

**Sampling:** The MEN data set consists of 3,000 word pairs, randomly selected from words that occur at least 700 times in the freely available [ukWaC and Wackypedia corpora combined](https://wacky.sslmit.unibo.it/) (size: 1.9B and 820M tokens, respectively) and at least 50 times (**as tags**) in the [opensourced subset](https://www.cs.cmu.edu/~biglou/resources/) of the [ESP game dataset](https://en.wikipedia.org/wiki/ESP_game). In order to avoid picking unrelated pairs only, we sampled the pairs so that they represent a balanced range of relatedness levels according to a text-based semantic score.

**Design and data collection:** Each pair was randomly matched with a comparison pair and rated in this setting (as either more or less related than the comparison point) by a single Turker (hence, there is no well-defined inter-subject agreement). Rather than ask annotators to give an absolute score reflecting how much a word pair is semantically related (like in [Wordsim353](https://gabrilovich.com/resources/data/wordsim353/wordsim353.html)), we instead asked them to make comparative judgements on two pair exemplars at a time because this is both more natural for an individual annotator, and also permits seamless integration of the supervision from many annotators, each of whom may have a different internal "calibration" for the relatedness strengths. Moreover, binary choices were preferred because they make the construction of "right" and "wrong" control items straightforward. In total, each pair was rated in this way against 50 comparison pairs, thus obtaining a final score on a 50-point scale, although the Turkers' choices were binary.

**Instructions:** We did not instruct the subjects about the difference between similarity and relatedness. We used only the second term, and gave examples involving both similarity, that is a special case of relatedness ("car-automobile"), and relatedness ("wheels-car").

**Participants:** We requested participants to be native speakers and only accepted those connecting from an English speaking country. We cannot guarantee that non-natives did not take part in the study, but our subject filtering techniques based on control "gold standard" pairs ensures that only the data of speakers with a good command of English were retained.

**Agreement:** Because raters saw the MEN pairs matched to different random items, with the number of pairs also varying from rater to rater, it is not possible to compute annotator agreement scores for MEN. However, to get a sense of human agreement, the first and third author rated all 3,000 pairs (presented in different random orders) on a standard 1-7 Likert scale. The Spearman correlation of the two authors is at 0.68, the correlation of their average ratings with the MEN scores is at 0.84. On the one hand, this high correlation suggests that MEN contains meaningful semantic ratings. On the other, it can also be taken as an upper bound on what computational models can realistically achieve when simulating the human MEN judgments.

**Files:** The combined set is available in both POS-tagged form (**lemma_form** suffix) and natural form (**natural_form** suffix). The development and testing sets are available in POS-tagged form.

- `MEN_dataset_natural_form_full`: combined set (3,000 pairs), natural form
- `MEN_dataset_lemma_form_full`: combined set (3,000 pairs), POS-tagged form
- `MEN_dataset_lemma_form.dev`: development set (2,000 pairs), POS-tagged form
- `MEN_dataset_lemma_form.test`: testing set (1,000 pairs), POS-tagged form

The first two columns in each file contain word pairs, followed by a column with the (floating-point) human scores. The archive also includes the two authors' Likert ratings (`agreement/`), the instructions shown to raters (`instructions.txt`) and the CC BY 2.0 licence (`licence.txt`).

### Availability and usage

Download the data set as a ZIP or TAR.GZ file:

- [MEN.zip]({{ site.baseurl }}/resources/MEN.zip) (95 KB)
- [MEN.tar.gz]({{ site.baseurl }}/resources/MEN.tar.gz) (87 KB)

If you publish results based on this data set, please cite as:

> E. Bruni, N.K. Tran and M. Baroni. [Multimodal Distributional Semantics](https://jair.org/index.php/jair/article/view/10857). Journal of Artificial Intelligence Research 49: 1-47, 2014.

Please also inform your readers of the current location of the data set: <https://eliabruni.github.io/MEN/>

### Questions

If you have questions or comments, please email me at [{{ site.author.email }}](mailto:{{ site.author.email }}).
