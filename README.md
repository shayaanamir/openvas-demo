# OpenVAS Vulnerability Assessment Demonstration

## Overview

This repository demonstrates the setup and usage of **OpenVAS (Open Vulnerability Assessment System)** to perform vulnerability scanning on intentionally vulnerable systems. The project includes installation of OpenVAS, configuration of scan targets, and vulnerability assessment using **Metasploitable** as the primary test environment.

The objective is to demonstrate how vulnerability scanners identify security weaknesses and generate reports with severity ratings and remediation steps.

---

##  Objectives

* Understand vulnerability assessment concepts
* Install and configure OpenVAS
* Setup intentionally vulnerable target (Metasploitable)
* Perform vulnerability scanning
* Analyze vulnerabilities using CVSS severity levels
* Generate and interpret scan reports

---

##  Tools Used

* OpenVAS (Greenbone Vulnerability Management)
* Oracle VirtualBox
* Metasploitable 2
* Windows Host System
* Web Browser

---


##  OpenVAS Installation & Setup

### Step 1: Import OpenVAS VM

1. Download OpenVAS Community Edition (.ova)
2. Import into VirtualBox
3. Start the VM
4. Note the Web UI IP address

### Step 2: Access Web Interface

Open browser and navigate to:

```
http://<openvas-ip>
```

Login using administrator credentials.

### Step 3: Configure Network

Set VM network to:

```
Bridged Adapter
```

---

# Metasploitable Setup

## Step 1: Download Metasploitable

Download Metasploitable 2:
[https://sourceforge.net/projects/metasploitable/files/Metasploitable2/](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/)

Extract the zip file.

---

## Step 2: Create Virtual Machine

1. Open VirtualBox
2. Click **New**
3. Name: `Metasploitable`
4. Type: Linux
5. Version: Ubuntu (32-bit)
6. RAM: 1024 MB
7. Use existing disk → Select `.vmdk` file

---

## Step 3: Configure Network

Set network adapter to:

```
Bridged Adapter
```

This allows OpenVAS to scan Metasploitable.

---

## Step 4: Start Metasploitable

Start the VM and login:

```
username: msfadmin
password: msfadmin
```

---

## Step 5: Find Metasploitable IP

Run command:

```
ifconfig
```

Example output:

```
192.168.29.50
```

This is the IP address to scan.

---

## Scanning Workflow

1. Login to OpenVAS
2. Go to **Tasks → Task Wizard**
3. Enter Metasploitable IP
4. Start Scan
5. Monitor progress

---

## Expected Results

OpenVAS detects:

* Open ports
* Vulnerable services
* Outdated software
* Misconfigurations
* Weak authentication
* Known CVEs

---

## Screenshots
Dashboard
<img width="1918" height="923" alt="image" src="https://github.com/user-attachments/assets/a735feb4-fdde-470f-ac74-4fd19e30080d" />

Task Wizard
<img width="1919" height="920" alt="image" src="https://github.com/user-attachments/assets/236e6369-8d7a-4fdf-88be-3e6c7bc62c48" />

Results
<img width="1919" height="926" alt="image" src="https://github.com/user-attachments/assets/51c57704-f0de-401e-9f72-108e04cba183" />

Reports
<img width="1919" height="921" alt="image" src="https://github.com/user-attachments/assets/5e866433-977d-4b94-b58f-8a715655aac0" />


---

## Report Includes

* Vulnerability Name
* CVE ID
* Severity Level
* CVSS Score
* Affected Port
* Description
* Solution

---


## Severity Levels

* Critical (9.0–10.0)
* High (7.0–8.9)
* Medium (4.0–6.9)
* Low (0.1–3.9)
* Informational

---


## Limitations

* Long scan time for full scans
* Possible false positives
* Requires proper network configuration

---

## References

* [https://www.openvas.org](https://www.openvas.org)
* [https://www.greenbone.net](https://www.greenbone.net)
* [https://sourceforge.net/projects/metasploitable/](https://sourceforge.net/projects/metasploitable/)
* [https://nvd.nist.gov](https://nvd.nist.gov)

---

