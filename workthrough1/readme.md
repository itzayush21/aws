# 🚀 Full-Stack AWS Deployment: Java Web App with Tomcat, Memcached, MariaDB, RabbitMQ

This project showcases the **end-to-end deployment of a full-stack Java web application** on **AWS**, using EC2, S3, IAM, Route 53, and an Application Load Balancer. All infrastructure setup and configurations are automated using shell scripts and follows AWS best practices.

---

## 📌 Project Highlights

- 🧱 4 EC2 instances (Tomcat + 3 backend services)
- 🔐 Security groups for load balancer, app, and backend layers
- ☁️ WAR deployment via S3 using IAM roles and policies
- 📡 Private Route 53 DNS for internal hostname resolution
- ⚖️ Application Load Balancer with Target Group for routing
- 🧪 Fully automated using Bash scripts

---

## 🔧 Tech Stack

| Layer        | Tool/Service       |
|--------------|--------------------|
| App Server   | Tomcat (Java WAR)  |
| Build Tool   | Maven              |
| Database     | MariaDB            |
| Messaging    | RabbitMQ           |
| Caching      | Memcached          |
| Cloud Infra  | AWS (EC2, S3, Route 53, IAM, ALB) |
| Scripts      | Bash               |

---

## 📂 Repository Structure
```
aws-vprofile-deployment/
├── README.md                        # Project overview and setup instructions
├── scripts/                         # Bash automation scripts
│   ├── setup-tomcat.sh
│   ├── setup-backend.sh
│   ├── deploy-artifact.sh
│   └── README.md                   # Explain each script’s purpose and usage
├── application/                     # App artifact and config
│   ├── vprofile.war
│   ├── application.properties
│   └── README.md                   # Describe .war deployment, Maven build, properties
├── iam/                             # IAM roles and policies
│   ├── s3-access-policy.json
│   ├── s3-access-policy.md         # Describe IAM policy logic and S3 connection
│   └── README.md                   # IAM users, roles, and permissions
├── route53/                         # Internal DNS setup
│   ├── private-dns-setup.md        # Private hosted zone config and usage
│   └── README.md                   # Naming conventions and internal resolution
├── architecture/                   # System layout and design
│   ├── architecture-diagram.png
│   └── architecture.md             # Description of architecture diagram
└── docs/                            # Detailed documentation
    ├── deployment-flow.md          # Full AWS deployment pipeline explained
    ├── load-balancer-config.md     # ALB, listeners, and target groups setup
    ├── future-improvements.md      # Suggestions for improvements (e.g., monitoring, IaC)
    └── troubleshooting.md          # Common issues and how to resolve them
```




---

## 🔁 Deployment Flow Overview

1. **Launch EC2 Instances**:
   - 1 for Tomcat app server (`vprofile-app-sg`)
   - 3 for backend services: DB, Cache, Queue (`vprofile-backend-sg`)

2. **Configure Servers via Scripts**:
   - Shell scripts install required software and configure them automatically.

3. **S3 Artifact Deployment**:
   - WAR file is uploaded to S3.
   - IAM Role on EC2 allows pulling the artifact securely.

4. **Private DNS Setup**:
   - Route 53 private zone created for internal naming.
   - e.g., `db.vprofile.internal`, `mq.vprofile.internal`

5. **Application Load Balancer**:
   - Public-facing ALB forwards traffic to EC2 in the Target Group (Tomcat).
   - Health checks and listener rules are configured.

---

## 🎯 Features Demonstrated

- ✅ Infrastructure automation via Bash
- ✅ Secure access to S3 using IAM roles
- ✅ Application Load Balancing with routing
- ✅ Internal DNS resolution using Route 53 Private Hosted Zone
- ✅ Full-stack integration with real-world services

---

## 📸 Architecture Diagram

> *Insert architecture image here once available*



