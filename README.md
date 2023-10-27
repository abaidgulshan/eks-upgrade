# EKS Upgrade with Terraform Module

![Terraform](https://img.shields.io/badge/Terraform-%23007ACC?style=for-the-badge&logo=terraform&logoColor=white)
![Amazon EKS](https://img.shields.io/badge/Amazon%20EKS-%23232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)

This repository contains how to change Terraform code and documentation for upgrading an Amazon Elastic Kubernetes Service (EKS) cluster using a Terraform module.

## Overview

Upgrading your EKS cluster is a critical operation. This Terraform module simplifies and automates the upgrade process, ensuring that you can perform upgrades reliably and consistently. It allows you to seamlessly upgrade your EKS cluster while adhering to best practices.

## Prerequisites

Before you can use this Terraform module to upgrade your EKS cluster, ensure that you have the following prerequisites in place:

- [Terraform](https://www.terraform.io/downloads.html) installed on your local machine.
- AWS CLI configured with valid credentials. You can configure it using `aws configure`.

## Usage

Follow these steps to upgrade your EKS cluster using this Terraform module:

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/eks-terraform.git
   cd eks-terraform
2. Check the location where we have
   ```bash
   module "eks" {
     source  = "terraform-aws-modules/eks/aws"
     version = "~> 18.20.1"

     cluster_version                 = "1.22"
   ```
   to 
   ```
   module "eks" {
     source  = "terraform-aws-modules/eks/aws"
     version = "~> 18.20.1"

     cluster_version                 = "1.23"
   ```
`terraform apply` and this will upgrade eks cluster and if there is any node group having `1.22` version. This will take about 15 to 20 min. 

## Manual Upgrade for Karpenter worker Nodes
* Check Nodes name with command  and their version
  ```
   kubectl get nodes
  ```
* Drain Node one by one and wait for new node with version 1.23 coming up
  ```
  kubectl drain ip-10-X-X-X.ec2.internal --ignore-daemonsets --delete-local-data
  ```
