## Prerequisites

Once you run *kubectl apply -f* on all five manifests folders (one for each microservice), you will need to:

1) Open the RabbitMQ UI on your web browser and add the *video* and *mp3* queues.
2) Shell into the auth-mysql container and create the *auth* database. Then create the table *user* within the *auth* database before adding your user (email, password). Check configmap.yaml and secret.yaml within /auth/manifests/ to match (or change) the MySQL username and password.
3) Shell into the mongo-db container and create the required databases (mp3s and videos). Then create the user for those databases. Refer to the configmap.yaml and secret.yaml files within /auth/manifests/ to match (or change) the mongoDB username and password.
4) Go to the configmap.yaml and secret.yaml within notification/manifests/ and change the GMAIL_ADDRESS and GMAIL_PASSWORD variables respectively with your own email account.

Once you complete the tasks above, delete the pods and re-deploy.

## Future Improvements

1) Use kustomize to centralize most the configmap and secret variables (/base).
2) Use SOPS to encrypt the secret.yaml file.


