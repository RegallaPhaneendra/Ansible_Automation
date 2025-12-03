# Ansible_Automation
# Ansible Package Management
This project demonstrate how to use ansible to efficiently manage software packages across different OS. It leverages Ansible's features to handle OS specific packages management and rollback capabilities.

## Table of Contents
* [Project-structure](#project-structure)
* [How it works](#how-it-works)
* [Installation](#installation)
* [Usage](#usage)

## Project Structure
```
├── README.md
├── ansible.cfg
├── inventory
├── playbooks
│   ├── deploy.yml
│   └── rollback.yml
└── roles
    ├── deploy
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    └── rollback
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── tasks
        │   └── main.yml
        ├── templates
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
```

## How it Works
The project is structured around two primary roles: ''deploy'' and ''rollback''.

* **deploy:** This role handles the installation of packages. It checks whether a package is already installed and, if not, proceeds with the installation.
* **rollback:** This role manages the removal of packages. It checks for the installation marker file (created during deployment) before attempting to remove a package. This ensures that only previously installed packages are removed during a rollback.

## Installation

1. **Clone the repository**
2. **Configure `ansible.cfg`** 
3. **Create the inventory file**

## Usage
**Installation of package:**
```ansible-playbook -i inventory playbooks/deploy.yml  # Install the package mentioned in default directory```

**Rollback:**
```ansible-playbook -i inventory playbooks/rollback.yml # Remove the packages```
