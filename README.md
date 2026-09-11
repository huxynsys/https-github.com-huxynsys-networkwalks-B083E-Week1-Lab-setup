# https-github.com-huxynsys-networkwalks-B083E-Week1-Lab-setup
<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab environment for penetration testing and ethical hacking practice using VMware and Kali Linux**

</div>

---

## 📌 Project Overview

This project is part of **Week 1 of the NetworkWalks Ethical Hacking & Cybersecurity Internship**.

The objective of this week was to build a safe and isolated cybersecurity lab environment using **VMware Workstation** and **Kali Linux**.

This lab provides a controlled environment for practicing cybersecurity, networking, penetration testing, and ethical hacking techniques without affecting the host system or external networks.

---

## 🎯 Week 1 Objectives

* Install 7-Zip
* Install VMware Workstation
* Configure VMware NAT networking
* Configure **VMnet8**
* Import and configure Kali Linux
* Configure Kali Linux network settings
* Verify network connectivity
* Create a clean VM snapshot
* Document the complete setup with screenshots

---

## 🖥️ Lab Configuration

| Component       | Configuration      |
| --------------- | ------------------ |
| Host OS         | Windows 11         |
| Host RAM        | 8 GB               |
| Processor       | Intel Core i3      |
| Hypervisor      | VMware Workstation |
| Security OS     | Kali Linux         |
| Kali RAM        | 2048 MB            |
| Virtual Network | VMnet8 (NAT)       |
| Network Type    | NAT                |
| Network Address | `YOUR_NETWORK/24`  |
| Kali IP Address | `YOUR_KALI_IP/24`  |
| Default Gateway | `YOUR_GATEWAY`     |
| DNS Server      | `YOUR_DNS`         |

> **Note:** Replace the network values above with the actual values from your VMware/Kali configuration.

---

# 🛠️ Lab Setup Procedure

## Step 1 — Install 7-Zip

7-Zip was installed on the Windows host system.

It was used to extract the downloaded Kali Linux virtual machine files.

### Screenshot

📸 **Screenshot 1:** 7-Zip installation / extracted Kali Linux files

---

## Step 2 — Install VMware Workstation

VMware Workstation was installed on the Windows host system to create and manage the virtual cybersecurity lab.

After installation, VMware Workstation was launched successfully.

### Screenshot

📸 **Screenshot 2:** VMware Workstation installed and opened

---

## Step 3 — Configure VMware Network

VMware's virtual networking was configured using **VMnet8**, which provides NAT connectivity for the Kali Linux virtual machine.

The Kali VM was connected to **VMnet8 (NAT)**.

### Network Configuration

```text
Network Adapter: VMnet8
Network Type: NAT
Subnet: YOUR_NETWORK/24
Gateway: YOUR_GATEWAY
```

### Screenshot

📸 **Screenshot 3:** VMware Virtual Network Editor showing VMnet8 configuration

---

## Step 4 — Import and Configure Kali Linux

The Kali Linux virtual machine was imported into VMware Workstation.

The VM hardware configuration was checked before starting the machine.

### VM Configuration

```text
Operating System: Kali Linux
RAM: 2048 MB
Network Adapter: VMnet8
Network Mode: NAT
```

The network adapter was configured to use **VMnet8**.

### Screenshots

📸 **Screenshot 4:** Kali VM hardware configuration

📸 **Screenshot 5:** Kali VM network adapter configured to VMnet8

📸 **Screenshot 6:** Kali Linux successfully started

---

## Step 5 — Configure Kali Linux Network

The network configuration inside Kali Linux was checked and configured.

The following network information was used:

```text
IP Address: YOUR_KALI_IP/24
Gateway: YOUR_GATEWAY
DNS: YOUR_DNS
```

The configuration was verified using:

```bash
ip a
```

The default gateway was checked using:

```bash
ip route
```

### Screenshot

📸 **Screenshot 7:** Kali Linux `ip a` output showing the configured IP address

📸 **Screenshot 8:** Kali Linux routing configuration

---

# 🔎 Lab Verification

After configuring the lab, several tests were performed to verify that the network was working correctly.

### 1. Check IP Address

```bash
ip a
```

The Kali machine showed the expected IP address on the network interface.

---

### 2. Check Default Gateway

```bash
ping YOUR_GATEWAY
```

The gateway responded successfully.

---

### 3. Check Internet Connectivity

```bash
ping 8.8.8.8
```

The test confirmed that Kali Linux could reach the internet through the VMware NAT network.

---

### 4. Check DNS Resolution

```bash
nslookup networkwalks.com
```

DNS resolution was tested successfully.

---

### 5. Check Nmap Installation

```bash
nmap --version
```

The installed Nmap version was displayed successfully.

---

### Verification Screenshots

📸 **Screenshot 9:** Gateway ping

📸 **Screenshot 10:** Internet connectivity test

📸 **Screenshot 11:** DNS resolution test

📸 **Screenshot 12:** Nmap version

---

# 💾 Step 6 — Create Clean VM Snapshot

After completing the configuration and verification, a clean snapshot of the Kali Linux virtual machine was created.

The snapshot provides a restore point that can be used to return the VM to its clean initial state before future cybersecurity exercises.

### Screenshot

📸 **Screenshot 13:** VMware snapshot showing the clean Kali Linux state

---

# ⚠️ Problems Encountered & Solutions

During the lab setup, network connectivity was checked after configuring the Kali Linux virtual machine.

If the network interface does not immediately obtain connectivity, the interface can be restarted and checked again.

Example:

```bash
sudo ifconfig eth0 down
sudo ifconfig eth0 up
```

The network configuration can then be verified again:

```bash
ip a
```

Connectivity can be tested using:

```bash
ping 8.8.8.8
```

---

# 📚 What I Learned

During this lab, I learned:

* How to create a virtual cybersecurity lab using VMware
* How VMware NAT networking works
* How to configure and use VMnet8
* How to configure networking inside Kali Linux
* How to verify IP and gateway configuration
* How to troubleshoot basic network connectivity
* How to create and use VMware VM snapshots
* How to document a cybersecurity lab environment

---

# ✅ Week 1 Status

| Task                  | Status      |
| --------------------- | ----------- |
| 7-Zip Installation    | ✅ Completed |
| VMware Installation   | ✅ Completed |
| VMnet8 Configuration  | ✅ Completed |
| Kali Linux Setup      | ✅ Completed |
| Network Configuration | ✅ Completed |
| Network Testing       | ✅ Completed |
| Nmap Verification     | ✅ Completed |
| Clean Snapshot        | ✅ Completed |
| Documentation         | ✅ Completed |

---

## 🏁 Conclusion

The Week 1 cybersecurity lab environment was successfully configured using **VMware Workstation, VMnet8 NAT networking, and Kali Linux**.

The network connectivity was verified and a clean snapshot was created. The environment is now ready for upcoming cybersecurity and ethical hacking practical exercises.

---

<div align="center">

**🔐 Cybersecurity Lab — Week 1**

**VMware + Kali Linux + VMnet8**

</div>
