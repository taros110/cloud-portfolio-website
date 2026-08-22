Cloud Portfolio Website

About This Project
This project is a personal portfolio website that I am building while developing practical skills in cloud computing, DevOps, Linux administration, containerization, automation, and software development.

The project is deployed on an Ubuntu Linux environment running on AWS EC2 and is managed using Git and GitHub.

The application is containerized with Docker and Docker Compose, served through Nginx as a reverse proxy, and automatically deployed using GitHub Actions.

Project Goals
This project provides hands-on experience with:

Cloud infrastructure
Linux administration
Version control
Containerization
Reverse proxy configuration
CI/CD automation
Cloud deployment
Secure SSH access
Infrastructure as Code
Monitoring and documentation
Technologies
Development
HTML5
CSS3
Git
GitHub
SSH
Cloud & Infrastructure
AWS EC2
AWS IAM
AWS Security Groups
Ubuntu Linux
Containers & Deployment
Docker
Docker Compose
GitHub Actions
Nginx
Current Features
Personal portfolio webpage
Structured HTML
CSS styling
Git version control
GitHub repository
AWS EC2 deployment
Ubuntu Linux server administration
Docker containerization
Docker Compose configuration
Nginx web server
Nginx reverse proxy
AWS Security Group configuration
Automated CI/CD deployment with GitHub Actions
GitHub Actions encrypted secrets for EC2 deployment
Deployment Architecture
The portfolio is deployed to an AWS EC2 Ubuntu server.

Nginx receives public HTTP traffic on port 80 and acts as a reverse proxy to the Dockerized portfolio application.

                         Internet
                            |
                            | HTTP :80
                            v
                    AWS Security Group
                            |
                            v
                       AWS EC2
                            |
                            v
                     Ubuntu Linux
                            |
                            v
                      Nginx :80
                            |
                    Reverse Proxy
                            |
                            v
                  Docker Compose
                            |
                            v
               Portfolio Container :80
                            |
                            v
                    Portfolio Website
CI/CD Architecture
The project uses GitHub Actions to automate deployment.

When changes are pushed to the main branch, GitHub Actions first validates the Docker Compose configuration. If validation succeeds, the workflow connects securely to the EC2 server using SSH, pulls the latest changes, and rebuilds the Docker Compose application.

Developer
    |
    | git push
    v
  GitHub
    |
    v
GitHub Actions
    |
    +------------------+
    |                  |
    v                  v
Validate            Deploy
Docker Compose        |
    |                 |
    +-------+---------+
            |
            v
          EC2
            |
            v
         git pull
            |
            v
    Docker Compose build
            |
            v
    Updated Portfolio
Development Workflow
The project is managed using Git and GitHub.

Typical development workflow:

Edit Website
     |
     v
git status
     |
     v
git add
     |
     v
git commit
     |
     v
git push
     |
     v
GitHub Actions
     |
     v
Automated Deployment
Changes pushed to the main branch trigger the CI/CD workflow.

Docker
The application is containerized using Docker.

The Dockerfile defines how the portfolio application is packaged into a Docker image.

Docker Compose is used to manage the running container through compose.yaml.

The application can be started with:

docker compose up -d
The container exposes port 80 internally and is mapped to port 8080 on the EC2 host.

Nginx receives public traffic on port 80 and forwards requests to the Docker container.

GitHub Actions
The project uses GitHub Actions for continuous integration and continuous deployment.

The workflow performs two main jobs:

1. Validate
The workflow checks out the repository and validates the Docker Compose configuration.

2. Deploy
After successful validation, GitHub Actions connects to the EC2 server using encrypted GitHub repository secrets.

The deployment process:

Connects to the EC2 server.
Navigates to the project directory.
Pulls the latest changes from GitHub.
Rebuilds the Docker image.
Restarts the application using Docker Compose.
This allows website updates to be deployed without manually rebuilding the application on the server.

Project Structure
cloud-portfolio-website/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── css/
│   └── style.css
├── index.html
├── Dockerfile
├── compose.yaml
└── README.md
What I Am Learning
I am developing practical skills in cloud computing, DevOps, Linux administration, and software development through hands-on projects and self-directed learning.

Cloud & DevOps
AWS cloud services and infrastructure
Linux administration and command-line operations
Git and GitHub version control
SSH and secure remote access
Docker and containerization
Docker Compose
Nginx and reverse proxy configuration
CI/CD and automated deployments
Infrastructure as Code
Cloud monitoring and logging
Programming & Development
Python fundamentals and scripting
HTML and CSS
Automation and scripting for DevOps workflows
Future Improvements
Planned improvements include:

Configure HTTPS using TLS certificates
Connect a custom domain
Create AWS infrastructure using Terraform
Add automated application testing
Add monitoring and logging
Improve website design and mobile responsiveness
Add links to additional Cloud and DevOps projects
Further improve deployment security
Expand the CI/CD pipeline with additional validation and testing
Author
Rosaline Mpeh Tanyi

Aspiring Cloud & DevOps Engineer
