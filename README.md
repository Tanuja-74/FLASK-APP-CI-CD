# 🚀 Flask CI/CD Pipeline using Jenkins

A complete CI/CD pipeline project for deploying a Flask application using Jenkins, GitHub, AWS EC2, and PM2.

---

## 📌 Project Overview

This project demonstrates how to automate the deployment of a Flask application using a CI/CD pipeline.

* Flask application developed in Python
* Jenkins used for automation
* GitHub used for version control
* PM2 used as process manager
* Deployed on AWS EC2 instance

---

## 🛠️ Tech Stack

* Python (Flask)
* Jenkins
* GitHub
* AWS EC2
* PM2

---

## 📂 Project Structure

```
FLASK-APP-CI-CD/
│
├── frontend-flask/
│   ├── app.py
│   ├── requirements.txt
│   └── templates/
│
└── Jenkinsfile
```

---

## ⚙️ Setup & Installation

### 1. Clone Repository

```bash
git clone https://github.com/Tanuja-74/FLASK-APP-CI-CD.git
cd FLASK-APP-CI-CD/frontend-flask
```

---

### 2. Install Dependencies

```bash
pip3 install -r requirements.txt
```

---

### 3. Run Application

```bash
python3 app.py
```

---

### 4. Access Application

```
http://<YOUR-EC2-PUBLIC-IP>:5000
```

---

## 🔄 CI/CD Pipeline (Jenkins)

Pipeline is configured using Jenkinsfile.

### Pipeline Stages:

1. Install Dependencies
2. Run Application using PM2

---

## 📜 Jenkinsfile

```groovy
pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('frontend-flask') {
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }

        stage('Run App') {
            steps {
                dir('frontend-flask') {
                    sh '/usr/bin/pm2 restart flask-app || /usr/bin/pm2 start app.py --name flask-app --interpreter python3'
                }
            }
        }
    }
}
```

---

## 🔔 Webhook Integration

GitHub webhook is configured to automatically trigger Jenkins pipeline on every code push.

```
http://<YOUR-EC2-PUBLIC-IP>:8080/github-webhook/
```

---

## 📊 Output

* Jenkins pipeline runs successfully
* Flask app deployed automatically
* Application managed using PM2

---

## 📸 Screenshots

(Add below screenshots)

* Jenkins Build Success
* Running Application in Browser

---

## 💡 Key Learnings

* CI/CD pipeline implementation
* Jenkins automation
* GitHub integration with Jenkins
* Process management using PM2

---

## 👩‍💻 Author

**Tanuja Kurane**

---

## ⭐ Future Enhancements

* Add testing stage in pipeline
* Dockerize the application
* Deploy using Kubernetes

---
