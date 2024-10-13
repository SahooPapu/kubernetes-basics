# kubernetes-basics
1) What is Kubernetes

			- Orchestration Platform
			- To manage containers
			- Developed by Google using Go language
			- Google donated K8S to CNCF
			- K8S first version released in 2015
			- It is free & Open source

Note: Kubernetes will use Docker internally. Using K8S we will manage our Docker containers.


2) Docker Swarm Vs K8S
	
			- Docker Swarm doesn't have Auto Scaling (Scaling is manual process)
			- K8S supports Auto Scaling 
			- For Production deployments K8S is highly recommended
			- Kubernetes is replacement for Docker Swarm

Auto Scaling : Increasing and Decreasnig containers count based on incoming requests for our app.

3) What is Cluster 

			 - Group Of Servers
			 - Master Node(s)
			 - Worker Node(s)			
			 - DevOps Enginner / Developer will give the task to K8S Master Node
			 - Master Node will manage worker nodes
			 - Master Node will schedule tasks to worker nodes
			 - Our containers will be created in Worker Nodes
			 - Using Cluster we can achieve High Availability

4) Kubernetes Architecture

			 - Control Plane / Master Node / Manager Node
				 - Api Server
				 - Schedular
				 - Control Manager
				 - ETCD
			
			 - Worker Node (s)
				- Pods
				- Containers
				- Kubelet
				- Kube Proxy
				- Docker Runtime
5) How to communicate with K8S control plane ?

				- Kubectl (CLI tool)

				- Web UI Dashboard
Kubernetes Architecture Components
====================================

Control Plane : Control Plane is called as Master Node (Responsible to handle k8s related work)

Worker Nodes: Responsible to execute our application as PODS.


=>  API Server : It is responsible to handle incoming requests of Control Plane ( to deploy our applications)

=>  Etcd : It is an internal database in K8S cluster, API Server will store requests / tasks info in ETCD

=>  Schedular : It is responsible to schedule pending tasks available in ETCD. It will decide in which worker node our task should execute. Schedular will decide that by communicating with Kubelet.

=> Kubelet : It is a worker node agent. It will maintain all the information related to Worker Node.

=> Conroller-Manager : After scheduling completed, Controller-Manager will manage our task execution in worker node

=> Kube-Proxy : It will provide network for K8S cluster communication 
				(Master Node <---> Worker Nodes)

=> Docker Engine : To run our containers Docker Engine is required. Containers will be created in Worker Nodes.

=> Container : It is run time instance of our application

=> POD : It is a smallest building block that we will create in k8s to run our containers.

Note: Docker Containers will run inside POD.

Kubernetes Cluster Setup
========================

1) Self Managed Cluster ( We will create our own cluster )
		
		a) Mini Kube ( Single Node Cluster )

		b) Kubeadm  (Multi Node Cluster)

2) Provider Managed Cluster (Cloud Provide will give read made cluster) ---> Charges applies

		a) AWS EKS

		b) Azure  AKS
	
		c) GCP GKE
