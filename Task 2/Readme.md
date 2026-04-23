Task-2 (Docker Deployment)
## Objective
Deploy a containerized web application using Docker.

## Installation & Setup

### 1. Install Docker
```bash
sudo apt update
sudo apt install docker.io -y
```

### 2. Start Docker Service
```bash
sudo systemctl start docker
sudo systemctl enable docker
```

## Application Files

### index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Docker Deployment</title>
</head>
<body style="margin:0; padding:0; background-color:#f4f6f9; font-family:Arial, sans-serif; display:flex; justify-content:center; align-items:center; height:100vh;">
    <div style="background:#ffffff; padding:40px; border-radius:10px; box-shadow:0 4px 15px rgba(0,0,0,0.1); text-align:center; width:90%; max-width:500px;">
        <h1 style="color:#2c3e50; margin-bottom:20px;">🚀 Successfully Deployed in Docker</h1>
        <p style="color:#555; font-size:16px; margin-bottom:15px;">This application is now running inside a Docker container.</p>
        <p style="color:#333; font-size:15px; background:#eef2ff; padding:10px; border-radius:6px;">📌 Task Submission: This deployment demonstrates successful containerization and execution of the application using Docker.</p>
        <p style="margin-top:20px; font-size:12px; color:#888;">Deployment Status: Active & Running</p>
    </div>
</body>
</html>
```

### Dockerfile
```dockerfile
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
```

## Deployment Steps

### Build Docker Image
```bash
docker build -t my-web-app .
```

### Run Container
```bash
docker run -d -p 8000:80 --name web-container my-web-app
```

### Access Application
```
http://<server-ip>:8000
```

## Results
- ✅ Docker container successfully running
- ✅ Web app accessible via browser on port 8000
