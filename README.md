# 🚀 Node.js “Hello World” App on AWS EC2

This repository contains a simple **Node.js Hello World** application deployed on an **AWS EC2 instance**.  
It demonstrates how to host and manage a Node.js backend on Amazon Web Services using the Free Tier.

---

## 🧰 Tech Stack
- **Node.js** — JavaScript runtime environment  
- **AWS EC2 (Ubuntu)** — Cloud hosting  
- **PM2** — Process manager for uptime  
- **GitHub** — Version control and project documentation  

---

## ⚙️ Deployment Steps

### 1️⃣ Launch an EC2 Instance
- Log in to [AWS Management Console](https://aws.amazon.com/console/)
- Launch an **Ubuntu Server (Free Tier eligible)**
- Allow **HTTP (port 80)** and **SSH (port 22)** access
- Connect to your instance:
  ```bash
  ssh -i your-key.pem ubuntu@<your-ec2-public-ip>

  
2️⃣ Install Node.js
sudo apt update
sudo apt install -y nodejs npm


3️⃣ Create the App
mkdir hello-world
cd hello-world
nano index.js

Paste this code:
const http = require('http');
const hostname = '0.0.0.0';
const port = 80;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World from AWS EC2!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

Run it:
sudo node index.js

Visit http://<your-ec2-public-ip> and you’ll see:
Hello World from AWS EC2!


4️⃣ Keep It Running Forever (PM2)
sudo npm install -g pm2
pm2 start index.js
pm2 save
pm2 startup systemd

✅ Your app will now restart automatically on reboot.

🌍 Demo
Access your live app at:
http://<your-ec2-public-ip>

(Replace <your-ec2-public-ip> with your actual EC2 address.)

👤 Author
Richard Adeoye (lexzzyy)
Hands-on Project — AWS EC2 + Node.js
GitHub: @lexzzyy

---

### 📝 STEP 3 — Save the README
Scroll to the bottom and click:  
✅ **“Commit new file”**

---

Once done, refresh your repo homepage — GitHub will automatically render your README beautifully at the bottom of your repository page. 🎉  

Would you like me to add your **actual EC2 public IP** into the README demo section before you commit it (so it’s clickable and people can test it)?
