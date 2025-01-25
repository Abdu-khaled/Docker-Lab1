# Docker Web Application Stack

This repository contains the files and instructions to set up a **Docker-based web application stack** using **Nginx** and **PostgreSQL**. It also includes answers to theory questions related to Docker fundamentals, image management, and networking.

---

## **Repository Structure**

docker-webapp/
├── markdown-files/           # Markdown files for theory answers
│   ├── Pic/                  # Images for theory answers
│   │   ├── pic1.png
│   │   └── pic2.png
│   └── TheoryQ.md            # Answers to theory questions
├── ubuntu-nginx/             # Files for Nginx setup
│   ├── Dockerfile            # Dockerfile for Nginx
│   ├── index.html            # Custom HTML file for Nginx
│   └── webapp/               # Web application files
│       └── html/             # HTML files for Nginx
├── docker-compose.yml        # Docker Compose file for multi-container setup
└── README.md                 # This file

---

## **Practical Tasks**

### **1. Dockerfile for Nginx**

- **Location**: `ubuntu-nginx/Dockerfile`
- **Description**: This Dockerfile uses Ubuntu as the base image, installs Nginx, and serves a custom `index.html` file.
- **Instructions**:
  1. Build the Docker image:
     ```bash
     docker build -t my-nginx .
     ```
  2. Run the container:
     ```bash
     docker run -d -p 8080:80 --name nginx-web my-nginx
     ```
  3. Access the web server at `http://localhost:8080`.

---

### **2. Multi-Container Setup with Docker Compose**

- **Location**: `docker-compose.yml`
- **Description**: This file sets up a web application stack with Nginx and PostgreSQL. It ensures the database is persistent using a Docker volume.
- **Instructions**:
  1. Start the stack:
     ```bash
     docker compose up -d
     ```
  2. Access the Nginx server at `http://localhost:8080`.
  3. Connect to the PostgreSQL database:
     ```bash
     docker exec -it postgres-db psql -U admin -d mydb
     ```

---

### **3. Resource Limiting**

- **Description**: Run the Nginx container with resource limits (512MB memory and 1 CPU core).
- **Instructions**:
  1. Run the container with resource limits:
     ```bash
     docker run -d --name nginx-web --memory="512m" --cpus="1" -p 8080:80 nginx:latest
     ```
  2. Verify resource limits using `docker stats nginx-web`.

---

## **Theory Questions**

The answers to the theory questions are located in the `markdown-files/` directory:

- **Theory Answers**: `markdown-files/TheoryQ.md`
- **Images**: `markdown-files/Pic/`

---

## **How to Use This Repository**

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/docker-webapp.git
   cd docker-webapp


   ```
2. Navigate to the ubuntu-nginx/ directory to run the Docker tasks.
3. Refer to the markdown-files/ directory for detailed explanations of Docker concepts.

---

## Contributing

If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---



