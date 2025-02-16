# CI/CD Pipeline with Jenkins, Docker, Kubernetes, and AWS

This project demonstrates a modern, automated CI/CD pipeline integrating industry-standard DevOps tools and practices.

## Architecture Overview

![CI/CD Pipeline Architecture](docs/images/architecture.png)

### Key Components

- **CI/CD Pipeline (Jenkins)**
  - Automated build, test, and deployment pipeline
  - GitHub webhook integration
  - Multi-stage pipeline with quality gates
  
- **Containerization & Orchestration**
  - Docker for application containerization
  - Kubernetes (AWS EKS) for container orchestration
  - AWS ECR for container registry

- **Infrastructure as Code**
  - Terraform for AWS infrastructure provisioning
  - Kubernetes manifests for deployment configuration
  - Helm charts for package management

- **Monitoring & Observability**
  - Prometheus for metrics collection
  - Grafana for visualization and dashboards
  - Alert management and notification system

## Project Structure

```
.
├── .github/                    # GitHub Actions workflows
├── jenkins/                    # Jenkins pipeline configurations
│   ├── Jenkinsfile            # Main pipeline definition
│   └── scripts/               # Pipeline utility scripts
├── terraform/                  # Infrastructure as Code
│   ├── eks/                   # EKS cluster configuration
│   ├── jenkins/               # Jenkins server setup
│   └── monitoring/            # Prometheus & Grafana setup
├── kubernetes/                 # Kubernetes configurations
│   ├── deployments/           # Application deployments
│   ├── services/              # Service definitions
│   └── configmaps/            # Configuration files
├── monitoring/                 # Monitoring configurations
│   ├── prometheus/            # Prometheus configuration
│   └── grafana/               # Grafana dashboards
└── src/                       # Sample application source code
```

## Prerequisites

- AWS Account with appropriate permissions
- GitHub account
- Docker installed locally
- kubectl installed locally
- Terraform installed locally
- AWS CLI configured

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/cicd-pipeline-demo.git
   cd cicd-pipeline-demo
   ```

2. **Configure AWS Credentials**
   ```bash
   aws configure
   ```

3. **Initialize Terraform**
   ```bash
   cd terraform
   terraform init
   terraform plan
   terraform apply
   ```

4. **Configure Jenkins**
   - Access Jenkins at http://jenkins-server-ip:8080
   - Install suggested plugins
   - Configure GitHub webhook
   - Add AWS credentials

5. **Deploy Application**
   ```bash
   kubectl apply -f kubernetes/
   ```

## Monitoring Setup

1. Access Grafana dashboard at http://grafana-ip:3000
2. Import provided dashboards from monitoring/grafana/dashboards
3. Configure alerting rules as needed

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please read our [Contributing Guide](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.
