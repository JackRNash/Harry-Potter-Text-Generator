# Harry-Potter-Text-Generator
Experiments in natural text generation using Harry Potter books as the source text

## Viewing the notebook/code
Github seems to struggle to render the notebook, so please use **[this link](https://nbviewer.jupyter.org/github/JackRNash/Harry-Potter-Text-Generator/blob/master/HarryPotter.ipynb)** to view it.

## Purpose
In preparation for a more advanced project using natural language generation, I wanted to investigate different techniques in NLP, get practice applying them, and learn about their pitfalls. I was inspired by Andrew Karpathy's excellent blogpost on the effectiveness of LSTMs at generating somewhat realistic text. The LSTM described in his post was the first one I implemented and works by predicting the next character based on the previous character the model has seen. It's impressive what the model can learn(like the enitre English language) just from looking at the past characters and guessing the next. 
![](http://karpathy.github.io/assets/rnn/charseq.jpeg)
##### Illustration of the character level model courtesy of Karpathy
Unfortunately, there are some severe limitations and the model struggles to form coherent sentences. I then looked at word embeddings, specifically `word2vec` and a more advanced model that first embedded the words and then, similar to the character level model, predicted the next word based on the past words it had seen. Unfortunately this didn't have the performance bump I hoped for and encountered similar pitfalls. I then started investigating state of the art models and saw they revolved around attention. OpenAI's `GPT-2` emerged as a great candidate and I found the wonderful package [gpt-2-simple](https://github.com/minimaxir/gpt-2-simple/) which made finetuning a breeze. This was the only model that could reliably produce coherent sentences and is what I'll use in my future project.

## Example Outputs
#### Character level LSTM

```
Hagrid and Hermione shouted.

"Ouch!" said Madam Pomfrey suspiciously.
```

#### Word level LSTM

```
Harry muttered at the fire.

"The dormitory," said Ron.
```

#### GPT-2

```
"Sometimes I wish I'd knew what the Wizards were all about." Ron's fists were
like lead.

"We're going out now," said Ron, tearing his eyes off another boat. "We're
done for.
```

#### Some silliness
``` 
"Wizard's duel, Round 3," said Ron. He pulled out a toad and paced around
the boy.
"Oh, are you doing Herbology?" he asked Ron excitedly.

Don't with Dobby whispered it inside their heads.
```
