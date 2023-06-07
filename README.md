# Amazon India - Product Attribute Extraction
Product attributes, such as brand name, size, weight, or dimension, are critical in e-commerce as they help customers find and select the right product for their needs. However, obtaining, adding, and maintaining these values is extremely labour intensive, especially on larger sites. Therefore we ventured to use 1. SOTA transformer based models like Google's BERT & Facebook's RoBERT, to make Product Attribute Extraction (PAE) and 2. Train question-answering model to predict brand name based on product description. For PAE, we used Bi-LSTM model to create chunkings of proper nouns from description and formulated relationship with the associated non-noun phrases. Using this Parts-of-speech tagging, we identified clusters and based on these we came up with an unsupervised technique to relate a product's attribute name with its attribute value. For brand detection task we modified a question-answering transformer model (DistilBERT) to answer the question 'what is the brand name of this product?' based on the descriptions. After finetuning the model we achieved a desirable accuracy. 

- You can check out the slides for the talk [here](https://docs.google.com/presentation/d/e/2PACX-1vQqUh3kelfdDfnvUef36naGv9JHw_PqY7tQqlTMXnqcpBM2VWa1LT114NfFvOG5yiRcNpcOi3r1cvkq/pub?start=false&loop=false&delayms=3000).
- The Paper for this work can be checked out [here](report/Product-Attribute-Extraction-E-Commerce.pdf)

### Method in Action
*Detection of All Possible Product Attribute unsupervisedly and supervised brand name detection using our method on products listed on Amazon India Website is demonstated in the video below*

https://github.com/RishiDarkDevil/Amazon-PAE/assets/52328147/eac61975-cdc7-44e1-ad68-6bf49845012c

Noun Attribute Search | Non-Noun Attribute Search
-|-
![](interactive-plots/search-noun.png)|![](interactive-plots/search-non-noun.png)

### Brief Overview of the Methodology

Data Cleaning | Chunking
-|-
![](interactive-plots/1.png)|![](interactive-plots/2.png)
Product Attribute Clustering | Cluster Labelling
![](interactive-plots/3.png)|![](interactive-plots/5.png)

Two fine-tuned models related to this work can be found at the HuggingFace Model Hub:
- [DistilBERT fine-tuned for Amazon India Brand Name Detection](https://huggingface.co/Aleron12/distilbert-base-uncased-finetuned-amz_brander)
- [DistilRoberta fine-tuned on Product Titles, Bullet Points and Descriptions from Amazon India](https://huggingface.co/RishiDarkDevil/distilroberta-base-finetuned-amazon-products)
