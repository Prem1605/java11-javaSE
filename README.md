# Azure WebApp using Java

In this demo you see how to deploy a java webapplication as WebApp on Azure.
A WebApp on Azure is a PAAS service, which means a serverless architecture which is maintained by your favorite Cloud provider.
Up and Down scaling is one of the features that Webapps has to offer, other features are: monitoring, deployment slots, application insights... but there are many many more features, Please have a look at the Azure WebApp documentation : https://docs.microsoft.com/en-us/azure/app-service-web/

- Preparatation
  - Create account on VSTS and create 3 projects (use GIT as repo)
    - project1: standard-webapp-java
    - project2: dockerized-webapp-java
    - project3: dockerkubenized-webapp-java 
  - Eclipse, install Azure plugin
  - Eclipse, install VSTS plugin
  - Make sure you have the following installed (on your local machine): >= JDK1.8, >= maven 3, eclipse 

- Standard Webapp on Azure
  - checkout https://github.com/chrisvugrinec/azure-webapp-java
  - cd standard-webapp
  - ./create.sh  (creates a standard hello-world webapp, using the maven web-app archetype)
  - Add the stuff to your standard-webapp-java VSTS project....
    - git init
    - git add .
    - git commit -m "initial commit"
    - git remote add origin https://[NAME OF YOUR VSTS SPACE].visualstudio.com/_git/standard-webapp-java
    - git push --set-upstream https://[NAME OF YOUR VSTS SPACE].visualstudio.com/_git/standard-webapp-java
  - In eclipse import existing maven project...you are Set :)
- Deploy current Hello World to Azure WebApp production
  - Create Azure WebApp, define App Service Plan, define deployment slots
  - Deploy to production using eclipse Azure Plugin
- Define Build in VSTS project ...automatic trigger with build, deploys on test deployment slot
- Make change in Eclipse...watch automated build being triggered
- Go to both webapps... (show kudu and SCM) 
- Make the swithch from test deployment slot to production

# Azure WebApp using dockerized Java App

# Java WebApp dockerized Java App on Kubernetes

  - To be more complete (Java deployment examples on Azure)  I added this example, however..this is NOT using a WebAPP, it uses a kubernetes cluster which is based (at the time of this writing) on a server (IAAS) architecture.

