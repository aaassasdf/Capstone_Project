# Capstone Project: E-commerece Recommedation System

This project is focusing on Basket Completion, which aims to promote users to finish their incompletion transaction due with actions such as reminder e-mail, discount etc.

Please refer to the preprocessing.ipynb for the data pre-processing and datasets preparation

#Open train_dataset.zip, validation_dataset.zip and test_dataset.zip

Due to the large size of the dataset. It is recommended to open it with the following method:

zf = ZipFile('train_dataset.zip') 

train_df = pd.read_csv(zf.open('train_dataset.csv'))

