# Zero-Local Jenkins CI/CD Pipeline

I wanted to build a production-grade CI/CD pipeline without that runs entirely in the cloud, leveraging AWS, Docker, and Jenkins to automate the linting and containerization of a Python microservice.

## Tech Stack
* Cloud Platform: AWS (EC2)
* Automation Engine: Jenkins (Declarative Pipeline via Jenkinsfile)
* Containerization: Docker (Using multi-stage builds for optimization)
* Application: Python (Flask API)


## Why This?
* 100% Cloud-Native: No local Git or software dependencies. Everything was built, configured, and managed through secure cloud terminals and web interfaces.
* Optimized Build Layering: Used a multi-stage Dockerfile to keep the final production image lightweight by dropping unnecessary build tools.
* Networking: Handled live AWS Security Groups and custom inbound firewall routing to securely expose port 8080 for automation streams.


## Workflow

### 1. AWS EC2 Hosting Node
My self-hosted Jenkins automation server running live on a cloud compute instance.
> [<img width="1897" height="894" alt="Screenshot 2026-06-07 012159" src="https://github.com/user-attachments/assets/ee355af7-9d53-435d-985b-23f0d36b6d56" />
]

### 2. Network Firewall Configuration
Custom security rules opening up Port 8080 (Jenkins UI) and Port 22 (SSH) for secure remote access.
> [<img width="1625" height="405" alt="Screenshot 2026-06-07 012301" src="https://github.com/user-attachments/assets/040a9cd6-6e67-479f-8343-8ec266d4e008" />
]

### 3. Successful Pipeline Execution
A straight line of green checkmarks confirming the codebase was successfully checked out, validated, and built into a Docker container.
> [<img width="1888" height="953" alt="Screenshot 2026-06-07 015621" src="https://github.com/user-attachments/assets/3e763da8-3629-48c4-ae37-e85627a07e34" />
]
