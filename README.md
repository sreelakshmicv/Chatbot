# CHATBOT

![th](https://user-images.githubusercontent.com/98879587/183256618-53de0d29-a6d8-4f01-a6c3-ffc62f8fb748.jpg)



**PROBLEM STATEMENT**

Building a seq2seq chatbot with attention mechanism using cornel movie dialogue corpus data.Here we use LSTM model.
Generally it is a question answer problem.

**ABOUT DATASET**

I downloaded my dataset from kaggle . I use the cornel dialogue corpus dataset.
This corpus contains a metadata-rich collection of fictional conversations extracted from raw movie scripts:

- 220,579 conversational exchanges between 10,292 pairs of movie characters
- involves 9,035 characters from 617 movies
- in total 304,713 utterances

- movie metadata included:
	   - genres
	   - release year
	   - IMDB rating
	   - number of IMDB votes
	   - IMDB rating
	   
- character metadata included:
	   - gender (for 3,774 characters)
	   - position on movie credits (3,321 characters)

The corpus contains:
- movie_titles_metadata.txt
- movie_characters_metadata.txt
- movie_lines.txt
- movie_conversations.txt

For this project I choose movie_conversations.txt and movie_lines.txt.

In all files the field separator is " +++$+++ "

- movie_lines.txt
	   - contains the actual text of each utterance
	- fields:
		 - lineID
		 - characterID (who uttered this phrase)
		 - movieID
		 - character name
		 - text of the utterance

- movie_conversations.txt
	   - the structure of the conversations
	- fields
		 - characterID of the first character involved in the conversation
		 - characterID of the second character involved in the conversation
		 - movieID of the movie in which the conversation occurred
		 
I also downloaded a glove dataset  to perform glove embedding.

**TOOLKIT**

1. Before performing the model I just did some kind of EDA and data preprocessing.
For this I use nltk.It (Natural Language Toolkit) Library is a suite that contains libraries and programs for statistical language processing. It is one of the most powerful NLP libraries, which contains packages to make machines understand human language and reply to it with an appropriate response.

2. I have used the above mentioned datasets and I use a simple seq2seq2 model.
Sequence to Sequence (often abbreviated to seq2seq) models is a special class of Recurrent Neural Network architectures that we typically use (but not restricted) to solve complex Language problems like Machine Translation, Question Answering, creating Chatbots, Text Summarization, etc.


![0_iDgmgGnrzq65dPXy](https://user-images.githubusercontent.com/98879587/183256712-dc620afb-0d69-4335-85fc-b46fc723912d.jpg)

The seq2seq model is an architecture based on the multiple LSTM network or sometimes a GRU,Here i use LSTM.Under the hood the model comprises two main components: encoder and decoder. These components are responsible for summarizing the information into fixed length vectors through a bottleneck and then predict the target words from that fixed length vector.

![unnamed](https://user-images.githubusercontent.com/98879587/183256979-312decc0-f6cf-43d7-8674-24495756e8d1.png)

**ENCODER**

The encoder of the network takes in the input sequence one element at a time and produces a vector called the context vector. This context vector aims to preserve the vital information for all the elements in the input sequence so that the decoder can make accurate predictions. 
As new information or words are sequentially fed into the encoder, the context vector is updated. 

![unnamed (1)](https://user-images.githubusercontent.com/98879587/183257077-0c03bf99-fac8-43cc-84fa-52a46703a71f.png)

**DECODER**

The decoder of the network takes in the final context from the encoder into the first layer of the network and starts predicting the target or the output sequences one element at a time. 

![unnamed-2](https://user-images.githubusercontent.com/98879587/183257184-90847c13-9ea2-47f4-9754-c660795205fc.png)

In our project we also implement an attention mechanism. we are considering all the hidden states from each input element we need a special context vector that not only captures important information from those hidden states but also removes unnecessary information. In other words, we want our model to focus on the important features and representations. 

**Seq2Seq MODEL FRAMEWORKS AND TOOLS**

Deep learning frameworks and library:
1. Pytorch
2. Keras
3. Tensorflow
4. Transformer by Huggingface
5. Spacy


Libraries to fetch data:
1. Sklearn
2. Tensorflow Text


I use keras,tensorflow libraries and sklearn to fetch the datas.

**INSTALLATION**

To run this code in your local system you have to download this repository using-
Git clone https://github.com/sreelakshmicv/Chatbot

Now open the downloaded directory and install the required python packages using-
pip install -r requirements.txt

Now open CHATBOT.ipynb and run all the cell.

**TRAINING AND EVALUATION**

I have used my local system to run this model.

LAPTOP-FOH9E19Q

Intel(R) Core(TM) i3-7020U CPU @ 2.30GHz   2.30 GHz

**FURTHER MODIFICATIONS**

Here I attached attention layer but because of some kind of running issues this attention mechanism is not perfect.so in future it can be modified by using some other model and we get more accuracy than this model.




**AUTHOR**

SREELAKSHMI CV

