# Task 1 - Network Port Scanning

## Objective
Learn to discover open ports on devices in a local network to understand network exposure.

## Tools Used
- Nmap 7.94SVN
- Ubuntu Linux

## Command Used
```bash
sudo nmap -sS -sV 10.14.218.0/24 -oN task1_result.txt
```

## Command Explained
| Flag | Meaning |
|---|---|
| sudo | Run as root |
| nmap | Network mapper tool |
| -sS | TCP SYN stealth scan |
| -sV | Detect service versions |
| 10.14.218.0/24 | Scan all 256 IPs in network |
| -oN | Save output to file |

## Scan Results

### Device 1 - Gateway
- IP: 10.14.218.74
- Port: 53/tcp open
- Service: domain (dnsmasq 2.51)
- MAC: BE:2E:D0:DC:A5:A5

### Device 2 - My Laptop
- IP: 10.14.218.12
- No open ports found

## Security Risk
- dnsmasq 2.51 is outdated
- Vulnerable to DNS poisoning
- Fix: Update Android to latest version

## Outcome
- Learned basic network reconnaissance
- Identified open ports on local network
- Understood network service exposure
