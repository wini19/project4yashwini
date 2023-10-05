[![CircleCI](https://dl.circleci.com/status-badge/img/circleci/Qy9p7Rh8A2eSKPx45gjp2X/14iUjQrvsPKbujBUGLPnXb/tree/main.svg?style=svg&circle-token=ef998bc10ec5816c84a94a96facd68889a737e39)](https://dl.circleci.com/status-badge/redirect/circleci/Qy9p7Rh8A2eSKPx45gjp2X/14iUjQrvsPKbujBUGLPnXb/tree/main)

## Project Overview

In this project I have applied skills learnt in this course to operationalize a Machine Learning Microservice API. 

The application is a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. App.py — serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.


## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
