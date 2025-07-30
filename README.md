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

* Generate a new SSH key pair

```bash
ssh-keygen -t ed25519 -C "<username>@<ip_address>"
```

* Upload the public key to the server

```bash
ssh-copy-id <username>@<ip_address>
```

* Disable password-based login

```bash
sudo nano /etc/ssh/sshd_config
```

* Edit the folowing line in the sshd_config file

```
<<<<<<< HEAD
PasswordAuthentication no
=======
├── PasswordAuthentication no

>>>>>>> 10d7988a8f149532a7bbd7a5728ac91e1f15414a

```

* Test the configuration and restart the SSH service

```bash
sudo sshd -t
sudo systemctl restart ssh
```

### 2. NGINX Web Server

<<<<<<< HEAD
* Install and start NGINX
=======
* Installe and verifie NGINX is up and running

>>>>>>> 10d7988a8f149532a7bbd7a5728ac91e1f15414a

```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

* Create a custom landing page

```bash
cd /var/www/html
sudo nano index.html
```

* Edit the `index.html` file and replace the default content with your own title and content
* Test the website in a browser

```
http://<ip_address>
```

### 4. Git + GitHub Integration

* Install and verify Git

```bash
sudo apt install git
```

* Configure Git by username and email

```bash
git config --global user.name "<your_username>"
git config --global user.email "<your_email@example.com>"
```

* Adding your SSH key to GitHub
To authenticate with GitHub using SSH add the public key to your GitHub account.

The command in below:

```bash
cat ~/.ssh/id_ed25519.pub
```

Displays the content of your public SSH key. You need to copy the entire output and then:

```
├──Go to your GitHub account.
├──Go to Settings.
├──Go to SSH and GPG keys.
├──Choose New SSH key.
├──Choose a name for projekt in Title and paste the entire output content of your public key in Key's section.
└──Add SSH key.
```

* Clone the project repository using SSH

```
├──Go to your GitHub repository.
├──Click the green Code button.
├──Select the SSH tab.
└──Copy the SSH URL.
```

```bash
git clone <SSH URL>
```

* The project is now connected to GitHub and version controlled.
---
