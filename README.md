# 🚀 RHEL 7 Security Audit Automation

#### Elevate Your Server Security with Ansible! 🔒

![Ansible](https://img.shields.io/badge/Ansible-2.5+-red?logo=ansible&style=for-the-badge)
![RHEL](https://img.shields.io/badge/RHEL-7.x-orange?logo=red-hat&style=for-the-badge)

Welcome to the **AAPSP_01 Security Audit for RHEL 7**! This Ansible-powered tool is your go-to solution for auditing and hardening your RHEL 7 systems with ease and precision. Designed for sysadmins and security enthusiasts, this playbook ensures your systems align with best practices while keeping things simple and automated. 🚀  

#### See It in Action! 📸
![image](https://github.com/user-attachments/assets/c662512c-d4f0-4829-b51b-93cebd82fc8c)


---
## 🎯 **What Does This Tool Do?**  
This Ansible playbook ([`security_audit_rhel7.yml`](https://github.com/adiooooos/AAPSP_01_security_audit_rhel7/blob/main/security_audit_rhel7.yml)) is crafted to:  
- 🔍 **Audit** your RHEL 7 system for security compliance.  
- 🛡️ **Identify** potential vulnerabilities based on industry standards.  
- 📝 **Report** findings in a clear, actionable format.  
- ⚙️ **Automate** the auditing process to save you time and effort.  

Whether you're securing a single server or an entire fleet, this tool simplifies the process while delivering professional-grade results.  

---

## ✨ **Why Choose AAPSP_01 Security Audit?**  
- **Ansible-Powered**: Leverage the power of Ansible for seamless automation.  
- **RHEL 7 Focused**: Tailored specifically for Red Hat Enterprise Linux 7.  
- **Easy to Use**: Minimal setup, maximum impact.  
- **Customizable**: Adapt the playbook to your specific needs.  
- **Open Source**: Free, transparent, and community-driven.  

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

## 🚀 **Getting Started**  

### **Prerequisites**  
Before you dive in, ensure you have:  
- 🖥️ A RHEL 7 system (or compatible).  
- 🛠️ Ansible installed (`ansible` version 2.9 or higher recommended).  
- 📡 SSH access to the target system(s).  
- 📄 Basic knowledge of YAML and Ansible playbooks.  

### **Installation**  
1. **Clone the Repository**  
   ```bash
   git clone https://github.com/adiooooos/AAPSP_01_security_audit_rhel7.git
   cd AAPSP_01_security_audit_rhel7
   ```

2. **Set Up Your Inventory**  
   Create an Ansible inventory file (e.g., `inventory.yml`) with your target hosts:  
   ```yaml
   all:
     hosts:
       your_server:
         ansible_host: <your_server_ip>
         ansible_user: <your_ssh_user>
   ```

3. **Run the Playbook**  
   Execute the audit with a single command:  
   ```bash
   ansible-playbook -i inventory.yml security_audit_rhel7.yml
   ```

4. **Review the Results**  
   The playbook will generate a report highlighting compliance status and recommendations. Check the output for details!  

---

## 🛠️ **How It Works**  
The [`security_audit_rhel7.yml`](https://github.com/adiooooos/AAPSP_01_security_audit_rhel7/blob/main/security_audit_rhel7.yml) playbook:  
1. **Scans** system configurations (e.g., file permissions, services, and packages).  
2. **Validates** against security benchmarks inspired by CIS and STIG guidelines.  
3. **Logs** findings for easy review and remediation.  

> 💡 **Pro Tip**: Customize the playbook by editing variables or tasks to match your organization’s security policies!  

---

## 📋 **Example Output**  
After running the playbook, you’ll see a clean summary like this:  
```
TASK [Check SSH Configuration] *************************
ok: [your_server] => SSH hardening compliant

TASK [Verify Auditd Status] ****************************
changed: [your_server] => Auditd is running

TASK [Check Unnecessary Services] **********************
failed: [your_server] => Telnet detected! Action required.
```

---

## 🌈 **Customization**  
Want to tweak the audit?  
- 📝 Modify variables in the `vars/` directory to adjust checks.  
- 🛠️ Add or remove tasks in `security_audit_rhel7.yml` for specific needs.  
- 🔄 Integrate with your existing Ansible workflows for seamless automation.  

---

## 🛡️ **Security Notes**  
- Always test the playbook in a non-production environment first.  
- Ensure you have backups before making changes.  
- Review the playbook’s tasks to understand its actions.  

---

## 🤝 **Contributing**  
Love this project? Join the community!  
- ⭐ Star the repo to show your support.  
- 🐛 Report bugs or suggest features via [Issues](https://github.com/adiooooos/AAPSP_01_security_audit_rhel7/issues).  
- 📦 Submit pull requests to enhance the playbook.  

---

## 📬 **Contact**  
Have questions? Reach out via [GitHub Issues](https://github.com/adiooooos/AAPSP_01_security_audit_rhel7/issues) or connect with the community on [X](https://x.com).  

---

## 🌟 **License**  
This project is licensed under the MIT License. See the [LICENSE](https://github.com/adiooooos/AAPSP_01_security_audit_rhel7/blob/main/LICENSE) file for details.  

---

**Secure your RHEL 7 systems with confidence!**  
Let’s make security auditing simple, fast, and fun. Try **AAPSP_01 Security Audit** today! 🎉

## 🌟 Why Choose This Tool?
This Ansible Playbook is your one-stop solution for RHEL 7 security audits. It’s fast, reliable, and designed to keep your servers compliant and secure. Ready to take control of your server security? Clone the repo and start auditing today! 💻
