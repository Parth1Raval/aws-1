🚀 Terraform Deployment: Flask Backend & Express Frontend on AWS

This project demonstrates how to deploy a Flask backend and an Express frontend on AWS using Terraform, starting from basic EC2 deployments and moving towards a production-ready setup with VPC, Load Balancer, and Target Groups.

I’ve explained everything in a simple, human-readable way with screenshots so even beginners can follow along.

🛠️ Tech Stack Used

AWS (EC2, VPC, ALB, Target Groups)

Terraform

Flask (Python Backend)

Express (Node.js Frontend)

Linux (Amazon EC2)

📌 What This Project Covers
✅ Part 1: Flask & Express on a Single EC2 Instance

One EC2 instance

Flask running on port 5000

Express running on port 3000

✅ Part 2: Flask & Express on Separate EC2 Instances

Two EC2 instances

Separate security groups

Inter-instance communication enabled

✅ Part 3: AWS Networking with Load Balancer

Custom VPC

Subnets

Application Load Balancer

Target Groups

Traffic routing using ALB listeners

⚙️ Step 1: Create VPC Using Terraform

We start by creating a custom VPC instead of using the default one.
This gives us full control over networking and security.

🔹 What’s happening here?

Custom VPC

Public subnets

Internet Gateway

Route Tables

📸 Screenshot – VPC Dashboard

You can see the created VPC and subnets in the AWS console after running terraform apply.

⚙️ Step 2: Launch EC2 Instances

Terraform provisions EC2 instances automatically.

🔹 What happens during EC2 creation?

Amazon Linux AMI

Security Groups attached

User Data installs:

Python

Node.js

Flask

Express

📸 Screenshot – EC2 Instance

⚙️ Step 3: Configure Security Groups

Security groups act like firewalls.

🔹 Opened Ports
Service    	Port
SSH	        22
Flask	      5000
Express    	3000
HTTP	      80

This ensures the apps are accessible from the browser.

⚙️ Step 4: Create Application Load Balancer (ALB)

The Application Load Balancer distributes incoming traffic to EC2 instances.

🔹 Why ALB?

High availability

Better traffic management

Scalable architecture

📸 Screenshot – Load Balancer Listener

⚙️ Step 5: Configure Target Groups

Target Groups define where traffic should go.

🔹 Target Group Setup

Protocol: HTTP

Port: 80

Health checks enabled

EC2 instances registered

📸 Screenshot – Target Groups

▶️ How to Run This Project

1️⃣ Clone the Repository

git clone https://github.com/your-username/terraform-flask-express.git
cd terraform-flask-express

2️⃣ Initialize Terraform
terraform init

3️⃣ Validate Configuration
terraform plan

4️⃣ Deploy Infrastructure
terraform apply

🧠 Key Learnings

Infrastructure as Code using Terraform

AWS VPC and networking basics

Load Balancer & Target Group configuration

Automating EC2 setup with user data

Real-world deployment practices
