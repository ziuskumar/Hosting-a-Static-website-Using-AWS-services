# 🌐 AWS Static Website Deployment (S3 + EC2)

## 📌 Project Overview

This project demonstrates how to deploy and host a static website using AWS cloud services. The website files (HTML, CSS, JavaScript) are first uploaded to Amazon S3, then transferred to an EC2 instance, and finally served over HTTP using the Apache web server.

---

## 🎯 Objective

To understand the process of cloud-based deployment using AWS services including storage (S3), compute (EC2), and web hosting via Apache.

---

## 🛠️ Technologies Used

* AWS S3 (Storage)
* AWS EC2 (Virtual Server)
* AWS IAM (Access Management)
* Apache Web Server (httpd)
* Linux (Amazon Linux)
* AWS CLI

---

## 🧩 Project Architecture

Local System → S3 Bucket → EC2 Instance → Apache Server → Browser

---

## 🚀 Implementation Steps

### 1️⃣ Create S3 Bucket

* Created a bucket in AWS S3
* Used it to store website files

---

### 2️⃣ Upload Files to S3

* Created folder: `Jio-Hotstar`
* Uploaded:

  * index.html
  * style.css
  * script.js

---

### 3️⃣ Launch EC2 Instance

* OS: Amazon Linux
* Instance type: t2.micro
* Enabled ports:

  * SSH (22)
  * HTTP (80)

---

### 4️⃣ Connect to EC2

* Used EC2 Instance Connect (browser-based SSH)
* Accessed Linux terminal

---

### 5️⃣ Install Apache Web Server

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

---

### 6️⃣ Setup AWS CLI and IAM

* Installed AWS CLI
* Created IAM user
* Generated Access Key & Secret Key

```bash
aws configure
```

---

### 7️⃣ Fix Permissions

```bash
sudo chmod -R 777 /var/www/html
```

---

### 8️⃣ Sync Files from S3 to EC2

```bash
aws s3 sync s3://zius-s3-sucket /var/www/html/
```

---

### 9️⃣ Move Files for Hosting

```bash
sudo cp -r /var/www/html/Jio-Hotstar/* /var/www/html/
```

---

### 🔟 Access Website

Open in browser:
```
http://<EC2-PUBLIC-IP>
```

---

## ✅ Output

The static website was successfully hosted on an EC2 instance and accessed via a public IP address over HTTP.

---

## 🧠 Key Learnings

* Understanding of cloud storage (S3)
* Deployment using EC2
* Working with Linux commands
* Managing permissions in Linux
* Using AWS CLI for automation
* Basics of web hosting using Apache

---

## ⚠️ Note

Permissions were set using `chmod 777` for simplicity. In real-world applications, secure permission handling is recommended.

---

## 🔥 Conclusion

This project demonstrates a complete workflow of deploying a static website on AWS using S3 and EC2. It provides practical exposure to cloud infrastructure and real-world deployment processes.

---
