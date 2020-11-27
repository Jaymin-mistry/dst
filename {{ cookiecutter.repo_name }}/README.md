# {{ cookiecutter.repo_name }}

{{ cookiecutter.project_short_description }}

The purpose of this project structure is to enable:
- individuals to work together as teams and understand where to find code/items
- teams to collaborate and individuals to move between teams

All project structures are a compromise but this is essential for us to work together.

### GUIDANCE/ GROUND RULES

1.  Store notebooks in the "notebooks" folders based on thematic labelling e.g. “Project_name”,”theme_x”, (...) 
2.	Within a thematic folder, only notebooks should be stored and they should be named as per the convention below
3.  No data., output or blob files (.DOC, .XLS, .PDF, .HTML, .PNG, .JPEG or .SVG) should ever enter the repository.
4.  All outputs (e.g images containing graphs etc should be stored into the "outputs" folder
4.	Any raw or intermediate data files created should be stored in the "data" folder.  No CSV/RDS/JSON/favourite_data_format in any folder aside “/data”. 
5.	All .py or .R files should be stored in src/ 
6.  Pytest is the preferred test framework.
7.	All tests should be stored in the tests folder and contained in files beginning test_XXX.py so that they can be detected by pytest
8.	The folder “models" can be deleted if not required
10.	Notebooks should be cleared of output before committing. This can be achieved using nbstripout (details below)

------------

#### NOTEBOOK NAMING CONVENTION

TICKET-Number-freetext description-of-notebook.ipynb 

E.g: ```ABC14-I-really-care-helping-my-colleagues-work-together.ipynb```
                          
Project Organization
------------

    ├── .github/workflows  <- Github actions/workflows 
    ├── config             <- local folder to store secrets etc that is not committed
    ├── data
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │   └── pull_request_template.md <- Template for pull requests
    ├── models             <- Trained and serialized models objects
    │
    ├── notebooks
      └── project/theme       <- Each project/theme has a folder for related work
    │   └── NOTEBOOK_NAMED_CONVENTION.ipynb <- A notebook about a topic with a ticket number and description<- Jupyter notebooks. Naming convention is ticket number (for ordering the creator's initials, and a short free-text `-` delimited description, e.g. `JNE-01-jm-initial-data-exploration`.
    │
    ├── outputs            <- Generated analysis as HTML, PDF, LaTeX, graphics and figures
    │
    ├── src                <- Source code for use in this project.
        └── __init__.py    <- Makes src a Python module 
    │        
    ├── tests              <- All tests for this project
    │
    ├── .gitignore
    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    └── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    
    
#### Setting up NBSTRIPOUT [link](https://github.com/kynan/nbstripout)
nbstripout is a python utility to remove the outputs from jupyter notebook files.  It is important as 
1. we do not want to commit sensitive data to repos
2. we do not want our repos to grow excessively large (which will occur if we commit graphs etc)

Running these commands will set up nbstripout to work by default on ALL repos on a VM/instance
```
pip install nbstripout
mkdir -p ~/.config/git  # This folder may not exist and will contain configuration for how git is handled
nbstripout --install --global --attributes=~/.config/git/attributes
```
Alternatively:
```pip install nbstripout```

Run each repository, run the following command via the command line

```nbstripout --install --global```

This will strip notebooks of outputs before committing for the specific repo that it is set up in..

Manual stripping of notebooks can be achieved by
``` nbstripout FILE.ipynb [FILE2.ipynb ...]```

--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
