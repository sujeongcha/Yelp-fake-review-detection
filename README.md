artificial-cilantro
==============================

Code for Team Artificial Cilantro's Machine Learning Final Project. The file structure is based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>.

You can use the following commands to download all the packages and the raw datasets:

```
make create_environment
workon artificial-cilantro
make requirements
make data
```

These commands call on code in the `Makefile`. 
- `make create_environment` sets up a virtualenv for our project where we can ensure the packages we use are *exactly* the same. `workon artificial-cilantro` activates the newly created environment; you can simply type `deactivate` into the command line if you want to exit the virtual env.
- `make requirements` downloads all packages in `requirements.txt` to the virtual env.
- `make data` downloads the raw data from CodaLab into the `data/raw` folder.

You can run `make help` to see a summary of all the `make` commands.

Code in your own git branch
------------
There are 5 of us working on this project. If we are all pushing code to the master branch, we will enter "commit push hell" where our code commits get mixed up with everyone else's code commits. 

What we can do instead is copy the current code in master to our own branch, edit it there, and once we are done we can send in a *pull request* for the master branch to *pull in* the changes from our own branch.

### Creating a new branch
I've seen branches divided across people (e.g. branch `eric`) or across tasks (e.g. branch `embeddings`).
```
git checkout -b mybranchname
```

### Pushing branch to Github
```
git push origin mybranchname
```

### Submitting a pull request
Go to the github repo and click the `New pull request` button. This will allow us to review code differences and whether we need to address any merge conflicts.

### Avoiding merge conflicts
Merge conflicts occur when there are two different changes to a file made off the same commit. Git does not know how to merge the two changes together so it will announce a "merge conflict" and throw the job over to us. To avoid this, we should try to work on separate files. For certain master files (e.g. `train_model.py` concurrent work may be unavoidable and changes should be coordinated with each other. But we can cross that bridge later.


Project file structure
------------
Let's try to follow it.

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
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

Helpful References
---------
Using `make`: https://medium.com/@davidstevens_16424/make-my-day-ta-science-easier-e16bc50e719c
Cookie cutter project template: https://drivendata.github.io/cookiecutter-data-science/
GitHub commands: https://rogerdudler.github.io/git-guide/