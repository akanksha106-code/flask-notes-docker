

# Flask Notes App with Docker & CI/CD

A **Flask-based Notes web application**, fully containerized with Docker and automated with **GitHub Actions CI/CD pipeline**. This project demonstrates modern DevOps practices, including:

* Building and pushing Docker images to Docker Hub
* Automated CI/CD workflow on GitHub
* Deployment on an **AWS EC2 instance**

It’s designed to be easy to deploy, extend, and scale.

---

## **Features**

* Create, read, update, and delete notes
* RESTful API endpoints for note management
* Fully containerized with Docker for consistent environments
* Automated CI/CD using GitHub Actions
* Deployed and running on **AWS EC2**
* Easy to scale and maintain

---

## **Tech Stack**

* **Backend:** Python, Flask
* **Containerization:** Docker
* **CI/CD:** GitHub Actions
* **Hosting/Deployment:** AWS EC2
* **Version Control:** Git & GitHub

---

## **Getting Started**

### **Prerequisites**

* Python 3.9+
* Docker
* Git
* AWS account (for EC2 deployment)

---

### **Clone the Repository**

```bash
git clone https://github.com/akankshatech/flask-notes-app.git
cd flask-notes-app
```

---

### **Run Locally with Docker**

1. Build Docker image:

```bash
docker build -t flask-notes-app .
```

2. Run Docker container:

```bash
docker run -p 5000:5000 flask-notes-app
```

3. Open your browser: [http://localhost:5000](http://localhost:5000)

---

### **Deploy on AWS EC2**

The app can be deployed on an **AWS EC2 instance**:

1. Launch an EC2 instance (Amazon Linux 2023 recommended)
2. SSH into the instance and install Docker:

```bash
sudo dnf update -y
sudo dnf install docker -y
sudo service docker start
```

3. Pull Docker image from Docker Hub:

```bash
docker pull akankshatech/flask-notes-app:latest
```

4. Run the container:

```bash
docker run -d -p 80:5000 akankshatech/flask-notes-app
```

5. Access the app via EC2 public IP:
   `http://<your-ec2-public-ip>`

> **Tip:** Ensure your EC2 security group allows HTTP traffic on port 80.

---

### **GitHub Actions CI/CD**

The project is configured to automatically:

1. Build the Docker image
2. Push the image to **Docker Hub** when code is merged into `main`
3. Optionally, deploy to EC2 using SSH or AWS CLI

> **Required GitHub Secrets:**
>
> * `DOCKERHUB_USERNAME` → Docker Hub username
> * `DOCKERHUB_TOKEN` → Docker Hub personal access token with write permission
> * (Optional) `EC2_SSH_KEY` → Private key for EC2 deployment

---

### **Project Structure**

```
flask-notes-app/
│
├── app.py              # Main Flask application
├── Dockerfile          # Docker configuration
├── requirements.txt    # Python dependencies
├── .github/
│   └── workflows/
│       └── docker.yml  # CI/CD workflow
└── README.md
```

---





