 # Task1 
 
 A HorizontalPodAutoscaler in helm charts to automatically scale workload per the average CPU and Memory utilization of target pods to match demand

A Serverless Posgress Database instance is recommended unpredictable production workload and to scale in response to increased demand with zero downtime

# Adding a Database 
There are two possible ways to acheive this:
+ By connecting to a remote database (outside of the cluster)

+ By creating a database cluster within the cluster 

### Connecting to a remote database

_**Step1:**_ Firstly you need to setup the remote database server. This could be a local database server on prem or a database instance in the cloud

_**Step2:**_ Tools like crossplaine and schemahero with helm using compositions and claims connects the application to the database seamlessly


### Creating a database cluster
There are a couple ways to do this. 
We'll use a helm chart provided by [bitnami](https://github.com/bitnami/charts/tree/main/bitnami/postgresql)  that bootstraps PostgreSQL deployment on a Kubernetes cluster

_**Step1:**_ Install the chart:

     helm install my-release oci://REGISTRY_NAME/REPOSITORY_NAME/postgresql

 ##### <span style="color:cyan"> _Note: Replace the placeholders <u>REGISTRY_NAME </u> and <u>REPOSITORY_NAME</u> with a reference to your Helm chart registry and repository. example : REGISTRY_NAME=registry-1.docker.io and REPOSITORY_NAME=bitnamicharts_</span>


_**Step2:**_ leverage the production-grade support that comes with the solution from bitnami to intergrate and tweak to suite your teams specification