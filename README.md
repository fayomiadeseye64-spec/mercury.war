🚀 Mercury Web Application – AWS Deployment Project

📌 Overview

This project demonstrates the deployment of a Java-based web application (".war" file) on a cloud environment using Amazon Web Services (AWS).

The goal of this project is to showcase practical skills in cloud infrastructure, server configuration, and application deployment using industry best practices.

---

🧠 Project Objective

- Deploy a Java web application on a Linux server
- Configure Apache Tomcat for hosting ".war" applications
- Implement secure and scalable cloud architecture
- Demonstrate real-world cloud engineering workflow

---

⚙️ Technologies Used

- Java (Servlet/JSP)
- Apache Tomcat
- Amazon Web Services (AWS)
- EC2 (Elastic Compute Cloud)
- S3 (Simple Storage Service)
- IAM (Identity and Access Management)
- Linux (Amazon Linux / CentOS)

---

🏗️ Architecture Overview

This project follows a simple cloud architecture:

User → EC2 Instance (Apache Tomcat) → Java Web Application

(Optional enhancements include Load Balancer, CloudFront, and Auto Scaling)

---

🚀 Deployment Steps

1. Launch EC2 Instance

- Choose Amazon Linux or CentOS
- Allow inbound ports:
  - 22 (SSH)
  - 8080 (Tomcat)
  - 80 (HTTP)

---

2. Install Java

sudo yum install java-11 -y
java -version

---

3. Install Apache Tomcat

wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.x/bin/apache-tomcat-9.0.x.tar.gz
tar -xvzf apache-tomcat-9.0.x.tar.gz
mv apache-tomcat-9.0.x tomcat
cd tomcat/bin
chmod +x *.sh
./startup.sh

---

4. Deploy the WAR File

cp mercury.war ~/tomcat/webapps/

---

5. Access the Application

Open in browser:

http://<EC2-PUBLIC-IP>:8080/mercury

---

🔐 Security Best Practices

- Use IAM roles instead of hardcoded credentials
- Restrict SSH access (port 22) to your IP
- Open only necessary ports
- Regularly update system packages

---

📸 Screenshots (To Add)

- EC2 instance running
- Tomcat application page
- AWS dashboard
- Application in browser

---

📈 Future Improvements

- Add Application Load Balancer (ALB)
- Implement Auto Scaling Group
- Configure CloudFront for global delivery
- Use AWS RDS for database integration
- Add HTTPS using ACM (SSL certificate)
- Implement CI/CD pipeline using GitHub Actions

---

🧑‍💼 Author

Fayomi Adeseye Abimbola
Cloud Solution Architect (Junior)

---

⭐ Project Value

This project demonstrates:

- Cloud deployment skills
- Linux server administration
- Java application hosting
- AWS architecture fundamentals

---

📬 Contact

Feel free to connect for collaboration or opportunities.
