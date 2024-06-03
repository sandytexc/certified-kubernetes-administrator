# Static Pod In Kubernets

Static pods in Kubernetes are created and managed directly by the kubelet service on a node, without the need for a Kubernetes API server.
The kubelet automatically tries to create a mirror Pod on the Kubernetes API server for each static Pod. This means that the Pods running on a node are visible on the API server, but cannot be controlled from there Static pod path is a directorypath where static pod manifests are stored on a node.

Path:var/lib/kublet/config.yaml

### Create a Static Pod with the Name "static-web" Using the Nginx Image.
To create a static pod with the name "static-web" using the Nginx image, follow these steps:

- Create a YAML file named static-web.yaml with the following contents:
```
apiVersion: v1
kind: Pod
metadata:
  name: static-web
spec:
  containers:
  - name: nginx
    image: nginx
```

- Apply the pod definition using the command:
```
kubectl apply -f static-web.yaml
```

- Verify the successful creation of the static pod using the command:
```
kubectl get pods
```

### Copy the pod YAML to the folder designated for static pod's YAML files
To copy the pod YAML to the folder designated for static pod's YAML files, complete the following steps:

- Locate the folder on the Kubernetes node that contains the static pod's YAML files, typically /etc/kubernetes/manifests/.
- Copy the static-web.yaml file into the folder using the command:
```
sudo cp static-web.yaml /etc/kubernetes/manifests/
```

### 3. How to Ensure that the Pod is Started by Kubelet?
To ensure that the pod is started by kubelet, follow these steps:

- Monitor the pod's status using the command:
```
kubectl get pods
```

Confirm that the pod's status changes to "Running," indicating that kubelet has successfully started the static pod.


### 4. What is the path of the directory holding the static pod definition files?

```
staticPodPath: /etc/kubernetes/manifests
```
