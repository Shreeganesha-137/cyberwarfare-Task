# Task 1: Server Setup and SSH Configuration

## 📌 Objective
Secure remote access to a Linux server using SSH with key-based authentication.

## Prerequisites
- SSH client (OpenSSH, PuTTY, or MobaXterm)
- Linux server with sudo access

## Steps

### 1. Start SSH Service

```bash
sudo systemctl start ssh
sudo systemctl enable ssh
```

### 2. Configure SSH
Edit the SSH configuration file:

```bash
sudo nano /etc/ssh/sshd_config
```