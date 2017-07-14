gcloud reference : https://cloud.google.com/sdk/gcloud/reference/

### Set the default project

- List the projects : 

````
gcloud projects list
````
- Set the default project 

````
gcloud config set project MyProject
````


### Set a default  Compute Engine zone
Example : Set the default zone to ``us-east1-d`` :

````
gcloud config set compute/zone us-east1-d
````

## Container Engine

Shutdown all nodes

````
gcloud container clusters resize MyCluster --size=0
````
