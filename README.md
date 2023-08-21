# Microk8s (Kubernetes) -Install-Ubuntu-22.04
This tutorial will teach you how to run Kubernetes. Kubernetes is also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

Every developer, systems admin and tech enthusiast is interested in learning Kubernetes. Kubernetes is a complex container orchestration tool that can be overwhelming for beginners. Kubernetes has been the buzzword in the tech industry 
and for good reason. If you’re itching to get started with Kubernetes and not looking forward to the complexities involved, this first blog is for you. We’ll walk you through getting up and running in a jiffy with a Kubernetes deployment 
using MicroK8s.

What is MicroK8s?
MicroK8s is a powerful, lightweight, reliable production-ready Kubernetes distribution. It is an enterprise-grade Kubernetes distribution that has a small disk and memory footprint while offering carefully selected add-ons out-the-box, 
such as Istio, Knative, Grafana, Cilium and more. Whether you are running a production environment or interested in exploring K8s, MicroK8s serves your needs.

I asked myself, Abe, Why MicroK8s?
MicroK8s is the smallest, fastest multi-node Kubernetes. Single-package fully conformant lightweight Kubernetes that works on Linux, Windows and Mac. Perfect for: Developer workstations, IoT, Edge, CI/CD.

Anyone who’s tried to work with Kubernetes knows the pain of having to deal with getting set up and running with the deployment. There are minimalist solutions in the market that reduce time-to-deployment and complexity 
but the lightweight solutions come at the expense of critical extensibility and missing add-ons.

If you don’t want to spend time jumping through hoops to get Kubernetes up and running, MicroK8s gets you started in under 60 seconds.

Small: Developers want the smallest K8s for laptop and workstation development. MicroK8s provides a standalone K8s compatible with Azure AKS, Amazon EKS, Google GKE when you run it on Ubuntu.
Simple: Minimize administration and operations with a single-package install that has no moving parts for simplicity and certainty. All dependencies and batteries included.
Secure: Updates are available for all security issues and can be applied immediately or scheduled to suit your maintenance cycle.
Current: MicroK8s tracks upstream and releases beta, RC and final bits the same day as upstream K8s. You can track the latest K8s or stick to any release version from 1.10 onwards.
Comprehensive: MicroK8s includes a curated collection of manifests for common K8s capabilities and services:
Service Mesh: Istio, Linkerd
Serverless: Knative
Monitoring: Fluentd, Prometheus, Grafana, Metrics
Ingress, DNS, Dashboard, Clustering
Automatic updates to the latest Kubernetes version
GPGPU bindings for AI/ML
Cilium, Helm and Kubeflow!
MicroK8s glossary
Snaps: Snaps are app packages for desktop, cloud and IoT that are easy to install, secure, cross-platform and dependency-free.
kubectl: A command-line interface for running commands on Kubernetes cluster.
Container: Containers are used as the building blocks of creating applications.
Pod: A pod is a collection of one or more containers that share storage and network resources. Pods contain the definition of how the containers should be run in Kubernetes. For example, you can define you need two pods. During execution, 
if a pod goes down, a new pod will be automatically started.
Service: Since pods are replaceable, Kubernetes needs an abstraction layer to keep the interaction between the different pods seamless. For example, if a pod dies and a new pod is created, the application users shouldn’t be bothered by it. 
Services are wrappers around the pods to create levels of abstraction.
Master: Master coordinates the cluster. It’s like the brains of the operation.
Node: Workers who run the pods.
Prerequisites

To run MicroK8s, you will need a computer with a Linux distribution that supports Snaps such as Ubuntu 🙂 If you have a Windows PC or a Mac, you can use the corresponding MicroK8s native installers.


Getting started

Now that we have the context on what MicroK8s is, and said how easy it is to get started, let’s take it for a spin.

1. Installation

sudo snap install microk8s --classic
In under 60 seconds you should have your distribution up and running!

2. Start MicroK8s and check the status of MicroK8s using the following commands:

sudo microk8s start
microk8s status

The above was the quickest you can get. Try the bellow:

Lets Install MicroK8s on Linux

Run the following commands:
sudo snap install microk8s --classic

Make sure you have the snap command:
Don’t have the snap command? Get set for snaps

Add your user to the microk8s admin group
MicroK8s creates a group to enable seamless usage of commands which require admin privilege. Use the following commands to join the group:

sudo usermod -a -G microk8s $USER
sudo chown -f -R $USER ~/.kube
You will also need to re-enter the session for the group update to take place:

su - $USER
Check the status while Kubernetes starts
microk8s status --wait-ready
Turn on the services you want
microk8s enable dashboard dns ingress
Try microk8s enable --help for a list of available services and optional features. microk8s disable ‹name› turns off a service.

Start using Kubernetes
microk8s kubectl get all --all-namespaces
If you mainly use MicroK8s you can make our kubectl the default one on your command-line with alias mkctl=”microk8s kubectl”. Since it is a standard upstream kubectl, you can also drive other Kubernetes clusters with it 
by pointing to the respective kubeconfig file via the “--kubeconfig” argument.

Access the Kubernetes dashboard
microk8s dashboard-proxy
Start and stop Kubernetes to save battery
Kubernetes is a collection of system services that talk to each other all the time. If you don’t need them running in the background then you will save battery by stopping them. microk8s start and microk8s stop will do the work for you
Read the docs to learn more
