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
___il conduisait la visiter voiture jaune <br>
___he was driving the yellow car <br>
not bad... let's try a couple of more epochs with a GPU! - AWS!
* Train in AWS: 6epochs, 512b, lr0.005;256rnn*2<br>
__il a vu un vieux camion jaune <br>
__he saw a old yellow truck<br>
Perfect! 

## Feecback

**Text_to_ids**<br>

You can make your code a little more elegant by using list comprehension. You can achieve the same results by doing something like this

```
source_id_text = [ 
        [source_vocab_to_int[word] for word in sentence.split()] for sentence in source_text.split('\n')]
target_id_text = [
        [target_vocab_to_int[word] for word in sentence.split()] + [target_vocab_to_int['<EOS>']]
        for sentence in target_text.split('\n')] ''' 
```
**encoding_layer**<br>
To know more about LSTM and RNN, please follow following links (explained very clearly)
http://karpathy.github.io/2015/05/21/rnn-effectiveness/

**decoding_layer_infer**<br>
The function decoding_layer_infer is implemented correctly.<br>
Important!!!!!!!!<br>
You should never use dropout at the time of inference. It won't make much difference in this case as keep_prob is set to 1 during inference, otherwise it can seriously degrade the network's performance.

Inference is very different from training, here's a nice article from nvidia on inference vs training.
https://blogs.nvidia.com/blog/2016/08/22/difference-deep-learning-training-inference-ai/

**seq2seq_model**
Here's an interesting blog post on sequence to sequence learning.
http://suriyadeepan.github.io/2016-12-31-practical-seq2seq/


**parameters** <br>
Suggestion<br>
The idea here is to save some space without losing too much language information. There are roughly ~227 unique words in this dataset -- common embeddings use the number of unique words. By using embedding size 256 you're not saving any space. Try using 128 or 200.<br>
You can read more about embeddings in tensorflow here.
https://www.tensorflow.org/programmers_guide/embedding
Rest everything is fine :smile:


## Material used for learning & creation of the project: 
* udacity deep learning foundation nanodegree Unit 4 RNN - Lesson 10L Sequence to Sequence exercise =) The requirements were very similar to this project and it was a very good guide for the complition of the project! Thank you udacity =) 