Task 1: Server Setup and SSH Configuration

Objective

To configure secure remote access to a Linux server using SSH with key-based authentication.

I have completed all 5 tasks, Task 1 using a local WSL server for SSH. In AWS, SSH is easy to connect using PuTTY or MobaXterm, which I usually use. Today, my network is not good and my laptop storage is full, so I took a cloud server to complete the other 4 tasks.

Windows subsystem for linux And AWS EC2 Instance
```bash
ssh -i ~/shree/download/task.pem ubuntu@172.31.32.196

```
---

## Steps Performed

### 1. Installed SSH Server
```bash
sudo apt update
sudo apt install openssh-server -y
```

### 2. Started SSH Service
```bash
sudo systemctl start ssh
sudo systemctl enable ssh
```

### 3. Generated SSH Key (Client Machine)
```bash
ssh-keygen -t rsa -b 4096
```

Copy the rsa key into local server to authenticate the access

### 4. Copied Public Key to Server
```bash
ssh-copy-id ubuntu@172.31.32.196
```

### 5. Verified Passwordless Login
```bash
ssh ubuntu@172.31.32.196
```

### 6. Disabled Password Authentication
- Edited SSH config:
    ```bash
    sudo nano /etc/ssh/sshd_config
    ```
- Changed:
    ```
    PasswordAuthentication no
    ```
- Restarted SSH:
    ```bash
    sudo systemctl restart ssh
    ```

## ✅ Outcome
- Successfully connected to server without password
- Improved security using SSH key authentication