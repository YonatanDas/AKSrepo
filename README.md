# AKSrepo
 
To complete the documentation efficiently, we’ll focus on structuring everything you have and explaining any limitations (like the free-tier restriction) clearly. Here’s a simple, organized way to structure your README document:

DevOps Junior Take-Home Task

Overview

This document outlines the steps I followed to complete the DevOps Junior take-home task. The assignment involves setting up infrastructure on Azure using Terraform, deploying a web application to a Kubernetes cluster, and configuring a CI/CD pipeline using Azure DevOps.

1. Infrastructure Setup (Terraform)

Steps:

	1.	Initialize Terraform:
	•	Used terraform init to initialize the working directory.
	2.	Resource Provisioning:
	•	Created a Kubernetes Cluster (AKS) with the following resources:
	•	Resource Group
	•	AKS Cluster
	•	Azure Container Registry (ACR)
	•	Networking and security components
	3.	Apply the Configuration:
	•	Ran terraform apply to deploy the infrastructure on Azure.
	4.	Terraform Files:
	•	The configuration is modular, and variables are stored separately. The main components are located in the following files:
	•	main.tf: Defines resources.
	•	variables.tf: Defines variables used across modules.
	•	outputs.tf: Defines the outputs for important resource values.

Challenges and Resolutions:

	•	Challenge: Managing the correct versions of Terraform providers and Azure modules.
	•	Resolution: Ensured compatibility by locking provider versions.

2. Kubernetes Deployment (YAML)

Steps:

	1.	Deployment File: A deployment.yaml file is created to deploy a simple “Hello World” web application.
	2.	Service Configuration: A service.yaml file defines the external IP or LoadBalancer to expose the application.
	3.	Ingress: Not implemented due to time constraints.
	4.	Kubernetes Files:
	•	deployment.yaml: Configures the application pods.
	•	service.yaml: Exposes the application via an external service.

Challenges and Resolutions:

	•	Challenge: Testing the external accessibility of the application without running the deployment.
	•	Resolution: Manually verified the configurations and included them for testing.

3. CI/CD Pipeline (Azure DevOps)

Steps:

	1.	Pipeline Configuration:
	•	Configured a basic CI/CD pipeline using YAML in Azure DevOps.
	•	The pipeline is designed to:
	•	Build the Docker image of the web application.
	•	Push the image to Azure Container Registry (ACR).
	•	Deploy the image to the AKS cluster.
	2.	Pipeline Stages:
	•	Build Stage: Uses the Dockerfile to build the image.
	•	Deploy Stage: Deploys the application using kubectl commands to the AKS cluster.
	3.	YAML Pipeline Configuration:
	•	The azure-pipelines.yml contains all pipeline stages.

Challenges and Resolutions:

	•	Challenge: The pipeline could not run due to free-tier restrictions.
	•	Resolution: I documented the pipeline steps and tested configurations locally but was unable to run the full pipeline due to Azure free-tier limitations.

4. Documentation of Issues Faced

	•	CI/CD Pipeline Restrictions: The Azure free-tier account does not support enough resources to run the CI/CD pipeline.
	•	Solution: I provided the full YAML pipeline configuration and explained how it would run in a non-restricted environment.
	•	Time Constraints: Focused on modular, reusable configurations and limited scope to critical components (no advanced networking like Ingress).

5. Conclusion

	•	All the necessary files (Terraform configurations, Kubernetes YAMLs, and CI/CD pipeline YAML) are provided in this repository.
	•	Due to Azure account restrictions, the CI/CD pipeline is not fully operational, but all configurations are in place for future use.
	•	Any further improvements, such as implementing Ingress or testing with a paid Azure account, can be addressed in future iterations.

File Structure:

|-- terraform/
|   |-- main.tf
|   |-- variables.tf
|   |-- outputs.tf
|-- kubernetes/
|   |-- deployment.yaml
|   |-- service.yaml
|-- azure-pipelines.yml
|-- README.md

