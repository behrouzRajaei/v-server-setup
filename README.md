# v-server-setup

## Project Structur

v-server-setup
        ├── Checkliste.pdf
        └── README.md

---

## Technologies Used

* OpenSSH (key-based authentication only)
* NGINX Web Server
* Git + GitHub

---

## Server Setup Overview

### 1. SSH Access Configuration

* Created a new SSH key pair

```bash
        ssh-keygen -t ed25519 -C "brajaei@188.245.220.182"
```

* Uploaded public key to the server

```bash
        ssh-copy-id brajaei@188.245.220.182
```

* Disabled password login and PAM

```bash
        sudo nano /etc/ssh/sshd_config
```

* Change the folowing items in sshd_config file
        ├── PasswordAuthentication no
        ├── UsePAM no
        └── PermitRootlogin no

* Restart service SSH

```bash
        sudo sshd -t
        sudo systemctl restart ssh
```

### 2. NGINX Web Server

* Installed and verified NGINX is up and running

```bash
        sudo apt update
        sudo apt install nginx -y
        sudo systemctl start nginx
        sudo systemctl enable nginx
```

* Create alternative for NGINX seite

```bash
        cd /var/www/html
        sudo nano index.html
```

* Write the new Title and Content for new webseite
* Test the website in browser
        http://188.245.220.182


### 4. Git + GitHub Integration

* Installed and verified Git

```bash
        sudo apt install git
```

* Configure git by User_name and Email Address

```bash
        git config --global user.name "Behrouz Rajaei"
        git config --global user.email "bmd.rajaei@gmail.com"
```

* Stage changes and commit them to the development branch

```bash
        git add .
        git commit -m "Projekt_data in devel;pment added"
```

* Push branch to GitHub

```bash
        git push --set-upstream origin development
```

* Project version-controlled and documented.

---

## Prerequisites

* Linux Server
* GitHub account

---

## How to Use

* Git initialized and connected to [GitHub repo](https://github.com/behrouzRajaei/v-server-setup) and Clone the project to your local machine:

```bash
        git clone git@github.com:behrouzRajaei/v-server-setup.git
        cd v-server-setup
```

---