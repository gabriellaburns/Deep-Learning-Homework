# NN Report:

## Overview:

The non-profit foundation Alphabet Soup wants to create an algorithm to predict whether or not applicants for funding will be successful. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

## Data Preprocessing:

- Results: The target variable is “IS_SUCCESSFUL” .
- The features are: Application Type, Affiliation, Classification, Use Case, Organziation, Status, Income Amount, Ask Amount, & Special Considerations.
- EIN and Name were neigher targets not features
- Here are a few steps I took to clean up the data:


## Compiling, Training, and Evaluating the Model

- I took several steps to increase model performance. 
    1. I changed the number of layers, activation type, and units. 
    2. I set a validation split of 0.15 for one model, changed the number of epochs, changed optimizers,  #
    3. While exploring different parameters to add into my final model training, I decided to add:
       a. batch size = 20
       b. steps per epoch to the equationsteps_per_epoch = int(np.ceil(X_train.shape[0]/batch_size) )
       c. outcome: 0.7308 accuracy - not bad compared to some of my other attempts.
        print(steps_per_epoch)
    4. I created matplotlib visualizations for my model accuracy to inform the changes I made along the way. Below is an example: 
    ![alt text](accuracy.png?raw=true)

    2. I choose a cutoff value and created a list of classifications to be replaced to reduce noise in the data
    3. I binned the outlier data for "Classification" and "Application Type" because of their high variability into a new value "Other" .
       a. I changed the cutoff value several times while tinkering with the model to balance noise reduction and data retention
- Ultimately, none of my models reached the 0.75 target accuracy

## Optimization:
- I used keras-tuner on my model 
- my top accuracy with keras-tuner was 0.735276997089386

## Future Recommendations:
- More data about the applications would be useful. I am curious about potential 
  factors that may not exist in the base csv file. For example, did some projects have additional outside funding that impacted their project's success?
- Additional time would give me the opportunity to experiment with new ways to reduce the influence of outliers in the model. For example, I would like to explore using a random forest classifier because RF handle outliers well. 
    

