# Task 4 — Firewall Configuration using UFW

## Objective
Configure and test basic firewall rules on Ubuntu Linux using UFW 
to allow or block network traffic on specific ports.

## Tool Used
- **UFW** (Uncomplicated Firewall) — built into Ubuntu

## Steps Performed

### 1. Check firewall status
```bash
sudo ufw status
```

### 2. Block port 23 (Telnet)
```bash
sudo ufw deny 23
```

### 3. Test the rule
```bash
nc -zv 10.14.218.12 23
```
Result: Connection refused ✅

### 4. Allow port 22 (SSH)
```bash
sudo ufw allow 22
```

### 5. Remove test rules
```bash
sudo ufw delete allow 22
sudo ufw delete deny 23
```

### 6. Verify final state
```bash
sudo ufw status
```

## Final Firewall Rules
| Port | Action |
|---|---|
| 631 | DENY |

## Key Learnings
- UFW applies rules to both IPv4 and IPv6 automatically
- Deleting a rule removes it completely
- Always test rules using nc (Netcat) after adding them

## Deliverables
- firewall-report.pdf
- screenshots/
