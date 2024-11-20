# cmse492_project

This is a classification algorithm that can classify keypoint data of body movements in dance videos into 2 different dance styles. The two dance styles it will classify are Jazz Ballet and House.



Here is the Project Structure:

cmse492_project/
├── data/
│   ├── raw/               
│   ├── processed/            
│   ├── README.md           
├── notebooks/
│   ├── 01_exploratory_data_analysis.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_model_evaluation.ipynb
│   ├── 05_hyperparameter_tuning.ipynb
├── src/
│   ├── __init__.py
│   ├── data_preprocessing.py      
│   ├── feature_engineering.py     
│   ├── model.py                   
│   ├── evaluate.py               
│   ├── config.py            
├── models/
│   ├── model.pkl                  
│   ├── model_config.json      
│   ├── README.md                 
├── reports/
│   ├── interim/                   
│   ├── final/                
├── tests/
│   ├── test_data_preprocessing.py 
│   ├── test_model.py             
├── requirements.txt             
├── README.md                      
└──  .gitignore                   


