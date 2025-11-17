# Cloud-Infrastructure-and-Dual-Service-Deployment-on-AWS-EC2-NGINX-and-Docker
Project Description:
This project demonstrates core DevOps and Cloud skills by provisioning an AWS EC2 instance and deploying two independent services on the same server, highlighting proficiency in Linux administration and container management.
Key Achievements:
1- System Administration & Troubleshooting: Configured an Amazon Linux 2023 EC2 instance, correctly identifying and using the dnf package manager instead of apt.
2- Web Server Deployment (NGINX): Installed and configured the NGINX web server to serve content on the default HTTP Port 80.
3- Containerized Application Deployment (Docker & Node.js): Successfully built a custom Docker image from a Dockerfile, resolved critical JSON syntax errors within the Node.js configuration, and deployed the application container.
4- Networking & Ports: Configured the server to run NGINX on Port 80 and the Dockerized Node.js app on Port 3000, managing access for both services via AWS Security Groups.
5- Troubleshooting: Resolved Docker build failures and corrected the required build context argument (docker build .).

Tools Used: AWS EC2, Amazon Linux 2023, DNF, NGINX, Docker, Node.js/Express, SSH.
🛠️ Complete Project Guide and Commands Used
This guide focuses solely on the installation, configuration, and troubleshooting steps you performed.
Phase 1: NGINX Web Server Setup (Port 80)
Install NGINX and Enable Service
Bash
sudo dnf update -y
sudo dnf install nginx -y
sudo systemctl enable nginx
sudo systemctl start nginx
Verification
Action: Open AWS Security Group to allow Port 80 (HTTP) inbound traffic.
Access: http://YOUR_SERVER_IP/
Phase 2: Dockerized Node.js Application Deployment (Port 3000)
Fix Configuration File
Action: Edit package.json to fix JSON syntax error.
Bash
nano package.json
Build the Docker Image
Bash
docker build -t nodeapp-image .
Phase 3: Run the Container
Bash
docker run -d --name nodeapp -p 3000:3000 nodeapp-image
Verification
Action: Open AWS Security Group to allow Port 3000 (Custom TCP) inbound traffic.
Access: http://YOUR_SERVER_IP:3000
<img width="1384" height="633" alt="image" src="https://github.com/user-attachments/assets/0fee6433-75d1-4d68-b9ed-c65c1a29fc49" />
<img width="795" height="431" alt="image" src="https://github.com/user-attachments/assets/2a2eb398-c36c-42be-82fa-fcd78742a476" />
<img width="1040" height="444" alt="image" src="https://github.com/user-attachments/assets/ea9fa342-258f-4472-bd93-9c2926cef6dd" />

Action: Open AWS Security Group to allow Port 3000 (Custom TCP) inbound traffic.
Access: http://YOUR_SERVER_IP:3000
