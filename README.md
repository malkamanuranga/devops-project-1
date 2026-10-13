# DevOps Project: Containerized Flask Application with Automated Testing

A lightweight Python Flask web application engineered to demonstrate foundational DevOps practices, local containerization, and automated testing workflows. This repository serves as the baseline architecture for an upcoming CI/CD pipeline integration.

---

## 🛠️ Tech Stack

* **Language:** Python 3.10
* **Framework:** Flask
* **Testing:** Pytest
* **Containerization:** Docker
* **Version Control:** Git & GitHub

---

## 📁 Project Structure

```text
devops-project-1/
├── .github/workflows/   # CI/CD pipeline configurations (Coming Soon)
├── .gitignore           # Excluded files and directories (venv, cache, etc.)
├── app.py               # Main Flask application entry point
├── Dockerfile           # Multi-stage/base image container build instructions
├── requirements.txt     # Python runtime dependencies
├── test_app.py          # Pytest automated test suite
└── README.md            # Project documentation

```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed locally:

* Python 3.10+
* Docker Desktop
* Git

### 1. Local Development Setup

Clone the repository and configure your virtual environment:

```bash
git clone https://github.com/malkamanuranga/devops-project-1.git
cd devops-project-1

# Create and activate virtual environment
python -m venv venv

# Windows (PowerShell / Command Prompt)
.\venv\Scripts\activate

# macOS / Linux
source venv/bin/activate

```

Install the project dependencies:

```bash
pip install -r requirements.txt

```

### 2. Running the Application

Start the local development server:

```bash
python app.py

```

Open [http://localhost:5000](http://localhost:5000) in your browser to verify the application is running.

### 3. Running Automated Tests

Execute the test suite using `pytest`:

```bash
pytest test_app.py

```

---

## 🐳 Docker Deployment

To build and run the application inside a container:

### Build the Docker Image

```bash
docker build -t devops-flask-app .

```

### Run the Container

```bash
docker run -d -p 5000:5000 --name flask-container devops-flask-app

```

Access the containerized application at [http://localhost:5000](http://localhost:5000).

To stop and remove the container when finished:

```bash
docker stop flask-container
docker rm flask-container

```

---

## 🗺️ Roadmap

* [ ] Implement GitHub Actions workflow for automated build and test on push.
* [ ] Configure AWS infrastructure provisioning.
