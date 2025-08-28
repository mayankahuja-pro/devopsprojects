DevOps Intern Project: Node.js App on AWS EC2 with Docker
This project showcases a simple Node.js web application deployed on AWS EC2 using Docker, demonstrating core DevOps skills such as Linux system administration, AWS cloud deployment, and containerization. An optional CI/CD pipeline using GitHub Actions automates Docker image builds and pushes to Docker Hub, highlighting modern DevOps practices.
🌟 Project Overview

Purpose: Built to demonstrate DevOps competencies for an intern role, including Linux, AWS, and Docker.
Application: A lightweight Node.js Express app serving a webpage.
Deployment: Hosted on an AWS EC2 instance (Ubuntu) using Docker.
Live Demo: Accessible at http://13.233.183.141/ (replace with your EC2 public IP).
Optional CI/CD: Automated Docker image builds and pushes via GitHub Actions.

🛠 Technologies Used

Node.js: Backend framework for the web app.
Docker: Containerization for consistent deployment.
AWS EC2: Cloud infrastructure for hosting.
Ubuntu Linux: OS for EC2 instance, managed via CLI.
GitHub Actions: (Optional) For CI/CD automation.
Docker Hub: (Optional) For storing Docker images.

📂 Project Structure
devops-intern-project/
├── index.js              # Node.js app code
├── package.json          # Dependencies and scripts
├── Dockerfile            # Docker configuration
├── .github/workflows/    # CI/CD pipeline (optional)
│   └── docker.yml
└── README.md             # Project documentation

🚀 Setup Instructions
Prerequisites

Node.js and npm (for local testing)
Docker (local and on EC2)
AWS account (free-tier EC2)
GitHub account
Docker Hub account (optional, for CI/CD)

1. Local Setup

Clone the repository:git clone https://github.com/mayankahuja-pro/devops-intern-project.git
cd devops-intern-project


Install dependencies and test locally:npm install
node index.js

Open http://localhost:3000 to verify the app displays "Hello from My DevOps Project 🚀".
Dockerize the app:docker build -t my-devops-app .
docker run -p 3000:3000 my-devops-app

Verify at http://localhost:3000.

2. Deploy on AWS EC2

Launch EC2 Instance:
Use AWS Console to create a free-tier Ubuntu 20.04 LTS instance (t2.micro).
Configure security group to allow:
SSH (port 22)
HTTP (port 80)


Download the key pair (e.g., my-key.pem).


SSH into EC2:chmod 400 my-key.pem
ssh -i my-key.pem ubuntu@13.233.183.141


Install Docker:sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu

Log out and back in to apply permissions.
Deploy the App:git clone https://github.com/YOUR_USERNAME/devops-intern-project.git
cd devops-intern-project
docker build -t my-devops-app .
docker run -d -p 80:3000 my-devops-app

Access the app at http://YOUR_EC2_PUBLIC_IP.

3. (Optional) CI/CD Pipeline

Configure GitHub Actions:
Add .github/workflows/docker.yml (see repository for the file).
Set up Docker Hub secrets in GitHub (Settings → Secrets and variables → Actions):
DOCKER_USERNAME: Your Docker Hub username.
DOCKER_PASSWORD: Your Docker Hub password or access token.




Push changes to trigger the pipeline:git add .github/workflows/docker.yml
git commit -m "Add CI/CD pipeline"
git push


Pull and run the image on EC2:docker pull YOUR_DOCKERHUB_USERNAME/my-devops-app:latest
docker run -d -p 80:3000 YOUR_DOCKERHUB_USERNAME/my-devops-app:latest



✅ Deliverables

GitHub Repository: https://github.com/YOUR_USERNAME/devops-intern-project
Live Application: http://YOUR_EC2_PUBLIC_IP
Skills Demonstrated:
Linux: Managed Ubuntu on EC2 via CLI.
AWS: Configured and deployed on EC2 with security groups.
Docker: Containerized the app for portability.
CI/CD (Optional): Automated deployments with GitHub Actions.



📝 Notes

This project was built in under 8 hours to meet a tight deadline, showcasing efficient DevOps workflows.
The live app may require an active EC2 instance to remain accessible.
For any issues, refer to the repository or contact me via GitHub.
