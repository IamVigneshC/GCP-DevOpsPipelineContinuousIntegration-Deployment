# Building a DevOps Pipeline - Google Cloud Platform (GCP)

Build a continuous integration pipeline using Cloud Source Repositories, Cloud Build, build triggers, and Container Registry.


![Image of DevOps](https://github.com/IamVigneshC/DevOpsPipelineCI/blob/master/templates/1.jpg)


‣ Create a simple Python Flask web application

‣ Define a Docker Build

‣ Manage Docker Images with Cloud Build and Container Registry

‣ Automate Builds with Triggers

‣ Test the Build Changes


# Deploying Apps to Google Cloud

Deploy applications to the Google Cloud services App Engine, Kubernetes Engine, and Cloud Run.


•	Deploy to App Engine

•	Deploy to Kubernetes Engine

•	Deploy to Cloud Run


## Deploy to App Engine

App Engine is a completely automated deployment platform. It supports many languages, including Python, Java, JavaScript, and Go. To use it, we create a configuration file and deploy applications with couple of simple commands. We create a file named app.yaml and deploy it to App Engine.


` gcloud app create --region=us-central `

` gcloud app deploy --version=one --quiet `

` gcloud app deploy --version=two --no-promote --quiet `





