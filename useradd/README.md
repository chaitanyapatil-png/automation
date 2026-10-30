# Linux User Management Automation

A secure, automated Bash utility for provisioning and tearing down multiple Linux user accounts simultaneously. Designed for sysadmins and DevOps environments, this script handles bulk user creation, automatic UID incrementing, and secure home directory setup.

## Features
* **Bulk Provisioning:** Add or remove multiple users in a single command.
* **Smart UID Assignment:** Pass a starting UID (`-i`), and the script automatically increments it for each subsequent user to prevent ID conflicts.
* **Metadata Tagging:** Assign system comments/roles (`-c`) to newly created accounts.
* **Root Enforcement:** Built-in security check ensures the script only executes with elevated privileges.
* **Clean Teardown:** The `-r` flag safely deletes users and their associated home directories.

## Prerequisites
* Linux environment (Debian/Ubuntu, CentOS/RHEL, etc.)
* `bash` shell
* `sudo` privileges

## Installation
Clone the repository and make the script executable:
```bash
git clone [https://github.com/yourusername/linux-user-manager.git](https://github.com/yourusername/linux-user-manager.git)
cd linux-user-manager
chmod +x manage_users.sh

usage

sudo ./manage_users.sh user1 user2 user3
sudo ./manage_users.sh -c "Developer" -i 1050 dev1 dev2
sudo ./manage_users.sh -r dev1 dev2