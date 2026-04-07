# 🚀 AWS Security Group Practical (Allow / Block Ports)

## 📌 Project Overview

This project demonstrates how Security Groups control traffic by allowing and blocking ports in an EC2 instance.

---

## 🧰 Services Used

* AWS EC2
* Security Groups
* Apache Web Server

---

## ⚙️ Setup Steps

### 1️⃣ Launch EC2

* Amazon Linux
* Allow SSH (22) initially

---

### 2️⃣ Install Apache

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
```

---

### 3️⃣ Allow HTTP (Port 80)

* Go to Security Group
* Add inbound rule:

  * Type: HTTP
  * Port: 80
  * Source: Anywhere (0.0.0.0/0)

✔ Open browser → Website works

---

### 4️⃣ Remove HTTP Rule

* Delete port 80 rule

❌ Website stops loading

---

### 5️⃣ Test SSH (Port 22)

```bash
ssh -i your-key.pem ec2-user@your-ip
```

✔ Works when port 22 allowed

---

### 6️⃣ Remove SSH Rule

* Delete port 22 rule

❌ SSH connection fails

---

## 🧪 Test Results

| Action        | Result        |
| ------------- | ------------- |
| Allow Port 80 | Website works |
| Block Port 80 | Website fails |
| Allow Port 22 | SSH works     |
| Block Port 22 | SSH fails     |

---

## 💡 Key Learning

* Security Groups act as firewall
* Ports control access to services
* Blocking a port = blocking access

---

## 🔗 Author

Guna A – AWS & DevOps Learner
