# DevSecOps Server Setup – Final Checklist

Project Name: v-server-setup
Repository URL: [https://github.com/behrouzRajaei/v-server-setup](https://github.com/behrouzRajaei/v-server-setup)
Server IP: 188.245.220.182
Access Method: SSH (key-based only)

---

## SSH Access Setup
- [x] Generated SSH key pair on local machine (ssh-keygen)
- [x] Copied public key to remote server (~/.ssh/authorized_keys)
- [x] Disabled password-based login in /etc/ssh/sshd_config:
          - PasswordAuthentication no
          - UsePAM no
- [x] Restarted SSH service (sudo systemctl restart ssh)

---

## Web Server (NGINX)
- [x] Installed NGINX: sudo apt install nginx
- [x] Verified NGINX is active: systemctl status nginx
- [x] Accessed server via web browser: http://188.245.220.182
- [x] Verified NGINX default page is visible

---

## Firewall (UFW)
- [x] UFW enabled: sudo ufw enable
- [x] Allowed OpenSSH and NGINX:
          - sudo ufw allow OpenSSH
          - sudo ufw allow 'Nginx Full'
- [x] Verified UFW status: sudo ufw status

---

## Git & GitHub Integration
- [x] Initialized git repo: git init
- [x] Added remote: git remote add origin git@github.com:behrouzRajaei/v-server-setup.git
- [x] Configured Git identity:
          - git config --global user.name "Behrouz Rajaei"
          - git config --global user.email "bmd.rajaei@gmail.com"
- [x] Pushed to GitHub:
          - git add .
          - git commit -m "Initial commit"
          - git push -u origin main

---

## Final Notes
- SSH access now only possible via key authentication.
- Password login completely disabled for better security.
- Web server is live and reachable through browser.
- All configuration steps tracked and versioned in GitHub.
