v-server-setup

## Project Structure
```
v-server-setup
├── Checkliste.pdf
└── README.md
```
---

## Technologies Used

* OpenSSH (key-based authentication only)
* NGINX Web Server
* Git + GitHub

---

## Prerequisites

* Linux Server
* GitHub account

---

## Server Setup Overview

### 1. SSH Access Configuration

* Created a new SSH key pair

```bash
ssh-keygen -t ed25519 -C "<username>@<ip_address>"
```

* Uploaded public key to the server

```bash
ssh-copy-id <username>@<ip_address>
```

* Disabled password login and PAM

```bash
sudo nano /etc/ssh/sshd_config
```

* Change the folowing items in sshd_config file
```
├── PasswordAuthentication no


```
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

* Edit the default `index.html` file and overwrite it with your own title and content to replace the default Nginx welcome page.
* Test the website in browser
http://<ip_address>


### 4. Git + GitHub Integration

* Installed and verified Git

```bash
sudo apt install git
```

* Configure git by username and email_address

```bash
git config --global user.name "<your_username>"
git config --global user.email "<your_email@example.com>"
```
* Clone the project repository using SSH:

Go to your GitHub repository, click the green Code button, and select the SSH tab. Copy the SSH URL, then run:

```bash
git clone <your-ssh-url-here>
```

* Project version-controlled and documented.

## How to Use

* Clone the project to your local machine:
```bash
git clone <your-ssh-url-here>
cd v-server-setup
```
* The project is now version-controlled and connected to GitHub.
---
