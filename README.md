# Project 4: Language Translation (EN2FR)

## Introduction
In this project, you’re going to take a peek into the realm of neural network machine translation. You’ll be training a sequence to sequence model on a dataset of English and French sentences that can translate new sentences from English to French.

## To do: 
* Convert text to IDs 
* Buidl NN 
    * model_inputs 
    * decoder input 
    * encoding/decoding layer 
* Training NN: epochs, batch_size, rnn_size, embedd..., lr. 
* Sentence2Sequence
* Translate: 'he saw a old yellow truck .' => Il a vu un vieux camion jaune.

## Results: 
* Fast training without GPU - 2epochs,512b,lr0.1,16rnn*2.<br>
il conduisait la visiter voiture jaune <br>
he was driving the yellow car <br>
not bad... let's try a couple of more epochs with a GPU! - AWS!
