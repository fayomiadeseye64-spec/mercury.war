# 🚀 Mercury Web Application – Enterprise AWS Deployment Project

## 📌 Overview

This project demonstrates the deployment of a scalable Java-based web application (`.war` file) on Amazon Web Services (AWS) using a production-style cloud architecture.

The solution architecture was upgraded from a single-server deployment to a highly scalable and resilient infrastructure capable of supporting up to **20 EC2 application servers** as traffic increases over time.

The project showcases practical cloud engineering skills including infrastructure provisioning, Linux server administration, web application deployment, scalability, security, HTTPS implementation, and global content delivery.

---

# 🧠 Project Objective

- Deploy a Java web application on Linux servers using Apache Tomcat
- Configure a scalable AWS infrastructure
- Implement secure HTTPS communication using AWS Certificate Manager (ACM)
- Distribute traffic using Application Load Balancer (ALB)
- Improve global performance using Amazon CloudFront
- Demonstrate enterprise-grade cloud architecture and deployment workflow

---

# ⚙️ Technologies Used

## Cloud Platform
- Amazon Web Services (AWS)

## Compute & Scaling
- EC2 (Elastic Compute Cloud)
- Auto Scaling Group (ASG)
- Application Load Balancer (ALB)

## Networking & Security
- VPC
- Security Groups
- IAM (Identity and Access Management)
- AWS Certificate Manager (ACM)

## Storage & Delivery
- Amazon S3
- Amazon CloudFront

## Application Stack
- Java
- Apache Tomcat 9
- WAR Deployment

## Operating System
- CentOS Linux

---

# 🏗️ Enterprise Architecture Overview

The architecture was redesigned into a scalable production-style system capable of handling increased traffic loads efficiently.

### Architecture Flow

User  
↓  
CloudFront CDN  
↓  
Application Load Balancer (ALB)  
↓  
Auto Scaling Group (Up to 20 EC2 CentOS Servers)  
↓  
Apache Tomcat  
↓  
Mercury Java Web Application (`.war`)

---

# ☁️ AWS Services Implemented

## ✅ Amazon EC2
Used to host Apache Tomcat and the Mercury Java web application.

## ✅ Auto Scaling Group (ASG)
Automatically scales infrastructure from 1 server up to 20 servers depending on traffic demand and health checks.

## ✅ Application Load Balancer (ALB)
Distributes incoming traffic evenly across multiple EC2 instances for high availability and fault tolerance.

## ✅ Amazon CloudFront
Configured as a CDN (Content Delivery Network) to improve global application performance, caching, and latency reduction.

## ✅ AWS Certificate Manager (ACM)
Used to provision and manage SSL/TLS certificates for secure HTTPS communication.

## ✅ Amazon S3
Used for application assets, backups, or static content storage.

## ✅ IAM
Configured for secure permission management and role-based access control.

---

# 🔐 Security Features

- HTTPS enabled using ACM SSL certificate
- CloudFront secured with SSL/TLS
- IAM roles used instead of hardcoded credentials
- SSH access restricted to trusted IP addresses
- Security Groups configured with least privilege access
- Only required ports opened:
  - 22 (SSH)
  - 80 (HTTP)
  - 443 (HTTPS)
  - 8080 (Tomcat Internal Access)

---

# 🚀 Deployment Steps

## 1️⃣ Launch EC2 Instances (CentOS)

Launch CentOS EC2 instances within the Auto Scaling Group.

### Required Security Group Rules

| Port | Protocol | Purpose |
|------|----------|----------|
| 22 | TCP | SSH Access |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |
| 8080 | TCP | Tomcat |

---

## 2️⃣ Connect to EC2 via SSH

### SSH Command

```bash
ssh -i your-key.pem centos@<EC2-PUBLIC-IP>
```

---

## 3️⃣ Update CentOS Server

```bash
sudo yum update -y
```

---

## 4️⃣ Install Java 11

```bash
sudo yum install java-11-openjdk -y
```

### Verify Java Installation

```bash
java -version
```

---

## 5️⃣ Install Apache Tomcat

```bash
cd /opt

sudo wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.105/bin/apache-tomcat-9.0.105.tar.gz

sudo tar -xvzf apache-tomcat-9.0.105.tar.gz

sudo mv apache-tomcat-9.0.105 tomcat9
```

---

## 6️⃣ Configure Tomcat Permissions

```bash
cd /opt/tomcat9/bin

sudo chmod +x *.sh
```

---

## 7️⃣ Start Apache Tomcat

```bash
sudo ./startup.sh
```

---

## 8️⃣ Deploy Mercury WAR File

```bash
sudo cp mercury.war /opt/tomcat9/webapps/
```

---

## 9️⃣ Access the Application

### Direct EC2 Access

```bash
http://<EC2-PUBLIC-IP>:8080/mercury
```

### Production Access Through CloudFront + HTTPS

```bash
https://your-domain-name.com
```

---

# 🌍 CloudFront Configuration

Amazon CloudFront was configured to:

- Improve global application delivery speed
- Cache static content
- Reduce latency
- Improve user experience worldwide
- Provide additional security layer

CloudFront distribution was connected to the Application Load Balancer as the origin.

---

# 🔒 SSL/HTTPS Configuration with ACM

AWS Certificate Manager (ACM) was used to:

- Generate SSL/TLS certificates
- Enable HTTPS communication
- Secure traffic between users and the application
- Integrate securely with CloudFront and ALB

---

# 📈 Scalability Design

The infrastructure supports:

- Automatic horizontal scaling
- Up to 20 EC2 application servers
- High availability across multiple instances
- Traffic distribution using ALB
- Health monitoring and auto replacement of unhealthy instances

This ensures the application remains stable under high traffic conditions.

---

# 📸 Screenshots (To Add)

- EC2 instances running
- Auto Scaling Group configuration
- Application Load Balancer
- CloudFront distribution
- ACM certificate
- Tomcat running on CentOS
- Mercury application browser page
- AWS Architecture Diagram

---

# 🛠️ Future Improvements

- Add Amazon RDS for database management
- Implement CI/CD pipeline using GitHub Actions or Jenkins
- Add Route 53 DNS management
- Configure centralized logging with CloudWatch
- Add Docker containerization
- Implement Kubernetes using Amazon EKS
- Add WAF (Web Application Firewall)
- Implement Infrastructure as Code using Terraform

---

# 🧑‍💼 Author

**Fayomi Adeseye Abimbola**  
Cloud Solution Architect (Junior)

---

# ⭐ Project Value

This project demonstrates:

- Enterprise AWS architecture design
- Linux server administration using CentOS
- Java web application hosting
- Auto Scaling implementation
- Load balancing configuration
- CloudFront CDN integration
- SSL/HTTPS implementation using ACM
- Production-style cloud deployment workflow
- AWS infrastructure scalability and security best practices

---

# 📬 Contact

Feel free to connect for collaboration, cloud engineering opportunities, or technical discussions.
