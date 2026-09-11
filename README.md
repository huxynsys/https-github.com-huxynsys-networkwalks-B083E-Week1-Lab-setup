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
| Host OS         | Windows 10         |
| Host RAM        | 8 GB               |
| Processor       | Intel Core i5      |
| Hypervisor      | VMware Workstation |
| Security OS     | Kali Linux         |
| Kali RAM        | 2048 MB            |
| Virtual Network | VMnet8 (NAT)       |
| Network Type    | NAT                |
| Network Address | `10.0.0.0/24`  |
| Kali IP Address | `10.0.0.2/24`  |
| Default Gateway | `10.0.0.1`     |
| DNS Server      | `8.8.8.8`      |

---

# 🛠️ Lab Setup Procedure

## Step 1 — Install 7-Zip

7-Zip was installed on the Windows host system.

It was used to extract the downloaded Kali Linux virtual machine files.


---

## Step 2 — Install VMware Workstation

VMware Workstation was installed on the Windows host system to create and manage the virtual cybersecurity lab.

After installation, VMware Workstation was launched successfully.


---

## Step 3 — Configure VMware Network

VMware's virtual networking was configured using **VMnet8**, which provides NAT connectivity for the Kali Linux virtual machine.

The Kali VM was connected to **VMnet8 (NAT)**.

### Network Configuration

```text
Network Adapter: VMnet8
Network Type: NAT
Gateway: 10.0.0.1
```

### Screenshot

<img width="609" height="536" alt="screenshot 3" src="https://github.com/user-attachments/assets/8af50745-025a-4569-98fa-32067d0f8c00" />

<img width="491" height="528" alt="screenshot 2" src="https://github.com/user-attachments/assets/6ed21986-c13e-42b3-a01b-671042871232" />



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

<img width="741" height="718" alt="screenshot3" src="https://github.com/user-attachments/assets/b5b572f2-6d1f-4d48-9d01-f6da49392b53" />


<img width="1161" height="646" alt="screenshot4" src="https://github.com/user-attachments/assets/7f8b1093-751f-4573-bb33-bef5c3b6cfba" />


<img width="1366" height="731" alt="screenshot5" src="https://github.com/user-attachments/assets/760ccd49-5231-42f1-917b-2db3bf001ab8" />


---

## Step 5 — Configure Kali Linux Network

The network configuration inside Kali Linux was checked and configured.

The following network information was used:

```text
IP Address: 10.0.0.2/24
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

The configuration was verified using:

```bash
ip a
```


### Screenshot

<img width="879" height="543" alt="screenshot 7" src="https://github.com/user-attachments/assets/f232ad1e-232c-488e-b813-fd890c348522" />




---

# 🔎 Lab Verification

After configuring the lab, several tests were performed to verify that the network was working correctly.

### 1. Check IP Address

```bash
ip a
```

The Kali machine showed the expected IP address on the network interface.

---
<img width="879" height="435" alt="image" src="https://github.com/user-attachments/assets/4ea23cad-20fc-4c94-b059-15891c69f8b2" />

<img width="841" height="150" alt="image" src="https://github.com/user-attachments/assets/d29514d9-2267-400e-b81a-a8879cfbe8e5" />


### 2. Check Default Gateway

```bash
ping 10.0.0.1
```

The gateway responded successfully.

---

### 3. Check Internet Connectivity

```bash
ping 8.8.8.8
```

The test confirmed that Kali Linux could reach the internet through the VMware NAT network.

---
<img width="530" height="254" alt="image" src="https://github.com/user-attachments/assets/985c94ad-80e9-4722-a6f3-aa2d2f5f131b" />


### 4. Check DNS Resolution

```bash
nslookup networkwalks.com
```

DNS resolution was tested successfully.

---
<img width="449" height="128" alt="image" src="https://github.com/user-attachments/assets/859b6b22-8a20-4c7c-bfab-14e3fa6a8154" />


### 5. Check Nmap Installation

```bash
nmap --version
```

The installed Nmap version was displayed successfully.

---
<img width="993" height="134" alt="image" src="https://github.com/user-attachments/assets/c08c520c-ff1b-4784-ba7c-f8db138551b9" />




# 💾 Step 6 — Create Clean VM Snapshot

After completing the configuration and verification, a clean snapshot of the Kali Linux virtual machine was created.

The snapshot provides a restore point that can be used to return the VM to its clean initial state before future cybersecurity exercises.

### Screenshot

<img width="1366" height="731" alt="image" src="https://github.com/user-attachments/assets/6e76c9bc-6304-42e7-888b-dea25d97c85f" />

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
