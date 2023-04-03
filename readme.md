# Product category classification
## by Said Kamalov s.kamalovwork@yandex.ru

This project works with text data provided by Kazan Express. Before running ipynb files, make sure to download datasets to *data* directory.
All data (text and images) can be found [here](https://drive.google.com/drive/folders/1a1OwG0gUEovQLiMSIfiSHA2g3DsZ62P0).

## Project structure:
Project consits of two main directories:

First, *data* directory contains initial datasets in *parquet* format. Moreover, intermediate files with features in different formats will be also stored there.

Second, *src* directory consists of executable *ipynb* files. To run the project and obtained final results, execute them according **Execution flow plan**. Also file with final results 'result.parquet' is stored there.

## Execution flow plan:
1. First file to execute is 
   <span style="color: green">./src/data-view.ipynb</span>.
    In tihs file train and test datasets are stored as pandas datagrames and then 'text-fields' coulmn is splitted into
    'title', 'description' and 'attributes'. Both modified frames are stored as pickles for further encoding.
2.  Then 
    <span style="color: green">./src/text-to-features.ipynb</span> should 
    be executed. In this file text from train and test datasets is incoded to numerical features with 'bag of words' techniques. Matrices with numerical features are stored in npy files, and later will be used for model training and evaluating the model.
3. In the end, 
   <span style="color: green">./src/model-training.ipynb</span> 
   should be executed. This file contains hyper-parameter tunning, model training, model evaluation and evaluation of obtained result.

   Trained model is saved in <span style="color: green">./src/svc.sav</span>