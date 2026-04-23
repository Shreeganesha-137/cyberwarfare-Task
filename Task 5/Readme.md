# Task 5: Firewall Configuration

## Objective
Configure firewall rules to allow only required traffic and block unauthorized access.

## Install UFW

```bash
sudo apt install ufw -y
```

## Default Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

## Allow SSH from Specific IP

```bash
sudo ufw allow from <your-ip> to any port 22
```

## Allow HTTP

```bash
sudo ufw allow 80
```

## Allow Port 8000

```bash
sudo ufw allow 8000
```

## Enable Firewall

```bash
sudo ufw enable
```

## Check Status

```bash
sudo ufw status
```

## Outcome

- ✅ Only allowed traffic can access server
- ✅ Unauthorized access is blocked