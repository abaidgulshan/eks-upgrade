# EKS Upgrade with Terraform Module

![Terraform](https://img.shields.io/badge/Terraform-%23007ACC?style=for-the-badge&logo=terraform&logoColor=white)
![Amazon EKS](https://img.shields.io/badge/Amazon%20EKS-%23232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)

This repository contains Terraform code and documentation for upgrading an Amazon Elastic Kubernetes Service (EKS) cluster using a Terraform module.

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
   git clone https://github.com/yourusername/eks-upgrade-terraform.git
   cd eks-upgrade-terraform

## Backup current EKS cluster 