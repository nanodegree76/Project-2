# Project 2: Disaster Response Pipeline Project


## Table of Contents
 * [Project Motivation](#project-motivation)
 * [File Descriptions](#file-descriptions)
 * [Components](#components)
 * [Instructions for Project Interaction](#instructions-for-project-interaction)
 * [Licensing, Authors, Acknowledgements, etc.](#licensing-authors-acknowledgements-etc)
 

### Project Motivation

This project is meant to showcase my learnings from the Software Engineering, Data Engineering and Data Science skills from the Data Science Nanodegree by Udacity.
The API helps classifying disaster messages from various sources to aid ressource allocation in disaster circumstances.
Automating the categorization, especially during such circumstances, is crucial as organizations have the least capacity then.  
The data used to build a model here was kindly provided by [Figure Eight (now a dividion of Appen)](https://appen.com/).
The ML pipeline categorizes real messages from disaster events. It offers an input field for new messages that are automatically categorized so that it can be forwarded appropriately.
Furthermore, visualizations of the data are shown in the web application.


### File Descriptions

app    

| - template    
| |- master.html # main page of web app    
| |- go.html # classification result page of web app    
|- run.py # Flask file that runs app    


data    

|- disaster_categories.csv # data to process    
|- disaster_messages.csv # data to process    
|- process_data.py # data cleaning pipeline    
|- InsertDatabaseName.db # database to save clean data to     


models   

|- train_classifier.py # machine learning pipeline     
|- classifier.pkl # saved model     


README.md

The folder 'Jupyter Notebooks' was added for documentation purposes and is not required for running the application.



### Components
Three workflows are completed in this project:

#### ETL Pipeline

The data exploration and initial analysis were done in the Jupyter notebook 'ETL Pipeline Preparation'.

The Python script, 'process_data.py', based on the mentioned Jupyter notebook, includes a data cleaning pipeline where:

 - Datasets are loaded (messages and categories)
 - Mentioned datasets are merged
 - Data is cleaned
 - Data is stored in an SQLite db

#### 2. ML Pipeline

The Python script 'train_classifier.py' includes a ML pipeline where:

 - The SQLite database is loaded
 - Training and test sets are distinguished
 - A text processing pipeline is built
 - A ML pipeline is built
 - A model is trained
 - Results on test set are returned
 - The final model is exported as a pickle file

The jupyter notebook 'ML Pipeline Preparation' was used for data exploration and analysis to prepare for the the train_classifier.py python script.

#### 3. Flask Web App
The included web app offers an input field for emergency workers to input new messages. The inputs are then classified into the pre-defined categories.
Furthermore, aggregated data is visualized in the web app to understand which categories are the most mentioned.


### Instructions for Project Interaction:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        'python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db'
    - To run ML pipeline that trains classifier and saves
        'python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl'

2. Run the following command in the app's directory to run your web app.
    'python run.py'

3. Once the server is running, open a new terminal window and type
    'env | grep WORK'
    Use the output in the next step.

3. Go to https://**SPACEID**-3001.**SPACEDOMAIN**
  

### Licensing, Authors, Acknowledgements, etc.
A big thanks to the Udacity team for the starter code for the web app and Figure Eight for the data.
