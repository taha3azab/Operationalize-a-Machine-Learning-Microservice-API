
[![CircleCI](https://circleci.com/gh/taha3azab/Operationalize-a-Machine-Learning-Microservice-API.svg?style=svg)](https://circleci.com/gh/taha3azab/Operationalize-a-Machine-Learning-Microservice-API)


## Operationalize a Machine Learning Microservice API
Project 4 [Udacity Cloud DevOps Engineer Nanodegree]

## Project Overview
Deploy a containerized Python flask application to serve out predictions (inference) about housing prices through API calls. It uses a a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features. 

---
### Install

### Setup the Environment

* Create a virtualenv and activate it
```
python3 -m venv <your_venv>
source <your_venv>/bin/activate
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

### Run the project

1. You should have a virtual machine like VirtualBox and minikube installed, as per the project environmet instructions. To start a local cluster, type the terminal command: 
```
minikube start
```

2. To deploy this application in kubernetes run:
```
./run_kubernetes.sh
```

3. After you’ve called run_kubernetes.sh, and a pod is up and running, make a prediction using a separate terminal tab and run 
```
./make_prediction2.sh
```

4. Delete the cluster
```
minikube delete
```


### Files explanation
- config.yml: CircleCI configuration file for running the tests
- app.py: Python flask app that serves out predictions (inference) about housing prices through API calls
- Dockerfile: Dockerfile for building the image
- make_prediction.sh: Send a request to the Python flask app to get a prediction, for localhost
- make_prediction2.sh: Send a request to the Python flask app to get a prediction, for minikube kubernetes
- Makefile: includes instructions on environment setup and lint tests
- run_docker.sh: file to be able to get Docker running, locally
- run_kubernetes.sh: file to run the app in kubernetes
- upload_docker.sh: file to upload the image to docker