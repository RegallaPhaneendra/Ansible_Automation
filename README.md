# Ansible_automate
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
The project is structured around two primary roles: 'deploy' and 'rollback'.

* **'deploy':** This role handles the installation of packages. It checks if the package is already installed, and then install the software.
* **'rollback':** This role manages the removal of packages. It checks for the installation marker file(created during installation) before attempting to remove the package. This ensures that only installed are removed during rollback.

## Installation

1. **Clone the repository:**
2. **Configure `ansible.cfg`** 
3. **Create the inventory file**

## Usage
**Installation of package:**
```ansible-playbook -i inventory playbooks/deploy.yml  # Install the package mentioned in default directory```

**Rollback:**
```ansible-playbook -i inventory playbooks/rollback.yml # Remove the packages```
