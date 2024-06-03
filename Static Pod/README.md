#Static Pod In Kubernets

Static pods in Kubernetes are created and managed directly by the kubelet service on a node, without the need for a Kubernetes API server.
The kubelet automatically tries to create a mirror Pod on the Kubernetes API server for each static Pod. This means that the Pods running on a node are visible on the API server, but cannot be controlled from there
Static pod path is a directorypath where static pod manifests are stored on a node.
Path:var/lib/kublet/config.yaml
