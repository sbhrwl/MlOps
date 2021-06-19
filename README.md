# E2E Project
* [Overview](#overview)
* [Project Setup](#project-setup)
* [DVC Initialisation](#dvc-initialisation)
* [Unit Test setup](#unit-test-setup)
* [CICD pipeline](#cicd-pipeline)
* [Creating and Distibuting Package](#creating-and-distibuting-package)

# Overview
* Create a machine learning model
* Create a continuous integration continuous deployment pipeline
* Deploy Model to Heroku
* Whenever a new commit is made to the project, deployment ot **Heroku** will be triggered

# Project Setup
* Create env 
```bash
conda create -n wineq python=3.7 -y
```
* Activate env
```bash
conda activate wineq
```
* Install the requirments
```bash
pip install -r requirements.txt
```
* Git Initialisation
```bash
git init
```

# DVC Initialisation
* Download the data from 
  * https://drive.google.com/drive/folders/18zqQiCJVgF7uzXgfbIJ-04zgz1ItNfF5?usp=sharing
* Initialise DVC
```bash
dvc init 
```
* Add files to dvc
```bash
dvc add data_given/winequality.csv
```
```bash
git add .
```
```bash
git commit -m "first commit"
```
* Oneliner updates  for readme
```bash
git add . && git commit -m "update Readme.md"
```
```bash
git remote add origin https://github.com/c17hawke/simple-dvc-demo.git
git branch -M main
git push origin main
```

# Unit Test setup
* tox command -
```bash
tox
```
* tox command for rebuilding
```bash
tox -r 
```
* pytest command
```bash
pytest -v
```
# CICD pipeline
Configure /workflows/ci-cd.yaml
* Choose container for the app
* Install Python 
* Install requirements for the project
* Run unit tests
* Provide Heroku specific Token and App name to trigger deployment on Heroku

# Creating and Distibuting Package
```bash
pip install -e . 
```

build your own package commands- 
```bash
python setup.py sdist bdist_wheel
```
