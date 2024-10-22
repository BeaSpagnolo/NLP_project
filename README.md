# Evaluating Model Generalizability for Mental Health detection on Reddit Datasets

This study examines whether different data collection methods on the same platform (Reddit) affect model performance, building on findings that models trained on one platform often perform poorly on another.
To see the files download and extract the NLP_project.zip folder, below you will find a precise description of each folder contents.


## datasets folder

1. **initial_datasets**
   - **depression_MAIN.csv**: First dataset, called MAIN, of Reddit comments on depression used for binary classification.
   - **depression_RSDD.csv**: Second dataset, called RSDD, of Reddit comments on depression used for binary classification.


2. **processing_methods**
   - **data_processing.ipynb**: Techniques to preprocess **depression_MAIN.csv** and **depression_RSDD.csv** datasets from **initial_datasets** folder.   
   - **smote_application.ipynb**: Technique to apply data augmentation on **depression_MAIN.csv** dataset from **initial_datasets** folder.   
   - **Word2vec.ipynb**: Creates a model to apply embedding to the datasets.  


3. **processed_datasets**
   - **processed_depression_MAIN_data.csv**: MAIN dataset pre-processed using **data_processing.ipynb** from **processing_methods** folder.
   - **processed_depression_MAIN_data_SMOTE.csv**: MAIN dataset augmented using **smote_application.ipynb** from **processing_methods** folder.
   - **processed_depression_RSDD_data.csv**: RSDD dataset pre-processed using **data_processing.ipynb** from **processing_methods** folder.

   - **Word2Vec_cbow_model_MAIN**: Model created using **Word2vec.ipynb** from **processing_methods** folder on **processed_depression_MAIN_data.csv** dataset from **processed_datasets** folder.
   - **Word2Vec_cbow_model_MAIN_SMOTE**: Model created using **Word2vec.ipynb** from **processing_methods** folder on **processed_depression_MAIN_data_SMOTE.csv** dataset from **processed_datasets** folder.
   - **Word2Vec_cbow_model_RSDD**: Model created using **Word2vec.ipynb** from **processing_methods** folder on **processed_depression_RSDD_data.csv** dataset from **processed_datasets** folder.


## basic_algorithms folder

- **same_datasets.ipynb**: Applies a random forest and an SVM on **processed_depression_MAIN_data_SMOTE.csv** and **processed_depression_RSDD_data.csv** datasets from **processed_datasets** folder, using train/test split.
- **different_datasets.ipynb**: Applies a random forest and an SVM on **processed_depression_MAIN_data_SMOTE.csv** and **processed_depression_RSDD_data.csv** datasets from **processed_datasets** folder, training on the first one and testing on the second, and viceversa.


## transformer_algorithms folder

- **same_MAIN_BERT.ipynb**: Applies BERT algorithm on **processed_depression_MAIN_data_SMOTE.csv** dataset from **processed_datasets** folder, using train/test split.
- **same_RSDD_BERT.ipynb**: Applies BERT algorithm on **processed_depression_RSDD_data.csv** dataset from **processed_datasets** folder, using train/test split.
- **same_MAIN_MentalBERT.ipynb**: Applies MentalBERT algorithm on **processed_depression_MAIN_data_SMOTE.csv** dataset from **processed_datasets** folder, using train/test split.
- **same_RSDD_MentalBERT.ipynb**: Applies MentalBERT algorithm on **processed_depression_RSDD_data.csv** dataset from **processed_datasets** folder, using train/test split.

- **different_datasets_BERT_train_MAIN.ipynb**: Applies BERT algorithm, training on **processed_depression_MAIN_data_SMOTE.csv** and testing on **processed_depression_RSDD_data.csv** datasets from **processed_datasets** folder.
- **different_datasets_BERT_train_RSDD.ipynb**: Applies BERT algorithm training on **processed_depression_RSDD_data.csv** and testing on **processed_depression_MAIN_data_SMOTE.csv** datasets from **processed_datasets** folder.
- **different_datasets_MentalBERT_train_MAIN.ipynb**: Applies MentalBERT algorithm, training on **processed_depression_MAIN_data_SMOTE.csv** and testing on **processed_depression_RSDD_data.csv** datasets from **processed_datasets** folder.
- **different_datasets_MentalBERT_train_RSDD.ipynb**: Applies MentalBERT algorithm training on **processed_depression_RSDD_data.csv** and testing on **processed_depression_MAIN_data_SMOTE.csv** datasets from **processed_datasets** folder.


## how to use it

A. to apply basic algorithms 

   1. Download **depression_MAIN.csv** dataset and **depression_RSDD.csv** dataset from the **initial_datasets** folder. 
   2. Run the **data_processing.ipynb** on both datasets to create **processed_depression_MAIN_data.csv** and **processed_depression_RSDD_data.csv** datasets.
   3. Run the **smote_application.ipynb** on **processed_depression_MAIN_data.csv** to create **processed_depression_MAIN_data_SMOTE.csv** dataset.
   4. Run **Word2vec.ipynb** on **processed_depression_RSDD_data.csv** and **processed_depression_MAIN_data_SMOTE.csv** to create **Word2Vec_cbow_model_MAIN_SMOTE** and **Word2Vec_cbow_model_RSDD** models.
   5. Run **same_datasets.ipynb** and **different_datasets.ipynb** from **basic_algorithms folder** to obtain final results.


B. to apply trasformer algorithms 

   1. Download **depression_MAIN.csv** dataset and **depression_RSDD.csv** dataset from the **initial_datasets** folder. 
   2. Run the **data_processing.ipynb** on **depression_MAIN.csv** to create **processed_depression_MAIN_data.csv** dataset.
   3. Run the **smote_application.ipynb** on **processed_depression_MAIN_data.csv** to create **processed_depression_MAIN_data_SMOTE.csv** dataset.
   4. Run **same_MAIN_BERT.ipynb**, **same_RSDD_BERT.ipynb**, **same_MAIN_MentalBERT.ipynb**, **same_RSDD_MentalBERT.ipynb**, **different_datasets_BERT_train_MAIN.ipynb**, **different_datasets_BERT_train_RSDD.ipynb**, **different_datasets_MentalBERT_train_MAIN.ipynb** and **different_datasets_MentalBERT_train_RSDD.ipynb** from **transformer_algorithms folder** to obtain the final results.


**Note**: Check to use correct datasets paths in the different notebooks.

**results.xls**: In this file are reported summaries of the results.



