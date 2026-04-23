# Task 4: User & Permissions

## Objective
Restrict access to monitoring logs using Linux user permissions.

### Create Dedicated User
```bash
sudo useradd monitoruser
sudo passwd monitoruser
```

### Assign Ownership
```bash
sudo chown -R monitoruser:monitoruser /opt/container-monitor
```

### Set Permissions
```bash
sudo chmod -R 700 /opt/container-monitor
```

## Verification

### Authorized User
```bash
su monitoruser
cd /opt/container-monitor/logs
```

### Unauthorized User
```bash
su otheruser
cd /opt/container-monitor
# Expected: Permission denied
```

## Outcome
- ✅ Only dedicated user can access logs
- ✅ Strong access control enforced