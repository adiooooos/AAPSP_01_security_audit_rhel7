# Security Audit for RHEL 7 🚀

#### Unleash the Power of Automated Security Auditing!


Welcome to the **RHEL 7 Security Audit Automation** tool! This Ansible Playbook is your ultimate sidekick for effortlessly auditing RHEL 7 servers, ensuring they align with Linux security best practices and industry compliance standards like **CIS** and **NIST**. Say goodbye to manual checks and hello to streamlined, secure automation! 💻🔒

#### See It in Action
Check out the stunning results below:  


---

## 🌟 Key Features

- ✅ **Core System Insights**: Collects critical details like IP and Hostname with ease.  
- 🔐 **11 Essential Security Checks**:  
  - 🔍 SSH Root Login Restrictions  
  - 🔑 Password Complexity Policy Validation  
  - 📜 System Log Service Monitoring  
  - 🛡️ Firewall Status Verification  
  - 📂 Critical File Permission Audits  
  - 🔧 SELinux Enforcing Mode Check  
  - 🔐 SSH Public Key Authentication Validation  
- 📧 **Automated Reporting**: Generates sleek HTML reports and sends them via email.  
- ⚙️ **Flexible Email Integration**: Supports Gmail SMTP and extensible to other providers.  

---

## 🚀 Get Started in Minutes

### 📋 Prerequisites
- **Ansible Automation Platform** 2.5 or higher  
- **RHEL 7 Target Hosts** with configured SSH access  
- **SMTP Email Account** (Gmail recommended)  
- **Community Collection**: Install with `ansible-galaxy collection install community.general`

### 🛠️ Quick Setup
```bash
# 1. Clone the Repository
git clone https://github.com/your_repo/rhel7-security-audit.git
cd rhel7-security-audit

# 2. Configure Inventory
echo "[rhel7]" > inventory.ini
echo "your_hostname ansible_host=192.168.1.100" >> inventory.ini

# 3. Run the Audit
ansible-playbook -i inventory.ini security_audit.yml
```

---

## 🔍 Playbook Task Breakdown

| Task ID | Audit Item                     | Compliance Reference       | Key Parameter            |
|---------|--------------------------------|----------------------------|--------------------------|
| task-03 | SSH Root Login Restriction     | CIS Benchmark 5.3          | `PermitRootLogin`        |
| task-04 | Password Length & Complexity   | NIST SP 800-63B            | `minlen=14`              |
| task-07 | /etc/passwd File Permissions   | CIS 6.1.2                  | `Mode 644`               |
| task-08 | SELinux Enforcing Mode         | PCI DSS Req.2.2.2          | `Enforcing Mode`         |
| task-09 | SSH Public Key Authentication  | NSA SSH Guidelines         | `PubkeyAuthentication`   |

---

## ⚙️ Customize Like a Pro

Tailor the audit to your needs by editing the `vars` block in `security_audit.yml`:

```yaml
vars:
  mail_host: "smtp.yourcompany.com"  # SMTP Server Address
  mail_port: "587"                   # STARTTLS Port
  sender_username: "audit@company.com"
  mail_to:                           # Recipient List
    - "admin@company.com"
    - "security-team@company.com"
```

🔐 **Secure Your Passwords**: Use Ansible Vault for encryption:  
```bash
ansible-vault encrypt_string 'your_password' --name 'sender_password'
```

---

## ⚠️ Usage Tips for Success

1. **SSH Key Authentication**: Ensure it’s configured on target hosts.  
2. **Template File**: Verify `audit_report.html.j2` exists.  
3. **Email Ports**: Open ports 25, 465, or 587 on target hosts.  
4. **SELinux Impact**: Be aware it may affect audit results.  
5. **Timing**: Run audits during low-traffic periods for best performance.  

---

## 🌈 Why Choose This Tool?

This Ansible Playbook is your ticket to **secure, compliant, and hassle-free** RHEL 7 server auditing. With its sleek reports, robust checks, and seamless email integration, it’s designed to make your security tasks feel like a breeze. Ready to elevate your server security game? Dive in now! 🎉
