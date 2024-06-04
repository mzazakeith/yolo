# YOLO

- Yolo is a MERN (MongoDB, Express, React, Node.js) stack application. For Moringa DevOps IP2, IP3 and IP4.
- View also [explanation.md](https://github.com/mzazakeith/yolo/blob/master/explanation.md)

# Prerequisites

Before running the application with Docker Compose, ensure that you have the following prerequisites installed on your system:
1. The latest version of Docker Desktop.

# Setup

- To run the application using Docker Compose, follow these steps:

# Clone the repository:

```bash
git clone git@github.com:mzazakeith/yolo.git
```

# Navigate to the project directory:
```bash
cd yolo
```

# Run Docker Compose:

```bash
docker-compose up
```

- This will build and start the application containers.

# Images on Docker Hub

- The application images are available on Docker Hub:
    - Frontend Image: [mzazakeith/yolo-app-client:1.0.0](https://hub.docker.com/repository/docker/mzazakeith/yolo-app-client/general)
    - Backend Image: [mzazakeith/yolo-app-backend:1.0.0](https://hub.docker.com/repository/docker/mzazakeith/yolo-app-backend/general)

>Note:These images are versioned and tagged accordingly.

# Usage
- Once the Docker containers are up and running, you can access the application at:
    - Frontend: http://localhost:3000
    - Backend: http://localhost:5000

# License
This project is licensed under the [MIT License.](https://github.com/mzazakeith/yolo/blob/master/LICENSE.md)
