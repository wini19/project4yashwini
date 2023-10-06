[![CircleCI](https://dl.circleci.com/status-badge/img/circleci/Qy9p7Rh8A2eSKPx45gjp2X/14iUjQrvsPKbujBUGLPnXb/tree/main.svg?style=svg&circle-token=ef998bc10ec5816c84a94a96facd68889a737e39)](https://dl.circleci.com/status-badge/redirect/circleci/Qy9p7Rh8A2eSKPx45gjp2X/14iUjQrvsPKbujBUGLPnXb/tree/main)

## Project Overview

In this project I have applied skills learnt in this course to operationalize a Machine Learning Microservice API. 

The application is a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. App.py — serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

## Tools and Technology 

Source code: Python, Flask
Containerization: Docker
Linting: Hadolint, PyLint
Orchestration: Kubernetes, minikube, kubectl
CI-CD: CIrcleCI
Version control: Git, Github

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
* Install Docker - refer instructions according to your system: https://docs.docker.com/engine/install/ 
(On Cloud9, Docker is already installed)
Run `docker --version` to verify installation.
* Run `make lint` to validate python code and Dockerfile
* Install minikube
Reference: https://minikube.sigs.k8s.io/docs/start/

`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`

`sudo install minikube-linux-amd64 /usr/local/bin/minikube`
Verify Installation
`minikube version`

* Install kubectl
Reference: https://kubernetes.io/docs/tasks/tools/#kubectl
`curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"`

`sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl`

Verify installation
`kubectl version --client`


### Steps to run application

* Create Flask app in Container
Run this command to create flask app in docker conatiner and starting the app:
`./run_docker.sh`

* Run via kubectl
1. Start minikube
`minikube start`
2. Run the app
`./run_kubernetes.sh`
If you get error about pod not running, re-run after few minutes when pod is created.
To check pod status: `kubectl get pod`



### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`
