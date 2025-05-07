🔒 Security Audit for RHEL 7

Empower Your RHEL 7 Security with Automation 🚀

A powerful Ansible Playbook designed to automate security audits for RHEL 7 servers, aligning with Linux best practices and industry compliance standards (CIS/NIST). Secure, efficient, and hassle-free! ✨

🎉 What It Looks Like
![image](https://github.com/user-attachments/assets/0523d55f-d270-445e-bab3-f53b42a6932f)

🌟 Key Features
✅ System Insights: Collects core system info (IP, Hostname) effortlessly.

🔐 11 Critical Security Checks:

SSH Root login restrictions

Password complexity policy validation

System log service monitoring

Firewall status verification

Key file permission audits

SELinux enforcing mode validation

SSH public key authentication checks


📧 Automated Reporting: Generates sleek HTML reports and sends them via email.
⚙️ SMTP Integration: Supports Gmail and extensible to other email providers.


🚀 Quick Start Guide

Get your security audit up and running in minutes! 🕒

📋 Prerequisites





Ansible Automation Platform 2.5+



RHEL 7 target hosts with configured SSH access



SMTP email service account (Gmail recommended)



Install the community collection:

ansible-galaxy collection install community.general

🛠️ Installation Steps

# 1. Clone the repository
git clone https://github.com/your_repo/rhel7-security-audit.git
cd rhel7-security-audit

# 2. Configure the inventory file
echo "[rhel7]" > inventory.ini
echo "your_hostname ansible_host=192.168.1.100" >> inventory.ini

# 3. Run the security audit
ansible-playbook -i inventory.ini security_audit.yml



📖 Playbook Task Breakdown

A detailed look at the tasks powering your security audit:







Task ID



Check Item



Compliance Reference



Key Parameter





task-03



SSH Root Login Restriction



CIS Benchmark 5.3



PermitRootLogin





task-04



Password Complexity Policy



NIST SP 800-63B



minlen=14





task-07



/etc/passwd File Permissions



CIS 6.1.2



Mode 644





task-08



SELinux Enforcing Mode



PCI DSS Req.2.2.2



Enforcing Mode





task-09



SSH Public Key Authentication



NSA SSH Guidelines



PubkeyAuthentication



⚙️ Customize Your Audit

Tailor the audit to your needs by editing the vars block in security_audit.yml:

vars:
  mail_host: "smtp.yourcompany.com"  # SMTP server address
  mail_port: "587"                   # STARTTLS port
  sender_username: "audit@company.com"
  mail_to:                           # Recipient list
    - "admin@company.com"
    - "security-team@company.com"

🔐 Secure Passwords: Encrypt sensitive fields with Ansible Vault:

ansible-vault encrypt_string 'your_password' --name 'sender_password'



⚠️ Important Notes





SSH Key Authentication: Ensure target hosts are configured for SSH key-based access.



Template File: Verify the audit_report.html.j2 template exists.



Email Ports: Target hosts must allow outbound traffic on ports 25, 465, or 587.



SELinux Impact: SELinux settings may affect audit results.



Timing: Run audits during low-traffic periods to minimize impact.



💡 Pro Tip: Schedule regular audits to keep your RHEL 7 servers secure and compliant! Let this playbook do the heavy lifting while you focus on what matters. 💪
