# Kubernetes Service Creation
## Introduction
This README provides step-by-step instructions on how to create and manage Kubernetes services. 


### Question 1: Create two pods named "blue" and "red" using nginx image. The "blue" pod should be exposed on port 80.

To create execute the following commands:
```
kubectl run blue --image=nginx --port=80
kubectl run red --image=nginx
```
