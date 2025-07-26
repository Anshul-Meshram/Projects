# Projects
Here’s the **final README.md** for your **Ansible LAMP project** (`DevOps/Ansible-WSL-LAMP` folder).

You can copy-paste this into a `README.md` file inside that folder:

---

``markdown
# Ansible LAMP Stack Automation (WSL Ubuntu)

This project automates the setup of a **LAMP Stack (Linux, Apache, MySQL, PHP)** and deploys a simple PHP website using **Ansible**, all running on **WSL Ubuntu** (no VirtualBox or Docker needed).

---

## What This Project Does
- Installs **Apache2**, **PHP**, and **MySQL** on your local Ubuntu (WSL).
- Configures a **MySQL database and user**.
- Deploys a **sample PHP website** with `index.html`, `process.php`, and `result.php`.
- Uses **Ansible playbooks** for full automation:
  - `lampstack.yml` – installs LAMP components.
  - `mysqlmodule.yml` – sets up MySQL database and user.
  - `deploywebsite.yml` – deploys the website to Apache’s web root.

---

## Project Structure
```

Ansible-WSL-LAMP/
├── inventory.ini         # Inventory file (defines localhost as target host)
├── lampstack.yml         # Playbook for Apache, PHP, MySQL
├── mysqlmodule.yml       # Playbook for MySQL config
├── deploywebsite.yml     # Playbook to deploy website
└── website/              # HTML & PHP files deployed to /var/www/html

```

---

## How to Run

### 1. Install Ansible on WSL Ubuntu
```bash
sudo apt update
sudo apt install ansible -y
ansible --version
````

### 2. Clone this Repository

```bash
git clone https://github.com/<your-username>/<your-main-repo>.git
cd <your-main-repo>/DevOps/Ansible-WSL-LAMP
```

### 3. Run the Playbooks

Run each step with privilege escalation:

```bash
ansible-playbook -i inventory.ini lampstack.yml -c local --ask-become-pass
ansible-playbook -i inventory.ini mysqlmodule.yml -c local --ask-become-pass
ansible-playbook -i inventory.ini deploywebsite.yml -c local --ask-become-pass
```

### 4. Access the Website

Open your browser and go to:

```
http://localhost
```

You should see the sample PHP site deployed by Ansible.
