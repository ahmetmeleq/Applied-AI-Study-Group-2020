
### Homework 2

- This homework will make you familiar with existing scraping tools, using them to scrape an NLP dataset from web. 

- It will optionally make you familiar with state of the art Natural Language Generation architecture and some niche Natural Language Processing tools such as the attention mechanism. This is a quite valuable kind of knowledge today.

- We will take a text dataset (a.k.a. corpus. corpus means a list of documents, like a list of articles) and we will train a network that is able to generate such text that, the generated text is indistinguishably similar to the example documents (articles) in the dataset. We will need to construct a vocabulary to input our strings to the model as one hot vectors. (and our one hot vectors will be embedded by the first layer of the network)

- Note that this homework is not a liability, instead it is only to benefit your skills. Hard is fun :)



Preperations: Scraping Data and trying to understand the Architecture:

1- Use a specialized scraping tool for your task. One example is this newspaper scraping tool, it is a good and easy one to work with, you can try it on some news sites: https://github.com/codelucas/newspaper

2- Once you scrape the text data, you need to prepare your data just as we did in class. Declare a list, fill it with document (article) instances and consider each of the documents as one training example. 

3- There are different approaches for this problem. We will use the Character based Transformer to be on the same page as the study group. It is a highly valuable study to implement such network since it is quite new and technically advanced.

(... to be added steps that describe the exact coding process)

7- Setup your model. Either:

	a- Download a ready-to-use network, which has a further training mode (to train it in your turkish corpus)
	b- Setup your own transformer network, simply by stacking some layers in the right way. The architecture is based on an encoder-decoder structure. Links and help that will guide you will be provided.

8- You can think of the encoder as the part that we downsample (that we reduce the dimensions, the down part on the image link) and the decoder as the part that we re-construct the data (up part on the image link). Here is the image link to explain it on convnets (u-net architecture): https://miro.medium.com/max/936/1*dKPBgCdJx6zj3MpED3lcNA.png

(... further explanation will be put)




To understand encoder-decoders: https://medium.com/@keremturgutlu/semantic-segmentation-u-net-part-1-d8d6f6005066

To understand transformers (high-level overview): https://medium.com/inside-machine-learning/what-is-a-transformer-d07dd1fbec04

To understand transformers (more low-level, technical): http://jalammar.github.io/illustrated-transformer/

Transformer XL: https://towardsdatascience.com/transformer-xl-explained-combining-transformers-and-rnns-into-a-state-of-the-art-language-model-c0cfe9e5a924

