### Google Cloud Fundamentals: Getting Started with GKE


Run the following code on your Terminal or Command Prompt with Cloud SDK installed.

* Run
```bash
gcloud auth login 
```
Then follow the prompts.

* To view your projects run
```bash
gcloud config list project
```

* Then set your project as default by running
```bash
gcloud config set project your-project-id
```
Replace 'your-project-id' with your project id you created

### Start a Kubernetes Engine cluster

* Start a Kubernetes Cluster
```bash
gcloud container clusters create my-cluster-name --zone my-zone --num-nodes node-number
```
replace 'my-cluster-name' with the name you want to give your cluster, replace 'my-zone' with the name of the zone you want the cluster to live in, replace 'node-number' with the number of nodes you want the cluster to have it can only accept numeric characters.

* After creating the cluster run the following code to test it
```bash
kubectl version
```

### Run and deploy a container

* Launch a single instance of a web server. Here we're using Ngix
```bash
kubectl create deploy nginx --image=nginx:1.17.10
```

* View the pod running the nginx container
```bash
kubectl get pods
```

* Expose the nginx container to the internet.
```bash
kubectl expose deployment nginx --port 80 --type LoadBalancer
```

* View the new service:
```bash
kubectl get services
```
You can use the displayed external IP address to test and contact the nginx container remotely.

It may take a few seconds before the External-IP field is populated for your service. This is normal. Just re-run the ```kubectl get services``` command every few seconds until the field is populated.

* Open a new web browser tab and paste your cluster's external IP address into the address bar. The default home page of the Nginx browser is displayed.

* Scale up the number of pods running on your service:
```bash
kubectl scale deployment nginx --replicas 3
```

* Confirm that Kubernetes has updated the number of pods:
```bash
kubectl get pods
```

* Confirm that your external IP address has not changed:
```bash
kubectl get services
```

