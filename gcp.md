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

- Get project's id

````
PROJECT_ID=$(gcloud config get-value core/project)
````

- Get project's number

````
PROJECT_NUMBER=$(gcloud projects describe ${PROJECT_ID} --format='value(projectNumber)')
````

### Set a default  Compute Engine zone
Example : Set the default zone to ``us-east1-d`` :

````
gcloud config set compute/zone us-east1-d
````

### Ensure the default credentials are available local machine

````
gcloud auth application-default login
````

- Print access token

````
gcloud auth application-default print-access-token
````

## Container Engine

- List clusters

````
gcloud container clusters list
````

- Shutdown all nodes

````
gcloud container clusters resize MyCluster --size=0
````

- Get active cluster

````
gcloud config get-value container/cluster
````

- Generate kubeconfig file for ``MyCluster``

````
gcloud container clusters get-credentials MyCluster
````

## KMS

- Create keyring

````
gcloud kms keyrings create my-keyring --location=global
````

- Generate a new encryption key

````
gcloud kms keys create my-key \
  --location=global \
  --keyring=my-keyring \
  --purpose=encryption
````  
- Encrypt a file using the ``my-keyring`` keyring and ``my-key`` encryption key

````
gcloud kms encrypt \
  --plaintext-file my-file \
  --ciphertext-file my-file.enc \
  --location=global \
  --keyring=my-keyring \
  --key=my-key
````
