# remessa-app

This a very simple Python Flask application that returns a message on the base path. 

The important part of this repository is how things are managed to be deployed.

- Helm
I'm using helm to get a lot easier to manage the kubernetes resources and to be way easier to be managed the versions of those deploys. I'm not uploading the chart to any place, I'm using the local chart.

- GH Actions
THere's two jobs to make the deploy happen: Build And Deployment.
  - Build: Uses a docker executor to build a image based on the Dockerfile from the repo and then upload the image to docker hub.
  - Deployment: Uses a helm chart (/remessa-app) to create a pod with the image that was deployed and a Node Port service to access the application from outside world.
