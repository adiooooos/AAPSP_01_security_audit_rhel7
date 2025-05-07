# 🚀 RHEL 7 Security Audit Automation

#### Elevate Your Server Security with Ansible! 🔒

![Ansible](https://img.shields.io/badge/Ansible-2.5+-red?logo=ansible&style=for-the-badge)
![RHEL](https://img.shields.io/badge/RHEL-7.x-orange?logo=red-hat&style=for-the-badge)

Welcome to the **RHEL 7 Security Audit Automation**! This powerful Ansible Playbook automates security audits for RHEL 7 servers, aligning with Linux best practices and industry compliance standards like **CIS** and **NIST**. Say goodbye to manual checks and hello to streamlined, secure operations! 🌟

#### See It in Action! 📸


---

## ✨ Key Features
- ✅ **System Info Collection**: Gathers critical details like IP and Hostname.
- 🔐 **11 Essential Security Checks**:
  - SSH Root login restrictions
  - Password complexity policy validation
  - System logging service status
  - Firewall operational status
  - Critical file permissions audit
  - SELinux enforcing mode verification
  - SSH public key authentication checks
- 📧 **Automated HTML Reports**: Generates detailed reports and emails them instantly.
- ⚙️ **Gmail SMTP Integration**: Easily extensible to other email providers.

---

## 🚀 Get Started in Minutes!

### 📋 Prerequisites
- **Ansible Automation Platform** 2.5 or higher
- RHEL 7 target hosts with configured SSH access
- An active SMTP email account (Gmail recommended)
- Community collection installed:  
  ```bash
  ansible-galaxy collection install community.general
  ```

### 🛠️ Quick Setup
```bash
# 1. Clone the repository
git clone https://github.com/adiooooos/AAPSP_01_security_audit_rhel7.git
cd AAPSP_01  cd rhel7-security-audit

# 2. Configure the inventory file
echo "[rhel7]" > inventory.ini
echo "your_hostname ansible_host=192.168.1.100" >> inventory.ini

# 3. Run the security audit
ansible-playbook -i inventory.ini security_audit.yml
```

---

## 🔍 Playbook Task Breakdown
| Task ID | Check | Compliance Reference | Key Parameter |
|---------|-----------------------|----------------------|---------------|
| task-03 | SSH Root Login Restriction | CIS Benchmark 5.3 | `PermitRootLogin` |
| task-04 | Password Length & Complexity | NIST SP 800-63B | `minlen=14` |
| task-07 | `/etc/passwd` File Permissions | CIS 6.1.2 | `Mode 644` |
| task-08 | SELinux Enforcing Mode | PCI DSS Req.2.2.2 | `Enforcing Mode` |
| task-09 | SSH Public Key Authentication | NSA SSH Guidelines | `PubkeyAuthentication` |

---

## ⚙️ Customize Your Audit
Tailor the audit to your needs by editing the variables in `security_audit.yml`:

```yaml
vars:
  mail_host: "smtp.yourcompany.com"  # SMTP server address
  mail_port: "587"                   # STARTTLS port
  sender_username: "audit@company.com"
  mail_to:                           # Recipient list
    - "admin@company.com"
    - "security-team@company.com"
```

**Secure your passwords** with Ansible Vault:
```bash
ansible-vault encrypt_string 'your_password' --name 'sender_password'
```

---

## ⚠️ Important Notes
1. Ensure SSH key-based authentication is configured on target hosts.
2. Verify the `audit_report.html.j2` template file exists.
3. Open ports 25, 465, or 587 on target hosts for email delivery.
4. SELinux settings may impact audit results.
5. Run audits during low-traffic periods to minimize disruption.

---

## 🌟 Why Choose This Tool?
This Ansible Playbook is your one-stop solution for RHEL 7 security audits. It’s fast, reliable, and designed to keep your servers compliant and secure. Ready to take control of your server security? Clone the repo and start auditing today! 💻
