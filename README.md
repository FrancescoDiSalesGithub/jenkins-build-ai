# jenkins-build-ai
main project of jenkins mini project

# Summary

* Overview of the infrastructure

# Overview of the infrastructure

In this small project the goal is to deploy an ollama modelfile to a server to later use it. This repository is the main repository of this project that has as dependencies the following ones:

* https://github.com/FrancescoDiSalesGithub/ai-models
* https://github.com/FrancescoDiSalesGithub/ai-models-jenkins

The first repository is about all the modelfiles written for llm models orchestrations, while, the second one has the jenkinsFile that Jenkins uses for the deployment of the modelfile. Why I have chosen Jenkinsfile over a pipeline written inside my stand-alone jenkins server? firstly if somehow something bad happens (for example my drive gets faulty) I can still hope with the Jenkinsfile store here to recover/update my pipeline.

# How the pipe works

Firstly I connect to the second node which is an ollama container and i start the node agent jar by replacing localhost:8080 with jenkins:8080. As soon as the node agent starts in the first stage i download from github the repository with all the ai modelfiles, then with the parameter passed i change directory to the model I want to build. From that, I launch the ollama build command to build the modelfile into the ollama docker container.
