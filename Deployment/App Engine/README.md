## Deploy to App Engine

App Engine is a completely automated deployment platform. It supports many languages, including Python, Java, JavaScript, and Go. To use it, we create a configuration file and deploy applications with couple of simple commands. We create a file named app.yaml and deploy it to App Engine.

In a project, an App Engine application has to be created. This is done just once using the gcloud app create command and specifying the region where you want the app to be created. 

`gcloud app create --region=us-central `

Deploy your app with the following command:

`gcloud app deploy --version=one --quiet `

In the Navigation menu, click App Engine > Dashboard

![Image of Dash](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/AppEngineDashboard.jpg)

Click on the link to test the program

Make changes and deploy version two with the following command:

` gcloud app deploy --version=two --no-promote --quiet `



When the command completes, return to the App Engine dashboard. Click the link again, and version one will still be returned. It should return Hello GCP. This is because of the --no-promote parameter in the previous command.

On the left, click the Versions link. Notice that two versions are listed.

Click on the version two link to test it

![Image of AppVersion](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/AppEngineVersions.jpg)

Note:
You might have to click Refresh to see version two.

Click on the version two link to test it. It should return Hello App Engine.


![Image of AppVersionDeploy](https://github.com/IamVigneshC/GCP-DevOpsPipelineContinuousIntegration-Deployment/blob/master/Resources/AppEngineDeploymentRunning.jpg)

To migrate production traffic to version two, click Split Traffic at the top. Change the version to two, and click Save.

Give it a minute to complete. Refresh the browser tab that earlier returned Hello GCP. It should now return the new version.

