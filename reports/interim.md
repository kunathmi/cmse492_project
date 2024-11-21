Dance Genre Classification

Link: https://github.com/kunathmi/cmse492_project.git 

This project will build a classification algorithm that can classify keypoint data of body movements in dance videos into 2 different dance styles. Specifically, I will use keypoint data which identifies major joints and key facial features and tracks their locations throughout a video. Then, I will build a feature vector using various calculations on the keypoint data. These calculations will be determined in order to identify a dance such as velocity or "energy," range of motion, etc. I can then use the feature vectors to build a machine learning model to classify dance videos into two different styles. My plan is to start with a small number of features and add more to improve classification if needed.

Here is my intended project structure:

project-name/

    data/
        raw/                # Original raw data files (e.g., CSVs, JSONs)
        processed/          # Processed data files ready for modeling
        external/           # External data sources, if any
        README.md           # Instructions on how to obtain or preprocess data
    notebooks/
        01_exploratory_data_analysis.ipynb
        02_data_preprocessing.ipynb
        03_model_training.ipynb
        04_model_evaluation.ipynb
        05_hyperparameter_tuning.ipynb
    src/
        __init__.py
        data_preprocessing.py      # Functions for data cleaning and preprocessing
        feature_engineering.py     # Feature extraction and engineering methods
        model.py                   # Model creation and training functions
        evaluate.py                # Model evaluation and metrics
        config.py                  # Configuration file for project settings
    models/
        model.pkl                  # Serialized model files (trained models)
        model_config.json          # Model configuration settings
        README.md                  # Explanation of models used and their configurations
    reports/
        interim/                   
        final/                
    tests/
        test_data_preprocessing.py # Unit tests for data preprocessing functions
        test_model.py              # Unit tests for model-related functions
    requirements.txt               # List of dependencies (e.g., scikit-learn, pandas)
    README.md                      # Overview of the project, instructions, usage
    .gitignore                     # Files and directories to be ignored by git

The key directories will be the notebooks, models, and reports folders. There are also directories for the data, src, and tests. Some of the dependencies that will be required are scikit-learn, numpy, pandas, matplotlib.pyplot, among other lesser used packages. There are not strict version constraints, so the requirements.txt file will have users download the most recent versions of the dependencies.

So far, I have loaded in a sample set of 10 videos from each of the two genres. I have started creating my feature vectors by calculating the velocities of each of the keypoints. I can then see if I can classify based on how the velocities differ between the genres. The next feature I plan to calculate is the distance between wrists and ankles because ballet uses a lot of overhead arms while house dances tend to have arms below shoulder height. Currently, I am working on the code to flatten the arrays and run a classifier on it. The code is still in progress, so I do not yet have preliminary results.

From this initial exploratory data analysis and model training, I have found that there is a notable difference in the pattern of movements for the parts of the body as demonstrated in the graph of y-coordinates of the keypoints over time. My additional calculations show that the keypoints on the body also have variation in velocity. This might be useful in comparing dances that have more arm movements versus leg movements. I also want to look at some distances which relate to range of motion that would be easy to calculate and add to the model such as the distance between wrists and ankles or the distance between wrists and nose. It could also be interesting to look at the angle made between the wrists, elbows, and shoulders, but I am not sure how helpful that would be. 

My machine learning approach will be to start with data preparation/processing. In this step, I will normalize the keypoints and do feature extraction. Next, I will move to model selection and evaluation. These go hand-in-hand because I will be in part selecting a model based on the evaluation metrics. Next, I will use hyperparameter tuning to optimize performance with one or a couple of the best classifiers from the previous round. Lastly, if the results are still not satisfactory, I might attempt a combination of the models to produce a better performance. 

Next, let’s discuss some of the challenges and solutions for this project. The first significant issue I encountered was the usability of my data set. Unfortunately, there is not a database with a large number of dances formatted as samples. Instead, each of the samples are saved as separate pkl files. This gives me the tedious task of loading in all of the samples from each type of dance individually. 



Upon looking through the documentation, I have determined how to easily differentiate genres in the naming conventions. So even though this task seemed quite daunting at first, I was able to overcome that fairly easily with copying and pasting file names and using a loop to read them in, as seen in the code snippet above. The second issue I faced was adding the data to my git repository. It is saved correctly locally, but every time I tried to add it to the origin, the process failed. I am still working through this issue.

For the next phase of the project, I want to finish loading in all of the dance keypoints I want to use, as for this part I only did a small sample to do some exploration with. I will also need to spend more time with the classifiers and with feature selection. I plan to use cross-validation and confusion matrices to pick the best classifier. The main thing I need to work on is finishing setting up my file structure and inputting information where it needs to go. As far as the timeline goes, I will start by loading in the rest of the dance keypoints this week. Next week, I will focus on classification. The week after, I plan to focus on visualizations and finishing fine tuning and adding dependencies to the git repository.

In summary, I have made some decent progress toward my machine learning project. I now have a method of loading in the data that makes sense and turns it into a data frame. I feel that my progress thus far has given me a clearer vision for the project and allowed me to set more specific goals to work toward completion. My plans include spending a bit more time ironing out my feature vector and then immediately testing it by running it through a classifier. I will then 






























Works Cited:

Shuhei Tsuchida, Satoru Fukayama, Masahiro Hamasaki and Masataka Goto. AIST Dance 
Video Database: Multi-genre, Multi-dancer, and Multi-camera Database for Dance Information Processing. In Proceedings of the 20th International Society for Music Information Retrieval Conference (ISMIR 2019), 2019.

