# v-server-setup

## Project Structure

v-server-setup/
CHECKLIST.md       README.md          config/

---

## Technologies Used

* OpenSSH (key-based authentication only)
* NGINX Web Server
* UFW 
* Git + GitHub

---

## Server Setup Overview

### 1. SSH Access Configuration

* Created a new SSH key pair.
* Uploaded public key to the server.
* Disabled password login and PAM.

### 2. Firewall (UFW)

* Enabled firewall and allowed only essential services (SSH + NGINX).

### 3. NGINX Web Server

* Installed and verified NGINX is up and running.
* Server is reachable via browser on http://188.245.220.182.

### 4. GitHub Integration

* Git initialized and connected to [GitHub repo](https://github.com/behrouzRajaei/v-server-setup).
* Project version-controlled and documented.

---

## Prerequisites

* A Linux
* Git and SSH installed locally
* GitHub account

---

## How to Use

Clone the project to your local machine:

```bash
        git clone git@github.com:behrouzRajaei/v-server-setup.git
        cd v-server-setup
```

Follow the instructions in [CHECKLIST.md](./CHECKLIST.md) to configure your server securely and step-by-step.

---
