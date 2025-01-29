# Open WebUI Deployment

This project provides a Kubernetes deployment setup for the Open WebUI application. It includes configuration files for deploying the application, setting up persistent storage, and managing ingress rules.

## Project Structure

- **02_pvc.yml**: Defines a PersistentVolumeClaim for storing application data.
- **03_deployment.yml**: Contains the deployment configuration for the Open WebUI application.
- **05_svc.yml**: Sets up a Kubernetes Service to expose the application.
- **06_ingress.yml**: Configures ingress rules for external access to the application.
- **setup.sh**: A script to set up the environment and deploy the application to a Kubernetes cluster.

## Prerequisites

- Kubernetes cluster
- `kubectl` command-line tool
- Access to a container registry

## Setup and Deployment

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Configure Environment Variables**:
   Edit the `setup.sh` script to set the `NAMESPACE` and `FQDN` variables according to your environment.

3. **Run the Setup Script**:
   Execute the `setup.sh` script to prepare the environment and deploy the application:
   ```bash
   ./setup.sh
   ```

4. **Access the Application**:
   Once deployed, the application will be accessible via the configured FQDN.

## Notes

- Ensure that the specified namespace does not already exist in your cluster, or modify the script to handle existing namespaces.
- The ingress configuration assumes the use of the Traefik ingress controller. Adjust the `ingressClassName` if using a different controller.
