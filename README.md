


# Flask-on-Docker 🚀

## 📌 Overview

This repository contains a **containerized Flask web application** that runs with **Nginx as a reverse proxy** and **PostgreSQL as the database**. The application is fully Dockerized, making it easy to deploy in different environments. Using `docker-compose`, you can quickly spin up the services, ensuring a reliable and scalable development setup. This project demonstrates best practices for container orchestration and is a great example of a production-ready Flask application.

---

### 🎥 **Screenshot of Image Upload (GIF)**
Below is an animated GIF showing the process of uploading an image:

![Uploading Image](services/web/project/media/ScreenRecording1.gif)


---

## 🦐 **Build Instructions**

### **1️⃣ Clone the Repository**

```bash
git clone https://github.com/LukeF2/flask-on-docker.git
cd flask-on-docker
```

### **2️⃣ Build and Run the Containers**

```bash
docker-compose -f docker-compose.prod.yml up -d --build
```

This command will: ✅ **Build the Flask app**\
✅ **Start the PostgreSQL database**\
✅ **Launch Nginx as a reverse proxy**

### **3️⃣ Verify Everything is Running**

To check if all services are up and running, execute:

```bash
docker ps
```

Expected output:

```
CONTAINER ID   IMAGE                   PORTS                      NAMES
xxxxx          flask-on-docker-nginx    0.0.0.0:9090->80/tcp       flask-on-docker-nginx-1
xxxxx          flask-on-docker-web      5000/tcp                   flask-on-docker-web-1
xxxxx          postgres:13              5432/tcp                   flask-on-docker-db-1
```

### **4️⃣ Test the Application**

#### 🔹 **On the Remote Server**

Run:

```bash
curl http://127.0.0.1:9090/
```

Expected output:

```json
{"hello": "world"}
```

#### 🔹 **Access Locally via SSH Port Forwarding**

On your **local machine**, run:

```bash
ssh <your.email>@lambda.compute.cmc.edu -p 5055 -L localhost:8080:127.0.0.1:9090
```

Now open a browser and go to:

```
http://localhost:8080/
```

---

## 📝 **Contributing**

Pull requests are welcome! If you'd like to suggest improvements, please open an issue to discuss your changes before submitting a pull request.

---

## 📄 **License**

This project is licensed under the MIT License.

