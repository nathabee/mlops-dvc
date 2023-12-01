mlops-dvc
application to "Wafer"
==============================
This project is an implementation of the Tutorial of a You Tube Video : 
MLOPS end to end implementation https://www.youtube.com/watch?v=Ly3Dor8HZUA
it uses the cookiecutter shell for the basic structure of the project

Document are to be found in https://c17hawke.github.io/wafer_mlops_docs/
=> this explains how to initialise a new project _(when you started from "null"), how to use dvc and mlops

The DVC docs explains how to interface the google drive .
It is recommended to use a custom Google Cloud project.  We should use the Google API console,create credential and use a TestUser
For a detailled procedure see : https://dvc.org/doc/user-guide/data-management/remote-storage



Because many files are not provided by Krish Naik or by Sunny, I had to make some research on GitHub and found wafer project, who are very inspirativ :
https://github.com/suryanshyaknow/faulty-wafer-component-detection
https://github.com/sethusaim/Wafer-Fault-Prediction-using-MlFlow/


======================================
thema : WAFER

======================================
stage1_init_setup/

use GDRIVE as remote DVC storage for the data files
create a repertory in googledrive (storage)
with the Google API enable the drive API , create credential OAuth and a test user

GDRIVE credential are saved in local in ./dvc/config.local when  we initialise dvc in local mode :
remote add --local
dvc remote add --local -d storage gdrive://...
dvc remote modify --local storage gdrive_client_id '....'
dvc remote modify --local storage gdrive_client_secret '...'
=> This will is secret and will not be imported in Github : it stays secret of my server

in github , the credential are saved as "secrets" so that DVC connect to the GoogleDrive (content of file in .dvc/tmp/gdrive_user_credentials.json will be coped/pasted inside. ) Just the owner oh the repository has accees to them. So you need your own repository if you want to make your own
will be initialise at the first dvc push

===========================================
stage1_init_setup/
schema_prediction.json and schema_training.json are to be found in https://github.com/suryanshyaknow/faulty-wafer-component-detection. so I used them because they can not be found in 

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
