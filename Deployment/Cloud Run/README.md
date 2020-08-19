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


Services:

![Image of DevOpsCloudService](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/CloudRunService.jpg)



Execution:

![Image of DevOpsCloudRun](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/CloudRunDeployRunning.jpg)
