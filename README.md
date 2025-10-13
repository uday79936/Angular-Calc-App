
# 🧮 Angular Calculator Deployment Lab on Ubuntu

![Angular](https://img.shields.io/badge/Framework-Angular-red?logo=angular)
![Ubuntu](https://img.shields.io/badge/OS-Ubuntu-orange?logo=ubuntu)
![Nginx](https://img.shields.io/badge/WebServer-Nginx-green?logo=nginx)
![License](https://img.shields.io/badge/License-MIT-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📑 Table of Contents
1. [🎯 Objective](#-objective)
2. [🧰 Materials Needed](#-materials-needed)
3. [📘 Prerequisites](#-prerequisites)
4. [🧪 Procedure](#-procedure)
   - [1️⃣ Setting up the Environment](#1️⃣-setting-up-the-environment)
   - [2️⃣ Clone the Angular Repository](#2️⃣-clone-the-angular-repository)
   - [3️⃣ Install Dependencies](#3️⃣-install-dependencies)
   - [4️⃣ Build the Angular Application](#4️⃣-build-the-angular-application)
   - [5️⃣ Install and Configure Nginx](#5️⃣-install-and-configure-nginx)
   - [6️⃣ Test the Application](#6️⃣-test-the-application)
5. [🏁 Conclusion](#-conclusion)
6. [⚙️ Troubleshooting Tips](#%EF%B8%8F-troubleshooting-tips)
7. [🚀 Additional Tasks (Optional)](#-additional-tasks-optional)
8. [📚 References](#-references)

---

## 🎯 Objective
The goal of this lab is to **set up and deploy an Angular-based web application (Angular Calculator)** on a local Ubuntu server using **Nginx**.  
By the end, you’ll know how to:
- Clone a GitHub repository
- Install dependencies
- Build the Angular project for production
- Deploy it with Nginx
- Access it via browser

---

## 🧰 Materials Needed
- 🖥️ Ubuntu system (or any Linux-based OS)  
- 🟢 Node.js and npm  
- 🔺 Angular CLI  
- 🧬 Git  
- 🌐 Nginx  

---

## 📘 Prerequisites
- Basic understanding of **Angular** and **web development concepts**  
- Familiarity with **Linux terminal commands**  
- Basic knowledge of **npm** and **Node.js**

---

## 🧪 Procedure

### 1️⃣ Setting up the Environment

#### 🧾 Step 1.1: Check and set hostname
```bash
hostnamectl
sudo hostnamectl set-hostname angular-app
````

#### 🔄 Step 1.2: Update system packages

```bash
sudo apt -y update
```

---

### 2️⃣ Clone the Angular Repository

#### 📂 Step 2.1: Clone the project

```bash
git clone https://github.com/Ai-TechNov/AngularCalculator.git
```

#### 📁 Step 2.2: Navigate into the directory

```bash
cd AngularCalculator
```

---

### 3️⃣ Install Dependencies

#### 🧩 Step 3.1: Verify Node.js and npm

```bash
node -v
npm -v
```

If not installed or outdated, install them:

#### ⚙️ Step 3.2: Install Node.js and npm

```bash
sudo apt-get install -y nodejs
sudo apt install npm -y
```

#### 📦 Step 3.3: Install project dependencies

```bash
npm install
```

---

### 4️⃣ Build the Angular Application

#### 🏗️ Step 4.1: Build for production

```bash
sudo ng build --prod
```

✅ Output will be generated in the `dist/` folder.

---

### 5️⃣ Install and Configure Nginx

#### 🌐 Step 5.1: Install Nginx

```bash
sudo apt -y install nginx
```

#### 🔍 Step 5.2: Check Nginx status

```bash
sudo systemctl status nginx
```

#### 🧹 Step 5.3: Remove default web files

```bash
sudo rm -rf /var/www/html/*
```

#### 📁 Step 5.4: Copy built files to Nginx root

```bash
sudo cp -r dist/angularCalc/* /var/www/html/
```

#### 🔁 Step 5.5: Restart Nginx

```bash
sudo systemctl restart nginx
```

---

### 6️⃣ Test the Application

#### 🧠 Step 6.1: Access in Browser

Open your browser and visit:

```
http://<your-server-ip>
```

Or if local:

```
http://localhost
```

🎉 You should now see your **Angular Calculator App** running successfully!

---

## 🏁 Conclusion

After completing this lab, you have learned to:
✅ Clone an Angular project from GitHub
✅ Install dependencies using npm
✅ Build for production
✅ Serve with Nginx
✅ Access your app in a browser

This lab builds practical knowledge in **Angular deployment**, **Linux administration**, and **DevOps fundamentals**.

---

## ⚙️ Troubleshooting Tips

| Issue                 | Possible Cause                 | Solution                                                 |
| --------------------- | ------------------------------ | -------------------------------------------------------- |
| ❌ `ng build` fails    | Missing dependencies           | Run `npm install`                                        |
| 🚫 Nginx not starting | Misconfiguration               | Run `sudo nginx -t` and check `/var/log/nginx/error.log` |
| Blank page in browser | Wrong file permissions or path | Check `/var/www/html/` contents                          |

---

## 🚀 Additional Tasks (Optional)

### 💡 Enhance the Calculator

Try adding:

* Additional math operations (%, √, ±)
* Decimal and keyboard input
* History log of calculations

### 🧭 Version Control with Git

```bash
git add .
git commit -m "Enhanced calculator UI"
git push origin main
```

---

## 📚 References

* [📘 Angular Official Documentation](https://angular.io/docs)
* [🌐 Nginx Official Documentation](https://nginx.org/en/docs/)
* [🟢 Node.js Official Docs](https://nodejs.org/en/docs)

---

## 🧠 Author & Purpose

**Author:** Ai-TechNov
**Purpose:** Educational lab for teaching **Angular deployment** and **Nginx configuration** on **Ubuntu Linux**.
**Category:** 🧩 Cloud • DevOps • Web Deployment

---

```

---

Would you like me to:
1. 🖼️ Add a **diagram or architecture image** (showing how Nginx serves Angular’s dist folder)?  
2. 📄 Generate this as a **stylish PDF lab guide** (for training distribution)?
```
