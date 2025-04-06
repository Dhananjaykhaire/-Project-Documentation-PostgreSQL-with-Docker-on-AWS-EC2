📌 Objective:
To set up a secure and portable PostgreSQL container using Docker on an AWS EC2 instance, allowing seamless database deployment and scaling.

⚙️ Tools & Technologies Used:
AWS EC2 (Ubuntu 20.04)
Docker
PostgreSQL (Official Image)
Linux CLI
SSH & Key-based authentication

🔧 Steps to Reproduce:
1. Launch an AWS EC2 Instance:
Choose Ubuntu as the OS.

Generate and download a .pem key pair.

In Security Group, allow:

SSH (22) from your IP.

PostgreSQL (5432) from your IP or anywhere (for dev).

2. Connect to EC2:
bash
Copy
Edit
ssh -i "your-key.pem" ubuntu@your-ec2-public-ip
3. Install Docker:
bash
Copy
Edit
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
4. Create a Dockerfile:
Dockerfile
Copy
Edit
# Dockerfile
FROM postgres:latest

ENV POSTGRES_USER=myuser
ENV POSTGRES_PASSWORD=mypassword
ENV POSTGRES_DB=mydatabase
5. Build Docker Image:
bash
Copy
Edit
docker build -t my-postgres-image .
6. Run PostgreSQL Container:
bash
Copy
Edit
docker run --name my-postgres-container \
  -e POSTGRES_USER=myuser \
  -e POSTGRES_PASSWORD=mypassword \
  -e POSTGRES_DB=mydatabase \
  -p 5432:5432 -d my-postgres-image
7. Connect to PostgreSQL inside Container:
bash
Copy
Edit
docker exec -it my-postgres-container bash
psql -U myuser -d mydatabase
8. Optional – Access Remotely (DEV only):
Modify /var/lib/postgresql/data/pg_hba.conf and postgresql.conf inside container for remote access.

Expose 5432 in EC2 security group.




