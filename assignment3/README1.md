# ENSF 400 - Assignment 3 - Kubernetes

## Introduction
This assignment involves deploying an NGINX service and two backend applications using Kubernetes in a Minikube environment. The goal is to demonstrate your understanding of Kubernetes concepts such as Deployments, ConfigMaps, Services, and Ingress.

## Prerequisites
- Minikube installed and configured on your system
- `kubectl` CLI tool installed and configured to communicate with your Minikube cluster

## Steps

1. **Start Minikube Cluster**
   - Start a Minikube cluster with 3 nodes using the following command:
     ```bash
     minikube start --nodes 3 -p ensf400
     ```
   - Verify the cluster status using the following commands:
     ```bash
     kubectl get nodes
     minikube status -p ensf400
     ```

2. **Deploy NGINX Service**
   - Create the `nginx-dep.yaml` Deployment configuration file.
   - Create the `nginx-configmap.yaml` ConfigMap configuration file.
   - Create the `nginx-svc.yaml` Service configuration file.
   - Create the `nginx-ingress.yaml` Ingress configuration file.
   - Apply the configurations using `kubectl apply`:
     ```bash
     kubectl apply -f nginx-dep.yaml
     kubectl apply -f nginx-configmap.yaml
     kubectl apply -f nginx-svc.yaml
     kubectl apply -f nginx-ingress.yaml
     ```

3. **Deploy Backend Applications**
   - Create the `app-1-dep.yaml` and `app-1-svc.yaml` files for the first backend application.
   - Create the `app-2-dep.yaml` and `app-2-svc.yaml` files for the second backend application.
   - Apply the configurations using `kubectl apply`:
     ```bash
     kubectl apply -f app-1-dep.yaml
     kubectl apply -f app-1-svc.yaml
     kubectl apply -f app-2-dep.yaml
     kubectl apply -f app-2-svc.yaml
     ```

4. **Configure Canary Deployments**
   - Create the `app-1-ingress.yaml` file to configure the canary deployment for `app-1`.
   - Create the `app-2-ingress.yaml` file to configure the canary deployment for `app-2`.
   - Apply the configurations using `kubectl apply`:
     ```bash
     kubectl apply -f app-1-ingress.yaml
     kubectl apply -f app-2-ingress.yaml
     ```

5. **Test the Deployment**
   - Obtain the Minikube IP address using `minikube ip`.
   - Use `curl` to test the NGINX service and the backend applications:
     ```bash
     curl http://$(minikube ip)/
     curl http://$(minikube ip)/
     ```
   - Observe the load balancing between `app-1` and `app-2` as per the canary deployment configuration.

## Deliverables
The following files should be submitted as part of the assignment:

1. `nginx-dep.yaml`
2. `nginx-configmap.yaml`
3. `nginx-svc.yaml`
4. `nginx-ingress.yaml`
5. `app-1-dep.yaml`, `app-1-svc.yaml`, `app-2-dep.yaml`, `app-2-svc.yaml`
6. `app-1-ingress.yaml`, `app-2-ingress.yaml`
7. `README.md` (this file)

## Conclusion
This assignment covers the deployment of an NGINX service and two backend applications using Kubernetes. It also demonstrates the use of Canary deployments to gradually roll out updates to the backend applications. The provided search results and the steps outlined in this `README.md` should help you complete the assignment successfully.

