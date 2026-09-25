# Highly Available 3-Tier Web Architecture on AWS

## 📌 Project Overview

This project demonstrates a highly available web infrastructure built on AWS using a custom VPC, public and private subnets, Application Load Balancer, Auto Scaling Group, NAT Gateways, Route 53 and AWS Certificate Manager.

The infrastructure is distributed across three Availability Zones to improve availability and provide scalable web application infrastructure.

## 🏗️ Architecture

Route 53
   ↓
Application Load Balancer
   ↓
Auto Scaling Group
   ↓
EC2 Instances
   ↓
Private Subnets

Internet
   ↓
Internet Gateway
   ↓
Public Subnets
   ↓
NAT Gateways
   ↓
Private Subnets

## 🛠️ AWS Services Used

- Amazon VPC
- Amazon EC2
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- NAT Gateway
- Internet Gateway (IGW)
- Route 53
- AWS Certificate Manager (ACM)
- Security Groups

## 🌐 Network Architecture

- Custom VPC: `prod-vpc`
- VPC CIDR: `10.0.0.0/16`
- 3 Availability Zones
- 3 Public Subnets
- 3 Private Subnets
- 3 NAT Gateways
- Internet Gateway
- Public and Private Route Tables

## ⚖️ Load Balancing & Auto Scaling

An internet-facing Application Load Balancer distributes incoming HTTP/HTTPS traffic across EC2 instances.

The Auto Scaling Group was configured with:

- Minimum instances: 1
- Desired instances: 3
- Maximum instances: 7

EC2 instances were deployed across multiple Availability Zones.

## 🔐 Security

Security Groups were configured to control traffic between the Application Load Balancer and backend EC2 instances.

The backend EC2 instances were deployed in private subnets rather than being directly exposed to the internet.

## 🔒 HTTPS & Custom Domain

AWS Certificate Manager was used to configure the SSL/TLS certificate.

Route 53 was configured with the custom domain:

`api.saurabhchavan.shop`

HTTPS traffic was configured through the Application Load Balancer.

## 🔄 Traffic Flow

1. User accesses the custom domain.
2. Route 53 resolves the domain.
3. Traffic reaches the Application Load Balancer.
4. ALB performs health checks and distributes traffic.
5. Traffic is forwarded to healthy EC2 instances.
6. EC2 instances run in private subnets.
7. NAT Gateways provide outbound internet connectivity for private resources.

## 📷 Project Screenshots

Screenshots demonstrating the VPC, subnets, route tables, NAT Gateways, ALB, Auto Scaling Group, EC2 instances, Route 53 and HTTPS configuration are included in this repository.

## 📚 Documentation

Detailed implementation steps and configuration screenshots are available in the project documentation.

---

## 👨‍💻 Author

**Saurabh Chavan**

AWS & DevOps Enthusiast
