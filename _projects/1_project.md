---
layout: page
title: Alignment Research Paper
description: Jonathan Choi's ISMIR 2024 Paper
img: 
importance: 1
category: Research
<!--related_publications: einstein1956investigations, einstein1950meaning-->
---


<div class="caption" style="text-align: left">
This project page is a simplified version of the full paper. The full paper wil be posted soon.<br><br>
<strong><u>Introduction:</u></strong><br>
Alignment is used for many situations such as aligning different instrumental parts or trying to locate a certain section of a full audio. Harmonics are considered a prevalent feature in music but many alignment methods don’t take harmonics into account when they align musical pieces. Alignment with harmonics holds the promise of improving alignment methods. This approach is specifically for aligning piano parts with full music mixes that include violin and cello parts.
<br><br> <strong><u>Some terms to take a note of:</u></strong><br>
<strong>BERT model architecture:</strong> (Bidirectional Encoder Representations from Transformers) : pre-trained language model that captures contextualized word representations. In this research, the BERT model architecture represents musical information and captures the context and relationships between the musical elements. <br><br>

<div class="caption">
<img src="https://miro.medium.com/v2/resize:fit:876/0*ViwaI3Vvbnd-CJSQ.png" alt="bert" width="500"/><br>
</div>

<div class="caption" style = "text-align: left">
<strong>Cross Entropy Loss:</strong> Common loss function used in machine learning(Log loss). Measures the performance of a classification model whose output is a probability value between 0 and 1. Cross-entropy loss increases as the predicted probability diverges from the actual label. <br><br>
</div>

<div class="caption">
<img src="https://assets-global.website-files.com/5d7b77b063a9066d83e1209c/63d2878f8b9a1378924ba771_Formula-9.webp" alt="bert" width="500"/><br>
</div>
<br>

<div class="caption" style = "text-align: left">
<strong>Dynamic Time Warping(DTW):</strong> Compared and aligned sequences with different lengths. Using DTW as a point of reference to other methods used in the paper.<br><br>
</div>

<div class="caption" style = "text-align: left">
<strong>Music Source Separation (MSS)</strong>A method used to separate a full audio piece into different audio parts. We use this method to test the feasibility of learning harmonics. <br><br>
</div>

<div class="caption">
<img src="https://source-separation.github.io/tutorial/_images/source_separation_io.png" alt="bert" width="500"/><br>
</div>

<strong> HPTSM:</strong> A method that stretches an audio clip to fit a different audio. 
</div>




<div class="caption">
Left Image --> Helps to Visualize the First Part described in the <strong>Methodology</strong> <br>
Right Image --> Helps to Visualize the Second Part described in the <strong>Methodology</strong>

</div>
<strong><u>Overview of the Project:</u></strong><br>


<strong><u>Methodology:</u></strong><br>
<strong>Dataset:</strong> The dataset includes MP3s and annotations of full mixes and individual parts for the piano, cello, and violin. (Name: PianoTrioAlignment Dataset)
<br><br>

<strong> First Part:</strong><br>
To test if learning harmonics is possible we used Music Source Separation(MSS) and HPTSM from pytsmod. First, we separated the full mix using MSS into a piano part. Then we do HPTSM with the original piano mp3. We then get the outputted audio and test if the audio was aligned correctly. (Modeled in Image Below)
<br><br>
<strong>Second Part:</strong><br>

To learn the harmonics, we put a fullmix through BERT. Then we do Cross Entropy loss with the BERT model’s output with a DTW between the fullmix and piano piece. Then we train the model by using the data and passing it through BERT while doing MSE-loss(Cross Entropy). For results, we compared the output of the fullmix with the corresponding piano part by using DTW and logging the value
<br><br>
<strong><u>Final Result Values:</u></strong><br>

|Regular DTW|Bert Model|MSS +HPTSM|
|:----:|:----:|:----:|:----:|
|69137|72715|54436|

<br>
<div class="caption">
<u>The lower the value: The better aligned</u>
</div>

<strong><u>Results Explained:</u></strong><br>
<strong>After training on 4 different audio clips, the effectiveness of the proposed methods is shown in the table above. The MSS is confirmed to be successful meaning that the possibility of learning harmonics is possible. With the current model, there is not enough data for it to learn to the extent of surpassing regular DTW. However, the Music Source Separation model serves as evidence that the proposed method with the BERT model can improve alignment. With more data, the BERT model will learn alignment methods with the use of harmonics.</strong><br>

<strong><u>Conclusion:</u></strong><br>
After looking at the results, alignment with the use of harmonics is possible and better than using regular DTW. With harmonics, alignment is improved. No other artifical intelligence model has ever used harmonics with alignment unlike this paper. With a little more training, the BERT model will be able to align better than DTW (We know this because we used MSS as evidence). The next step to the paper is for other alignment methods to use harmonics to see how much their models improve by. 
