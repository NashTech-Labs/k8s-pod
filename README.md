#### Python client for the kubernetes API for pods

# crud operations on pods

we can use the client module to interact with the resources. 

`Resources:` kubectl get commands are used to create pod using yaml files in a cluster for eg:

To create the pod in the cluster, we fire following kubectl command:

```kubectl apply -f pod.yaml``` 

Get the list of all pod

`kubectl get pods`

But In Python, we instantiate CoreV1Api class from client module:

`client_api = client.CoreV1Api()`         

Here I've created the client with it's respective class CoreV1Api
and storing in a var named as client_api. so furture we can use it.

`KubeConfig:` to pass the on local cluster e.g minikube we use bellowcommand: 

`config. load_kube_config()`

#### Authenticating to the Kubernetes API server

But what if you want to list all the automated ingress of a GKE Cluster, you must need to authenticate the configuration

`configuration.api_key = {"authorization": "Bearer" + bearer_token}` 

I've used Bearer Token which enable requests to authenticate using an access key.

### create pods:

call the function create_pod(cluster_details)

And run following command:

`python3 pod.py`

#### get the list of all pods:

call the function get_pods(cluster_details)

And run following command:

`python3 pod.py`

#### update pods:

Call the function update_pod(cluster_details,k8s_object_name="nginx-pod-yamika")

NOTE: You can't update the metadata name of existing pod.

And run following command:

`python3 pod.py`

#### delete pods:

call the function delete_pod(cluster_details,k8s_object_name="nginx-pod-yamika")

`python3 pod.py`
