

````markdown
# Project 1: Let's Play with Docker Containers

**CECS 327 - Networks & Distributed Computing** 

## Overview

This project demonstrates the fundamentals of containerization using Docker. It includes the deployment of a custom Python application, a modified Nginx web server using volume mounting, and a multi-container network orchestrated via Docker Compose.

---

## Prerequisites

* **Docker Desktop** (Windows/macOS) or **Docker Engine** (Linux).  
* **System Requirements:** Minimum 4GB RAM and 20GB free storage.  
* **Terminal:** Access to CMD, PowerShell, or Bash.  

---

## How to Build and Run the Project

### Task 1: Nginx Web Server with Volume Mounting

This task deploys an Nginx server and replaces its default landing page with a custom `index.html`.

1. Navigate to the project directory:  
   ```cmd
   C:\Users\HoFamily\my_dockerapp
````

2. Execute the following command to run the container and mount the local `index.html`:

   **Windows (CMD):**

   ```cmd
   docker run -d -p 8080:80 -v "%cd%/index.html":/usr/share/nginx/html/index.html --name my-nginx nginx:latest
   ```

3. Open your browser and visit:

   ```
   http://localhost:8080
   ```

---

### Task 2: Multi-Container Setup (Server + Clients)

This task uses Docker Compose to orchestrate communication between a Python TCP server and multiple client containers.

1. Ensure you are in the project directory containing `docker-compose.yml`.

2. Build the images and start the containers:

   ```cmd
   docker-compose up --build
   ```

3. **Verification:** Observe the terminal logs. You will see the server listening and the clients successfully receiving messages.

   * **Server Log:** `Connected successfully to client at...`
   * **Client Log:** `Received from server: Message received! Hello from the Docker Server.`

---

## Troubleshooting

* **Permission Denied:** Run commands with `sudo` (Linux) or ensure Docker Desktop is running with administrator privileges (Windows).
* **Port Already in Use:** If port 8080 is occupied, stop existing containers using:

  ```cmd
  docker stop <container_name>
  ```

  or change the host port mapping (e.g., `-p 8081:80`).
* **Logs:** To view logs for a specific container, use:

  ```cmd
  docker logs <container_id>
  ```

---

## Submission Checklist

* [ ] **Report:** PDF/Word explaining Dockerfile steps and individual contributions.
* [ ] **Code:** `server.py`, `client.py`, and `index.html` with detailed comments.
* [ ] **Docker:** `Dockerfile` and `docker-compose.yml`.
* [ ] **Video:** Link to the execution recording.

```

This is now fully Markdown-ready, clean, and structured with headings, code blocks, and lists.  

If you want, I can also make it **look even nicer on GitHub** by adding badges, emojis, and table of contents links. It’ll make it more professional. Do you want me to do that?
```
