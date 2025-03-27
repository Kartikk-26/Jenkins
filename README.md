# 🔄 CI/CD Pipeline Setup using Jenkins on AWS EC2

This project demonstrates how to set up a complete CI/CD pipeline using **Jenkins** hosted on an **AWS EC2** instance. 
The project integrates Jenkins to automate build and deployment workflows, providing a seamless and efficient CI/CD pipeline.

---

## 🎯 **Project Overview**

This project covers:

✅ Jenkins Installation on AWS EC2 (Amazon Linux/Red Hat)  
✅ Creating and Configuring a Jenkins Job  
✅ Building and Deploying a Test Project  
✅ Verifying Workspace Files and Git Integration  

---

## 📝 **Prerequisites**

1. AWS EC2 instance with security groups configured to allow:
   - Port **8080** for Jenkins
   - Port **22** for SSH
2. Basic knowledge of Linux and Jenkins.
3. Public IP of EC2 instance for Jenkins dashboard access.

---

## 🛠️ **Jenkins Installation and Setup**

### 1. Connect to Your EC2 Instance
```bash
ssh -i your-key.pem ec2-user@your-public-ip
```

### 2. Install Java
```bash
sudo yum update -y
sudo yum install java-17-openjdk -y
```

### 3. Add Jenkins Repository
```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

### 4. Install Jenkins
```bash
sudo yum upgrade
sudo yum install jenkins -y
```

### 5. Start and Enable Jenkins
```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
```

### 6. Check Jenkins Status
```bash
sudo systemctl status jenkins
```

---

## 🌐 **Access Jenkins Dashboard**

1. Get your Jenkins initial admin password:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
2. Visit your Jenkins dashboard:
```
http://<your-public-ip>:8080
```

3. Paste the password to unlock Jenkins.

---

## 🧩 **Creating and Configuring a Test Project**

1. Go to **Jenkins Dashboard** ➡️ Click **New Item**.
2. Select **Freestyle Project** and name it `Test-Project`.
3. Configure build steps and save.

---

## 📂 **Validating Workspace Files**

Navigate to the Jenkins workspace:
```bash
cd /var/lib/jenkins/workspace/Test-Project/
ls
```

Files should be visible after successful builds.

---

## 🧪 **Testing and Verifying Git Integration**

1. Set up a Git project:
```bash
cd /var/lib/jenkins/workspace/Git
ls
cat index.html
```

You should see the expected output.

---

## 🎉 **Conclusion**

You have successfully:
- Installed Jenkins on AWS EC2.
- Configured a CI/CD pipeline.
- Validated file deployments and Git integration.

---

## 🤝 **Connect with Me**  
- Stay updated on [LinkedIn](https://www.linkedin.com/in/-kartikjain/) to see more projects and continuous improvements as I advance on this exciting journey. 
- Follow along to track my daily progress and solutions as I tackle challenging **DevOps Projects**, master new tools, and refine my skills.  
- Let’s collaborate and build impactful **DevOps solutions** together!   

--- 
