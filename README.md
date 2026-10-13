
DevOps Project 1: Dockerized Flask App + Automated Testing


📌 What's this about?

This is a straightforward Python Flask app built to showcase fundamental DevOps practices. The main goal here was to set up a solid baseline for Continuous Integration (CI) by containerizing the application and making sure unit tests run automatically.
It’s a clean, minimal setup meant to serve as a building block for more complex pipelines.

🛠️ The Tech Stack

• Backend: Python 3.10 & Flask
• Testing: Pytest
• Containerization: Docker
• Source Control: Git + GitHub

📁 Project Structure

text
devops-project-1/
├── .github/workflows/   # (Coming Soon) CI/CD pipeline configs
├── .gitignore           # Keeps venv, __pycache__, etc. out of source control
├── app.py               # The main Flask application
├── Dockerfile           # Blueprint for building the Docker image
├── requirements.txt     # Python package dependencies
├── test_app.py          # Automated unit tests via Pytest
└── README.md            # You are here!
