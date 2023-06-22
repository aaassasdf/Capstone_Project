#Objective

Transformer is widely used in recent years. It is good at solving seq2seq problem sets and is mainly applied in the NLP field. The idea of this project is to treat the order of products being put in the basket as a "Sentence". 

By extracting the relationship of the product (word) orders in the basket (sentence). We should be able to predict or provide relevant product recommendations according to all user's buying habits. 

This means if product a,b,c,d,e is being put in the basket with a certain order(e.g. b,d,a,e,c| c,b,d,a,e | e,a,c,b,d ...), we should be able to make a good guess on what product will be put in the basket according to the products already existing in the basket. 

For example, we can tell d would be put in the basket if b is being collected.

# Data Preprocessing

After analyzing the data, we discover that most of the users are not going to buy more than 20 products in a single transaction. Therefore, our basket size can be reduced to 20 based.

And then, in order to further reduce the data size, we filter out the products that are not in top k sales. The top 1999 products are included in ~66% of transactions. Which can be significant to represent the whole data.

Then, we can further reduce our basket size according to this ratio.

the shape of the created dataset is [basket_size,nunmber of baskets]

Pytorch defines the data input must be in shape [batch_size,basket_size]. Therefore, we need to transpose the created dataset into [number of baskets, max_len] and then sample it. The batch_size is bptt in this project with value = 512.

# Current result (incomplete)

the transformer keeps predicting the same sequence no matter what the input is. Please feel free to comment and point out the wrong parts.

# Credit

the model implementation follows the video: https://www.youtube.com/watch?v=M6adRGJe5cQ by Aladdin Persson

and thank you Avishek Majumder for the guidance and tutoring.
