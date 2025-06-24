# 🛡️ Zero Trust Network Lab (ZTNA Simulation)

This project simulates a Zero Trust environment using pfSense and virtual machines. It demonstrates how to enforce least privilege access, block untrusted users, and secure internal services using firewall rules.


## 🔧 Lab Overview

| Component           | Description                                   |
|---------------------|-----------------------------------------------|
|   pfSense           | Acts as internal firewall (192.168.1.1)       |
|   Ubuntu (Admin)    | Trusted user with full access (192.168.1.10)  |
|   Kali (Employee)   | Untrusted user, limited access (192.168.1.20) |


## 🧪 Zero Trust Principles Demonstrated

- Least Privilege Access  : Only the admin can access sensitive ports (e.g., SSH).
- Microsegmentation       : Internal firewall zones control traffic between roles.
- Role Enforcement        : Employee cannot access privileged ports or services.
- Threat Simulation       : The attacker (employee) runs nmap scans and SSH probes.


## 🖥️ Network Diagram

![ZTNA Network Diagram](https://github.com/JenishPatel08/ztna-simulation-lab/blob/2d8b4f74ca4ca3313b11a21fa891442aa4df7f14/ZeroTrust-Network-Lab/Network-diagram.png)


## 🔒 RBAC Summary

- Admin is allowed to SSH into pfSense.
- Employee is blocked from SSH and other sensitive access.
- ICMP (ping) is allowed for both to test connectivity.


## 📈 Key Results

| Test                    | Admin (Ubuntu)    | Employee (Kali)     |
|-------------------------|-------------------|---------------------|
| SSH to pfSense          | ✅ Allowed       | ❌ Blocked          |
| Ping to pfSense         | ✅ Allowed       | ✅ Allowed          |
| Nmap Port Scan (before) | ✅ Ports visible | ✅ Ports visible    |
| Nmap Port Scan (after)  | ✅ SSH visible   | ❌ Ports filtered   |


## 🚀 How to Reproduce This Lab

1. Set up 3 VMs: pfSense, Ubuntu, Kali
2. Assign static IPs on the same subnet
3. Configure pfSense LAN interface as `192.168.1.1`
4. Allow only admin IP to access SSH (port 22)
5. Block all other SSH attempts using firewall rules
6. Test with `ssh`, `ping`, and `nmap`


## 📸 Screenshots

- Included: Firewall rule screenshots, SSH attempts, IP configuration, and `nmap` results
- Screenshots show access being enforced based on identity (IP)


## 🧠 What You Learn

- How Zero Trust architecture works in practice
- How to build secure micro-networks using pfSense
- How to simulate internal and external threats using free tools
