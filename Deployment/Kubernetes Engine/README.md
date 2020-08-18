## Deploy to Kubernetes Engine

Kubernetes Engine allows you to create a cluster of machines and deploy any number of applications to it. Kubernetes abstracts the details of managing machines and allows you to automate the deployment of your applications with simple CLI commands. To deploy an application to Kubernetes, you first need to create the cluster. Then you need to add a configuration file for each application you will deploy to the cluster.

Kubernetes Engine -> Create cluster

In the Connect to the cluster screen, click Run in Cloud Shell. This opens Cloud Shell with the connect command entered automatically.

![Image of KubeCluster](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/KubernetesCluster.jpg)

To test your connection, enter the following command:

` kubectl get nodes `


Add a file named kubernetes-config.yaml in the project folder

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


When you have an external IP, open a browser tab and make a request to it.

![Image of KubeDeploy](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/KubernetesRunning.jpg)
