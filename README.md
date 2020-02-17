# EASE 2020 Replication package


This repository contains the replication package and dataset of the paper to be published at EASE 2020 with the title **A Multinomial Naïve Bayesian (MNB) network to
automatically recommend topics for GitHub repositories**

All the resources, including the tool, the dataset, and the article have been realized by:

- Claudio Di Sipio 
- Riccardo Rubei
- Davide Di Ruscio
- Phuong T. Nguyen


# Setting the environment 

To run the Python scripts, you need the following libraries:

- scikit-learn 0.22.1
- nltk 3.4.5
- guesslang 0.9.3
- tensorflow 1.6.0 (required by guesslang)
- PyGithub 1.44

Notice that guesslang module requires Python 3.6. More information about this module can be found [here](https://pypi.org/project/guesslang/)

# Crawler settings

To enable the crawler, you have to set a personal access token in this way:

access_token = Github ("your token", per_page=100)

To generate an access token from your Github profile, please refer the following [link](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)

The optional parameter per_page is useful to paginate the results

# Run the tool 

In main.py, you have to edit the following paths:

- train_dir = "path_to_train_folder"
- test_dir = "path_to_test_folder"


After the train data is loaded, you have to modify the following parameters in the predict_topics function: 

- dirs: the root folder that contains the test files
- test_dir: the test folder for a single round
- train_dir: the train folder for a single round
- labels: the list of topics to predict
- num_topics: number of predicted topics
- list_test: a txt file that contains the name of repository to test

The output is a CSV files with all the metrics presented in the work:
- success rate (1..5)
- precision
- recall
- top rank



# Dataset and experiments

This [link](https://drive.google.com/drive/folders/197LCCfBTcpbqqaPfxO4C8V0t3f-XFnKT) contains the dataset used in the evaluation as well as the results in CSV format

As discussed in the paper, we have build three different dataset by variating the number of files used in the training phase i.e., 10, 50, and 100:

```
results
    .
    |--- validation_100/       		It contains the results for the 10 README files
    |
    |--- validation_50/				The ten-folder structure for the 50 README files
    |
    |--- validation_10/   			The ten-folder structure for the 10 README files
    


evaluation structure
    .
    |--- ten_folder_100.rar/       		The ten-folder structure for the 100 ReadMe
    |
    |--- ten_folder_50.rar/				The ten-folder structure for the 50 ReadMe
    |
    |--- ten_folder_10.rar/   			The ten-folder structure for the 10 ReadMe
    
```




