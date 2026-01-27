# YouTube Showcase App CI/CD with Jenkins & Docker

This project demonstrates a fully automated CI/CD pipeline for a static web application showcasing YouTube videos, playlists, and shorts. It uses Jenkins to automate the build process and package the site into a high-performance Nginx container.

## 🚀 System Architecture

1.  **Source Control**: HTML5 source code and Docker configuration are managed in GitHub.
2.  **CI/CD Pipeline**: Jenkins triggers a build on every commit to the repository.
3.  **Containerization**: Jenkins builds a Docker image based on **Nginx Alpine** to ensure a lightweight footprint.
4.  **Web Server**: The app uses Nginx to serve the static HTML content efficiently.
5.  **Deployment**: The containerized app is ready to be deployed to any environment running Docker.

## 🛠 Tech Stack
*   **Frontend:** HTML5 / CSS3
*   **Web Server:** Nginx (Alpine Linux)
*   **CI/CD:** Jenkins
*   **Containerization:** Docker

## 📂 Project Structure
*   `index.html` - The main website containing the YouTube embeds and custom CSS.
*   `Dockerfile` - Instructions to package the app into the Nginx container.

## ⚙️ CI/CD Setup

### 1. Dockerfile Logic
The build process ensures a clean and optimized production environment:
*   Uses `nginx:alpine` as the base image for minimal resource usage.
*   Removes default Nginx static files to avoid conflicts.
*   Injects the local `index.html` into the Nginx web root.
*   Exposes port `80` for web traffic.

### 2. Jenkins Automation
The pipeline is designed to:
*   Pull the latest code from the GitHub repository.
*   Execute the `docker build` command to create the image.
*   Tag the image for version control and deployment readiness.

## 🏃 How to Run the App Locally

If you want to run the application manually:

### Using Docker
```bash
# Build the image
docker build -t youtube-showcase .

# Run the container
docker run -d -p 8080:80 youtube-showcase
