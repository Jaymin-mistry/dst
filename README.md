# data science template

in this repo u can look at default template for ds/ml/dl/.. projects or similar

## how to use

**[0]** before creating a new project from this template, u need to install the next dependencies

* [cookiecutter](https://github.com/cookiecutter/cookiecutter)

  ```bash
  $ pip install cookiecutter
  ```

* [github cli](https://cli.github.com/manual/installation)


  * linux

    see [linux installation instructions](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)

**[1]** after go to the directory where u want to create your project and run

```bash
cookiecutter gh:vtrokhymenko/dst
```

## using the next project structure

```markdown
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
```

----

## another similar templates

* [cookiecutter-data-science](https://github.com/drivendata/cookiecutter-data-science)
  * [cdst](https://github.com/crplab/cdst/) by @crplab
  * [python-package-template](https://github.com/TezRomacH/python-package-template) by @TezRomacH
* [ocean](https://github.com/surfstudio/Ocean)
* [kedro](https://github.com/quantumblacklabs/kedro/)

## Potential tools to add 

* [dvc](https://dvc.org) – open-source version control system for ds projects
* [cml](https://cml.dev) – continuous machine learning | ci/cd for ml/dl
* [hydra](https://hydra.cc) – to configuring complex applications
* [dependabot](https://dependabot.com) – automated dependency updates
* [act](https://github.com/nektos/act) – run github actions locally
* [pre-commit](https://pre-commit.com) – framework for managing & maintaining multi-language pre-commit hooks
* coding style/review/formatter/typer
  * [codefactor](https://www.codefactor.io)
  * [deepsource](https://deepsource.io)
  * [prettier](https://github.com/prettier/prettier)
  * [pyright](https://github.com/microsoft/pyright)
  * [super-linter](https://github.com/github/super-linter)
    * [pylint](https://www.pylint.org/)
    * [flake8](https://flake8.pycqa.org/en/latest/)
    * [black](https://github.com/psf/black)
  * [restyled](https://restyled.io)
    * autopep8
    * black
    * isort
    * prettier-markdown
    * reorder-python-imports
    * yapf
* tests
  * [codecov](https://codecov.io)
* spellcheckers
  * [vale](https://errata-ai.gitbook.io/vale/)
  * [pyspelling](https://facelessuser.github.io/pyspelling/)
  * [yaspeller](https://github.com/hcodes/yaspeller)

## citation

```citation
@misc{dst,
  author = {viktor trokhymenko},
  title = {data science template},
  year = {2020},
  publisher = {github},
  howpublished = {\url{https://github.com/vtrokhymenko/dst}}
}
```

## license

this project licensed under the terms of the `mit` license. see the [license](./LICENSE) file for details
