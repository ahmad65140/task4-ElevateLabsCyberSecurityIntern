# task4-ElevateLabsCyberSecurityIntern
---
# Firewall Configuration with UFW (Kali Linux)

## Task Overview

This task demonstrates the use of **UFW (Uncomplicated Firewall)** on Kali Linux to configure firewall rules, test them, and document the process. UFW is a simple frontend for `iptables` that makes managing firewall rules more user-friendly.

---

## Steps Performed

### 1. Open Firewall Configuration Tool

Ensure UFW is installed and enabled:

```bash
sudo apt update && sudo apt install ufw -y
sudo ufw status
sudo ufw enable
```

### 2. List Current Firewall Rules

```bash
sudo ufw status numbered
```

This shows active rules with rule numbers.

### 3. Block Inbound Traffic on Port 23 (Telnet)

```bash
sudo ufw deny 23/tcp
```

This blocks any TCP traffic on port 23, preventing Telnet connections.

### 4. Test the Rule

Use **netcat** to test the connection:

```bash
nc -v 127.0.0.1 23
```

Expected result: *connection refused* or timeout, showing the port is blocked.

### 5. Allow SSH (Port 22)

```bash
sudo ufw allow 22/tcp
```

This ensures SSH access remains available.

### 6. Remove the Test Block Rule

List rules and delete by number:

```bash
sudo ufw status numbered
sudo ufw delete <rule-number>
```

### 7. Document Commands

Commands used:

```text
1. sudo ufw status
2. sudo ufw deny 23/tcp
3. nc -v 127.0.0.1 23
4. sudo ufw allow 22/tcp
5. sudo ufw status numbered
6. sudo ufw delete <rule-number>
```

### 8. Summary of Firewall Filtering

A firewall filters **incoming and outgoing network traffic** based on predefined rules:

* **Allow rules** permit traffic (e.g., SSH on port 22).
* **Deny rules** block unwanted or insecure traffic (e.g., Telnet on port 23).
* This prevents unauthorized access and reduces the system’s attack surface.

---



Do you want me to export this into an actual **README.md file** you can download, or just keep it as text for you to copy?
