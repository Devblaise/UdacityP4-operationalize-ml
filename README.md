[![devblaise](https://circleci.com/gh/Devblaise/UdacityP4-operationalize-ml.svg?style=svg)](https://app.circleci.com/pipelines/github/Devblaise/UdacityP4-operationalize-ml)
## Project Overview

The Operationalize ML project contains a Machine Learning Microservice, built on **Scikit-Learn**. It contains a model that predicts house prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 

## What does this project do?

- Run a docker container
- Upload container into a public registry (hub.docker.com)
- Run the deployed application in a Kubernetes cluster
- Integrate with CircleCI for continuous integration

## Requirements
 - Python 3.7

### Steps
- Setup a t3.small Ubuntu 18.04 instance with 20GB space

- Install docker on Ubuntu 18.04 - https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common  
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -   
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"  
sudo apt update -y  
apt-cache policy docker-ce  
sudo apt install docker-ce  
sudo systemctl status docker  
```
- Grant user permissions to docker executable
```
sudo usermod -aG docker ${USER}  
su - ${USER}  
id -nG  
```

- Test docker
```
docker ps  
```

- Install hadolint
```
wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64 && chmod +x /bin/hadolint
```

- Install minikube
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

- Activate environment
```
source ~/.devops/bin/activate
```