
### Homework 2

- This homework will make you familiar with existing scraping tools, using them to scrape an NLP dataset from web. 

- It will optionally make you familiar with the niche details of Natural Language Generation and Natural Language Processing in general, such as the attention mechanism. This is a quite valuable kind of knowledge for today's data scientist.

- We will take a text dataset (a.k.a. corpus. corpus means a list of documents, like a list of articles) and we will train a network that is able to generate such text that, the generated text is indistinguishably similar to the example documents (articles) in the dataset.

- Copy-paste is worse than non-submission. (just dont copy paste code that is: written by someone else to do this homework)

- Note that this homework is not a liability, instead it is only to benefit your skills. It is also fun :)



Steps:

1- Use a specialized scraping tool for your task. One example is this newspaper scraping tool, it is a good and easy one to work with: https://github.com/codelucas/newspaper

2- Once you scrape the text data, you need to prepare your data just as we did in class. Declare a list, fill it with document (article) instances and consider each of the documents as one training example. (only for now)

3- There are different approaches, however, character based models (most popular character based model nowadays is called Transformer) are arguably more suitable to work with, in this task.

4- To use a character based model, put a "beginning of sentence" token and "end of sentence" token at the beginning of each document. This way, your model knows how a document starts and how a document ends.

5- Form a giant one document using all the documents you have. This means, aggragate all your preprocessed text in one big string. This will be our corpus (dataset)

6- Form a vocabulary like we did in class. By vocabulary, we mean the one hot encoded versions of each symbol (character) in the text. Remember, size of vocabulary should be the same as the length of your one hot vector. Change the symbols (characters) in the text by the one hot encoded vectors.

7- Setup your model. Either download a ready-to-use network, which has a further training mode (to train it in your turkish corpus); or setup your own model, simply using Embedding and LSTM layers. For a better model, check attention and try that method in your net.

8- Train your model. Your inputs are all of your corpus except the last character in the corpus. Your labels are **your corpus shifted by one character**, meaning they are all of your corpus except the first character in your corpus. Example:

	model.fit(  inputs = corpus[0:-1],
		    outputs = input_corpus[1:] )

	In above, fit method takes all of the characters in the corpus, except the last character, as input.
	Also, fit method takes all of the characters in the corpus, except the first character, as output.
	So each input character is matched with the next character as its label. This way model will learn to find the next character once it takes a character input.
	
	

9- Don't forget to add a randomness factor if you develop your own model architecture! Here are two different ways to introduce randomness: 
	
	First way to introduce randomness to the model: 
		use a random vector as a second type of input at the beginning of the network
		
	Second way to introduce randomness to the model:
		use the variational encoder method, which simply finds the mean and variance values of each independent feature along the batch axis, then samples examples from the gaussian distrion defined by our mean and variance values. (network does this at the bottleneck layer). You can do this operation with functional api of keras!
	

10- So if you modify your fit function according to the first way:
	
	model.fit(  inputs = [corpus[0:-1],randomvecs],
		    outputs = input_corpus[1:] )
		    
	np.shape(randomvecs) >> ( len(corpus), howmany_randomness_units_do_I_want_for_one_character )
	






Please submit your homeworks into the repository as:

	1- form a folder with the names of your team members: person1name_person1surname-'and'-person2name_person2surname
	2- inside the folder: preprocessing.ipynb
	3- inside the folder: model.ipynb
	4- load your pickle files into your google drive, copy the share link, paste the link to our discord channel.



