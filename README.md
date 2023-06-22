# Capstone Project: E-commerce Recommendation System

This project is focusing on Basket Completion, which aims to promote users to finish their incompletion transaction due to actions such as reminder e-mails, discounts, etc.

Please refer to the preprocessing.ipynb for the data pre-processing and datasets preparation

# Open train_dataset.zip, validation_dataset.zip and test_dataset.zip

Due to the large size of the dataset. It is recommended to open it with the following method:

zf = ZipFile('train_dataset.zip') 

train_df = pd.read_csv(zf.open('train_dataset.csv'))

# Data Preprocessing

After analyzing the data, we discover that most of the users are not going to buy more than 20 products in a single transaction. Therefore, our basket size can be reduced to 20 based.

And then, in order to further reduce the data size, we filter out the products that are not in top k sales. The top 1999 products are included in ~66% of transactions. Which can be significant to represent the whole data.

Then, we can further reduce our basket size according to this ratio.

the shape of the created dataset is [basket_size,nunmber of baskets]

Pytorch defines the data input must be in shape [batch_size,basket_size]. Therefore, we need to transpose the created dataset into [number of baskets, max_len] and then sample it. The batch_size is bptt in this project with value = 512.

# Credit

the model implementation follows the video: https://www.youtube.com/watch?v=M6adRGJe5cQ by Aladdin Persson

and thank you Avishek Majumder for the guidance and tutoring.
