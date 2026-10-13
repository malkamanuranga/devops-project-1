

# DevOps Project: Containerized Flask Application with Automated CI/CD Pipeline

![CI/CD Pipeline](https://github.com/malkamanuranga/devops-project-1/actions/workflows/deploy.yml/badge.svg)

A fully automated, containerized Python Flask web application demonstrating modern DevOps practices. This project features a complete Continuous Integration and Continuous Deployment (CI/CD) pipeline that automatically tests code, builds a Docker image, pushes it to DockerHub, and deploys it to a live AWS EC2 instance.

## 🛠️ Tech Stack
*   **Language:** Python 3.10
*   **Framework:** Flask
*   **Testing:** Pytest
*   **Containerization:** Docker
*   **CI/CD:** GitHub Actions
*   **Cloud Infrastructure:** AWS EC2
*   **Registry:** DockerHub
*   **Version Control:** Git & GitHub

## 📁 Project Structure
```text
devops-project-1/
├── .github/workflows/
│   └── deploy.yml       # CI/CD Pipeline configuration (GitHub Actions)
├── .gitignore           # Excluded files (venv, cache, etc.)
├── app.py               # Main Flask application entry point
├── Dockerfile           # Docker container build instructions
├── requirements.txt     # Python runtime dependencies
├── test_app.py          # Pytest automated test suite
└── README.md            # Project documentation
```

## 🚀 Local Development
### Prerequisites
Ensure you have the following installed locally:
*   Python 3.10+
*   Docker Desktop
*   Git

### 1. Setup
```bash
git clone https://github.com/malkamanuranga/devops-project-1.git
cd devops-project-1

# Create and activate virtual environment
python -m venv venv
# Windows: .\venv\Scripts\activate
# macOS/Linux: source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 2. Run Locally
```bash
python app.py
```
Open `http://localhost:5000` to view the app. Run tests with `pytest test_app.py`.

### 3. Docker Deployment
```bash
docker build -t my-devops-app .
docker run -d -p 5000:5000 --name my-app my-devops-app
```

## 🤖 CI/CD Pipeline Architecture
This project utilizes GitHub Actions to automate the deployment lifecycle. On every push to the `main` branch, the pipeline executes two jobs:

1.  **Build and Push:**
    *   Checks out the code.
    *   Sets up Python 3.10.
    *   Installs dependencies and runs automated tests (Pytest).
    *   Logs into DockerHub.
    *   Builds the Docker image and pushes it to the registry.
2.  **Deploy:**
    *   SSHes into the AWS EC2 instance using secure GitHub Secrets.
    *   Pulls the latest Docker image from DockerHub.
    *   Stops the old container, removes it, and starts the new container on port 80.

### Required GitHub Secrets
The pipeline relies on the following repository secrets configured in GitHub:
*   `DOCKERHUB_USERNAME`
*   `DOCKERHUB_TOKEN`
*   `EC2_HOST`
*   `EC2_USERNAME`
*   `EC2_SSH_KEY`

## 🌐 Live Demo
The application is deployed on an AWS EC2 instance. 
*(Note: The live URL may change if the EC2 instance is restarted, as it uses a dynamic public IP).*
**URL:** `http://98.93.117.126`

## 🗺️ Roadmap
- [x] Implement GitHub Actions workflow for automated build and test on push.
- [x] Configure AWS infrastructure provisioning (EC2, Security Groups, Route Tables).
- [x] Implement automated deployment to AWS EC2.
- [ ] Migrate infrastructure provisioning to Terraform (IaC).
- [ ] Implement HTTPS/SSL via Nginx and a custom domain.
```
