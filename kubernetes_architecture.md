# Kubernetes Architecture Explained

This document provides an overview of the key components that form the architecture of a Kubernetes cluster, simplified for easy comprehension.
Table of Contents

    1. Control Plane (Master Node Components)
        1.1 API Server
        1.2 etcd
        1.3 Scheduler
        1.4 Controller Manager
        1.5 Cloud Controller Manager
    2. Worker Node Components
        2.1 kubelet
        2.2 kube-proxy
        2.3 Container Runtime
    3. Other Components
        3.1 Pod
        3.2 Service
        3.3 Volume
        3.4 Namespace
        3.5 Ingress

![Kubernetes Architecture Diagram](https://miro.medium.com/v2/resize:fit:1400/1*0Sudxeu5mQyN3ahi1FV49A.png)

1. Control Plane (Master Node Components)

The Control Plane is responsible for managing the overall state of the cluster, and it includes the following components:
1.1 API Server

    Acts as the "front door" of Kubernetes.
    All interactions with the cluster go through the API Server.
    It handles authentication, authorization, and exposes the Kubernetes API.

1.2 etcd

    A highly available, key-value store that holds all cluster data.
    Think of it as the cluster's "database."
    Stores configuration, state, and metadata about nodes and pods.

1.3 Scheduler

    The "event planner" for Kubernetes workloads.
    Determines which node (worker) should run a pod based on resource requirements and constraints.

1.4 Controller Manager

    A collection of controllers responsible for regulating cluster state.
    Ensures the cluster matches the desired state, e.g., restarting pods if they crash.

1.5 Cloud Controller Manager

    Manages interactions between Kubernetes and the underlying cloud provider (AWS, Azure, etc.).
    Responsible for cloud-specific tasks like managing load balancers and storage.

2. Worker Node Components

Worker nodes run your application workloads (pods) and ensure that they function correctly.
2.1 kubelet

    The "node manager" responsible for ensuring all containers in the node are running and healthy.
    Communicates with the control plane to receive instructions.

2.2 kube-proxy

    Acts as the "traffic cop" that manages network routing.
    Directs traffic between services and pods or external clients and services.

2.3 Container Runtime

    The software responsible for running containers.
    Examples include Docker, containerd, or CRI-O.

3. Other Components

Additional components that enhance the functionality of a Kubernetes cluster.
3.1 Pod

    The smallest and simplest unit in Kubernetes.
    A Pod can contain one or more containers that share storage and networking.
    Think of it as a "house" for your containers.

3.2 Service

    Provides a stable IP and DNS name for a set of pods, allowing easy discovery and access.
    Think of it as the "address book" that enables communication between different parts of your app.

3.3 Volume

    A storage unit attached to a pod to store data persistently.
    Similar to an external hard drive that can be shared by containers in a pod.

3.4 Namespace

    A mechanism to divide cluster resources among different teams or users.
    Like creating separate folders on a shared computer for each team.

3.5 Ingress

    Controls HTTP and HTTPS access to services inside the cluster from external clients.
    Think of it as the "gateway" for external traffic into the cluster.