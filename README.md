# 5153_GP_Hate_Speech
This project will utilize the 39,565 comments to provide a tool to detect hate speech across five common categories, including Status, Violence, Genocide, Dehumanization, and Humiliation.

## Prerequisites
Before you begin, make sure you have the following installed:

- Python 3.x(For the libraries mentioned in the notebook, to be sure you have already installed)
- ngrok account

## Dataset Creation
Original dataset from the datasets library named measuring-hate-speech in the Hugging Face Hub:
- original_data.csv: All the comments from users

We also filted columns we will analyze later:
- filted_data.csv

We then aggregated the data by 'comment id' and 'speeches' and calculated the mode or mean for each type of hate speech label within these groups. 
- group_filted_data_01.csv

- svm_test_scores.csv: Because we use another notebook to train the SVM model, we save the test scores, which will be compared with DistilBERT model's test scores.

## Models by using DistilBERT
- DisilBERT_models.ipynb
- best_model_{'status', 'violence', 'genocide', 'dehumanize', and 'humiliate'}_01.bin: they are the best models we trained in DistilBERT in 5 epochs for each dimensions.

## Models by using SVM
- compared_svm_model.ipynb: We also use TF-IDF with SVM to train, which will be compared the test score with DistilBERT, to decide the final model to later predict comments we want.

## Model explaination
- model explain.ipynb: using lime to find out key features influencing each model's decision-making process with a specific example.

## Date visualization and Interface
- Run from the section 'Interface Predict in HTML' in DisilBERT_models.ipynb(change ngrok.set_auth_token into your own token)
- templates folder(include index.html: the main entry point for our web application)












