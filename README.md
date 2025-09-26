
# Flask Notes App with Docker & CI/CD

A simple **Flask-based Notes web application** containerized with Docker and automated with GitHub Actions CI/CD pipeline. This project demonstrates modern DevOps practices, including Docker builds, image pushes to Docker Hub, automated workflow triggers, and deployment on an **AWS EC2 instance**.

---

## **Features**

* Create, read, update, and delete notes.
* RESTful API endpoints for note management.
* Fully containerized with Docker.
* Automated CI/CD using GitHub Actions.
* Deployed and running on **AWS EC2**.
* Easy to scale and extend.

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
git clone https://github.com/akanksha106-code/flask-notes-docker.git
cd flask-notes-docker
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

### **EC2 Deployment**

The app is deployed on an **AWS EC2 instance**:

1. Launch an EC2 instance (Amazon Linux 2023 recommended).
2. SSH into your instance and install Docker:

```bash
sudo dnf update -y
sudo dnf install docker -y
sudo service docker start
```

3. Pull Docker image from Docker Hub:

```bash
docker pull akanksha106/flask-notes-docker:latest
```

4. Run the container:

```bash
docker run -d -p 80:5000 akanksha106/flask-notes-docker
```

5. Access your app via the EC2 public IP:
   `http://<your-ec2-public-ip>`

---

### **GitHub Actions CI/CD**

Configured to automatically:

1. Build the Docker image.
2. Push it to **Docker Hub** whenever code is merged into `main`.
3. Optional: trigger EC2 deployment using SSH or AWS CLI (can be extended).

> **GitHub Actions secrets required:**
>
> * `DOCKERHUB_USERNAME` → Your Docker Hub username
> * `DOCKERHUB_TOKEN` → Personal access token with read/write permission
> * (Optional) `EC2_SSH_KEY` → Your private key for automated EC2 deployment

---

### **Project Structure**

```
flask-notes-docker/
│
├── app.py              # Main Flask application
├── Dockerfile          # Docker configuration
├── requirements.txt    # Python dependencies
├── .github/
│   └── workflows/
│       └── docker.yml  # CI/CD workflow for GitHub Actions
└── README.md
```

---

### **Statistics / Metrics**

| Metric           | Status                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------ |
| **Build Status** | ![Build Status](https://github.com/akanksha106-code/flask-notes-docker/actions/workflows/main.yml/badge.svg) |
| **Docker Pulls** | ![Docker Pulls](https://img.shields.io/docker/pulls/akanksha106/flask-notes-docker)                          |
| **Commits**      | ![Commits](https://img.shields.io/github/commit-activity/m/akanksha106-code/flask-notes-docker)              |
| **GitHub Stars** | ![Stars](https://img.shields.io/github/stars/akanksha106-code/flask-notes-docker)                            |

---


### **License**

This project is **MIT licensed**.




Do you want me to do that too?

