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

![Image of Deploy](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/templates/2.png)

•	Deploy to App Engine

•	Deploy to Kubernetes Engine

•	Deploy to Cloud Run


## Deploy to App Engine

App Engine is a completely automated deployment platform. It supports many languages, including Python, Java, JavaScript, and Go. To use it, we create a configuration file and deploy applications with couple of simple commands. We create a file named app.yaml and deploy it to App Engine.


` gcloud app create --region=us-central `

` gcloud app deploy --version=one --quiet `

` gcloud app deploy --version=two --no-promote --quiet `


## Deploy to Kubernetes Engine

Kubernetes Engine allows you to create a cluster of machines and deploy any number of applications to it. Kubernetes abstracts the details of managing machines and allows you to automate the deployment of your applications with simple CLI commands. To deploy an application to Kubernetes, you first need to create the cluster. Then you need to add a configuration file for each application you will deploy to the cluster.

Add a file named kubernetes-config.yaml 

•	https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

•	https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/

To use Kubernetes Engine, you need to build a Docker image.

` gcloud builds submit --tag gcr.io/$DEVSHELL_PROJECT_ID/devops-image:v0.2 . `

Enter the following Kubernetes command to deploy your application:

` kubectl apply -f kubernetes-config.yaml `

In the configuration file, three replicas of the application were specified. Type the following command to see whether three instances have been created:

` kubectl get pods `

A load balancer was also added in the configuration file. Type the following command to see whether it was created:

` kubectl get services `


## Deploy to Cloud Run

Cloud Run simplifies and automates deployments to Kubernetes. When you use Cloud Run, you don't need a configuration file. You simply choose a cluster for your application. With Cloud Run, you can use a cluster managed by Google, or you can use your own Kubernetes cluster.
To use Cloud Run, your application needs to be deployed using a Docker image and it must be stateless.

To use Cloud Run, you need to build a Docker image.

` gcloud builds submit --tag gcr.io/$DEVSHELL_PROJECT_ID/cloud-run-image:v0.1 . `

1.	When the build completes, in the GCP Navigation menu, click Cloud Run.

2.	Cloud Run is not enabled by default. Click Start using Cloud Run to enable the API.

3.	Click Create service.

4.	Accept the defaults in the Deployment platform section.

5.	Click the Select link in the Container image URL text box. In the resulting dialog, expand cloud-run-image and select the image listed. Then click Continue.

6.	Finally, click Create. When a green check appears, click on the URL that is automatically generated for the application.








