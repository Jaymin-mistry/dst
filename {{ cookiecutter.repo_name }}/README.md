# {{ cookiecutter.repo_name }}

{{ cookiecutter.project_short_description }}

![Python code](https://github.com/test-and-trace/{{ cookiecutter.repo_name }}/workflows/Python%20application/badge.svg)
![NBStripout](https://github.com/test-and-trace/{{ cookiecutter.repo_name }}/workflows/NBStripout/badge.svg?branch=master)    

## PURPOSE
The purpose of this project structure is to enable:
- individuals to work together as teams and understand where to find code/items
- teams to collaborate and individuals to move between teams

## PRINCIPLES
- *Common structure* makes it easy to know where to find code/items and make it easier to collaborate/ onboard people.
- *Shared functions* reduce duplication and simplify work.
- *Continuous Integration* used by default to automate code quality (PEP8) and run tests to ensure code quality

All project structures are a compromise but this is essential for us to work together.

### GUIDANCE/ GROUND RULES
1.  Store notebooks in the "notebooks" folders based on thematic labelling e.g. “Project_name”,”theme_x”, (...) 
2.	Within a thematic folder, only notebooks should be stored and they should be named as per the convention below
3. Notebooks should be cleared of output before committing. This can be achieved using nbstripout (details below) 
4. No data, output or blob files (.DOC, .XLS, .PDF, .HTML, .PNG, .JPEG or .SVG) should ever enter the repository.
5.  Any raw or intermediate data files created should be stored in the "data" folder.  No CSV/RDS/JSON/favourite_data_format in any folder aside “/data”. 
6.	All outputs (e.g images containing graphs etc should be stored into the "outputs" folder
7.	All .py or .R files should be stored in src/ 
8.  Pytest is the preferred test framework.
9.	All tests should be stored in the tests folder and contained in files beginning test_XXX.py so that they can be detected by pytest.
10.	The folder “models" can be deleted if not required
11. The default location for outputs or objects (images, models etc) that need to be persisted and shared is S3.

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
    ├── .pre-commit-config.yaml
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    └── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
                              generated with `pip freeze > requirements.txt`
                  

#### Automated PEP8 formatting using [black](https://github.com/psf/black)
Writing consistently formatted and structured code enables us to work at pace.  [PEP8](https://www.python.org/dev/peps/pep-0008/) is the standard Python coding standard, whilst there are a number of code style checkers/formatters (flake8 etc), black is the most widely adopted by large organisations and can be used to reformat code as well as identify issues.  It can be used on all python files inside directory by running the following command once black is installed.
```
black .
```


#### Testing using [Pytest](https://docs.pytest.org/en/stable/getting-started.html#create-your-first-test)
Pytest is a common python testing framework.  Tests are important for ensuring that changes to code do no break existing functionality and can be run in an automated manner to check this.  Tests should be stored in the "tests" directory and be preceded with "test_XXX.py" so that pytest can identify them.  Tests are run on Pull request using Github actions and can be manually run by using the following command in the repo directory.
```
pytest .
```

#### Precommit [pre-commit](https://pre-commit.com/)
Pre-commit is python tool for managing pre-commit hooks so that issues are fixed before they end up in the commit history of git.  By installing pre-commit in a repo you can ensure your code is of the correct standard before you commit it and prevent issues when conducting PRs, freeing you up to focus on actual code review.  The same code quality checker (black) is used in the PR tests as in the pre-commit hook 
```
pip install pre-commit

# Run the following command in the repo directory
pre-commit install

# This command runs pre-commit against all files in the repo.  Use this the first time it is installed
 pre-commit run --all-files
```
#### Setting up [NBSTRIPOUT](https://github.com/kynan/nbstripout)
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
