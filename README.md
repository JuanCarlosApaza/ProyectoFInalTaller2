# Proyecto Ansible - Innovasys

Este repositorio contiene la automatización de configuración de un servidor utilizando **Ansible**.  
El proyecto incluye la creación de roles (Apache y Samba), inventario de hosts, y un playbook principal para ejecutar la configuración en un servidor remoto.

---

## 📌 Requisitos previos

Antes de comenzar, asegúrate de tener lo siguiente instalado en tu máquina de control (la computadora desde donde ejecutarás Ansible):

- **Git**
- **Python 3**
- **Ansible**

### 🔹 Instalación de Git
```bash
sudo apt update
sudo apt install git -y
🔹 Instalación de Ansible
sudo apt update
sudo apt install software-properties-common -y
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
Verifica la instalación:

ansible --version

🔹 Estructura del repositorio
innovasys/
├── inventory.ini        # Inventario con los hosts administrados
├── playbook.yml         # Playbook principal
├── roles/               # Roles de Ansible
│   ├── apache/          # Configuración del rol Apache
│   │   ├── tasks/
│   │   ├── handlers/
│   │   └── templates/
│   └── samba/           # Configuración del rol Samba
│       ├── tasks/
│       ├── handlers/
│       └── templates/
└── README.md            # Este archivo

🔹 Clonar este repositorio
git clone https://github.com/USUARIO/innovasys.git
cd innovasys

🔹 Configuración de conexión SSH

Debes tener acceso al servidor remoto con un usuario que pueda ejecutar sudo.
Por ejemplo, en tu inventario inventory.ini podrías tener:

[servidores]
servidor-innovasys ansible_host=192.168.10.100 ansible_user=operador


🔹 Asegúrate de poder conectarte al servidor usando SSH antes de ejecutar el playbook:

ssh operador@192.168.10.100

🔹  Ejecutar el Playbook

Para ejecutar el playbook principal con privilegios de administrador, utiliza:

ansible-playbook -i inventory.ini playbook.yml --become --ask-become-pass
