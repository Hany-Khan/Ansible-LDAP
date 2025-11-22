<img width="680" height="1280" alt="image" src="https://github.com/user-attachments/assets/2d6a97e5-212a-4130-aaa7-beba909f8440" /># End-to-End OpenLDAP Automation (Ansible + Bash Menu Interface)
This project provides a fully automated deployment workflow for an OpenLDAP server and client environment using Ansible. It includes installation, configuration of slapd.conf and database files, LDIF population, firewall/NSS setup, and a Bash-driven interactive automation menu.

Features include:
- Automated server & client package installation
- Database + slapd.conf provisioning
- Dynamic LDIF population (users, OUs, hosts, groups)
- iptables-based firewall automation
- NSS + nslcd configuration

Interactive Bash menu for running individual or full deployments
Great for reproducible labs, DevOps workflows, and identity management practice.

---

# Features
Automated Server & Client Installation:
Installs all required OpenLDAP packages (openldap-servers, openldap-clients, nss-pam-ldapd, etc.) depending on the chosen target (server or client).

This configuration automatically:
- Backs up slapd.d
- Deploys a fresh slapd.conf
- Initializes database directories
- Restarts + validates the slapd service

LDIF Tree Provisioning:
Automatically builds the entire LDAP tree using structured LDIF files:
- Base domain
- OU structure (accounts, hosts, groups)
- Users and host entries
- Group memberships
- Email attribute updates

Firewall & NSS Configuration:
Configures iptables to enforce LDAP access rules per subnet and deploys the NSS / nslcd client configuration to enable LDAP-based host and user resolution.

Interactive Bash Menu:
1. Install packages
2. Configure database
3. Add LDIF entries
4. Configure firewall + NSS
5. Run a full deployment end-to-end

---

Tech Stack:
For this project, you will need:
- Ansible (roles, tasks, idempotent execution)
- OpenLDAP
- Linux (CentOS/RHEL-based)
- iptables
- nslcd / NSS
- Bash scripting

---

For this project, you will need this required tree structure:
<img width="680" height="1280" alt="image" src="https://github.com/user-attachments/assets/1acd4bb3-1d77-4f63-b038-db73d0443ffe" />
