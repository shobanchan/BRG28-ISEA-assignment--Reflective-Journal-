
# Additional Server Setup – MariaDB on Ubuntu

## 1. Introduction

The objective of this lab was to install, configure, secure, and verify an additional server on Ubuntu Linux.

For this assignment, I selected **MariaDB**, an open-source relational database management system (RDBMS).

The purpose of this lab was to understand:

- What an additional server is.
- Why additional servers are required.
- The relationship between Ubuntu, VirtualBox, and server applications.
- How to install and configure MariaDB.
- How to secure and verify a database server.
- How to troubleshoot basic Linux command errors.

In my previous labs, I installed and configured Apache as a web server. This lab introduced me to a different type of server that manages data rather than delivering webpages.

---

## 2. Understanding Ubuntu and Additional Servers

### 2.1 What is Ubuntu?

Ubuntu is a Linux-based operating system, similar to Windows and macOS.

An operating system manages computer hardware, system resources, and applications.

In my previous labs, I installed Ubuntu using Oracle VirtualBox on my Windows laptop.

This allowed me to run Ubuntu as a guest operating system without replacing Windows.

**My lab environment:**

| Component | Description |
|---|---|
| Host Operating System | Windows |
| Virtualization Software | Oracle VirtualBox |
| Guest Operating System | Ubuntu 20.04 |
| Additional Server | MariaDB |
| Database Server Version | MariaDB 10.3.39 |

### 2.2 What is an Additional Server?

An additional server refers to a server application installed to provide a specific service within an existing computing environment.

Different servers perform different functions.

| Server | Purpose |
|---|---|
| Apache | Hosts and delivers webpages |
| MariaDB | Stores and manages database information |
| Syslog | Collects system and application logs |
| DNS | Translates domain names into IP addresses |
| DHCP | Automatically assigns IP addresses |
| NFS | Provides file sharing between Linux systems |
| Samba | Enables file sharing with Windows systems |

**My Understanding:**

Initially, I was confused about the difference between Ubuntu and a server.

I learned that Ubuntu is an operating system, while MariaDB and Apache are server applications installed on an operating system.

A server does not necessarily require a separate physical computer.

Multiple server applications can run on the same Ubuntu operating system.

For example:

- Apache provides web services.
- MariaDB provides database services.
- Both can operate on the same Ubuntu virtual machine.

### 2.3 Why Are Additional Servers Needed?

Additional servers are required because different applications and network services perform different tasks.

For example, an online shopping website may require:

1. A web server to display webpages.
2. A database server to store customer information and orders.
3. A logging server to record system activities and errors.

Each server provides a different service.

Separating these responsibilities helps administrators manage, maintain, and secure individual services.

---

## 3. Why I Selected MariaDB

I selected MariaDB because databases are widely used in business applications, websites, and enterprise IT environments.

MariaDB is a relational database management system that stores information in structured tables.

Examples of information stored in databases include:

- Customer information
- Employee records
- Product inventories
- Financial transactions
- Application data

MariaDB uses **Structured Query Language (SQL)** to manage and retrieve information.

### Difference Between Apache and MariaDB

| Apache | MariaDB |
|---|---|
| Web server | Database server |
| Handles HTTP requests | Handles database queries |
| Delivers webpages | Stores and retrieves data |
| Commonly uses ports 80 and 443 | Commonly uses port 3306 |

**My Understanding:**

Apache and MariaDB serve different purposes.

Apache delivers website content, while MariaDB manages the information used by applications.

Both services can work together when developing a database-driven website.

---

## 4. System Preparation

Before installing MariaDB, Ubuntu packages should be updated.

### Step 1 – Update Ubuntu

```bash
sudo apt update && sudo apt upgrade -y
```

**Command Explanation:**

- `sudo` – Executes a command with administrative privileges.
- `apt update` – Updates the available package information.
- `&&` – Runs the next command if the previous command succeeds.
- `apt upgrade -y` – Upgrades installed packages automatically.

### Step 2 – Install Prerequisites

```bash
sudo apt install -y curl wget gnupg lsb-release ca-certificates
```

These packages provide utilities for downloading software, managing security keys, and identifying system information.

---

## 5. Installing MariaDB

### Step 1 – Install MariaDB Server and Client

```bash
sudo apt install -y mariadb-server mariadb-client
```

**Explanation:**

- `mariadb-server` – Installs the database server.
- `mariadb-client` – Provides tools to connect to and manage the database.
- `-y` – Automatically confirms the installation.

### Step 2 – Start MariaDB

```bash
sudo systemctl start mariadb
```

This command starts the MariaDB database service.

### Step 3 – Enable MariaDB

```bash
sudo systemctl enable mariadb
```

This configures MariaDB to start automatically when Ubuntu boots.

### Step 4 – Verify MariaDB Service

```bash
sudo systemctl status mariadb
```

The expected output includes:

```text
Active: active (running)
```

This indicates that the MariaDB service is running.

**Screenshot – MariaDB Service Status**

![MariaDB Service Status](./screenshots/MariaDB_status.png)

---

## 6. Securing MariaDB

After installation, I completed the MariaDB security configuration.

### Step 1 – Run Security Configuration

```bash
sudo mysql_secure_installation
```

This command launches an interactive security configuration process.

### Security Configuration Options

| Configuration | Purpose |
|---|---|
| Configure root authentication | Protect administrative access |
| Remove anonymous users | Prevent anonymous database access |
| Disallow remote root login | Restrict remote administrative access |
| Remove test database | Remove an unnecessary default database |
| Reload privilege tables | Apply updated access privileges |

After completing the process, the terminal displayed:

```text
Installation should now be secure.

Thanks for using MariaDB!
```

**My Understanding:**

Securing a database server is important because databases may contain sensitive information.

Removing unnecessary accounts and restricting administrative access helps reduce security risks.

The security configuration provides basic protection, although further security measures may be required in a production environment.

**Screenshot – MariaDB Security Configuration**

![MariaDB Security Configuration](./screenshots/Installing_MariaDB2.png)

---

## 7. Verifying MariaDB

After securing MariaDB, I tested the database connection.

### Step 1 – Connect to MariaDB

```bash
sudo mysql -u root -p
```

**Command Explanation:**

- `sudo` – Executes the command with administrative privileges.
- `mysql` – Launches the database client.
- `-u root` – Specifies the root database account.
- `-p` – Prompts for a password.

After entering the password, the terminal displayed:

```text
Welcome to the MariaDB monitor.

Your MariaDB connection id is 44

Server version: 10.3.39-MariaDB
```

This confirmed that I successfully connected to MariaDB.

**Screenshot – Successful MariaDB Login**

![MariaDB Login](./screenshots/MariaDB_login.png)

### Step 2 – Display Existing Databases

Inside MariaDB, I entered:

```sql
SHOW DATABASES;
```

This SQL command displays the databases available on the server.

The command executed successfully and displayed the existing databases.

This verified that MariaDB could process SQL commands and retrieve database information.

**Screenshot – MariaDB Database Verification**

![MariaDB Database Verification](./screenshots/Showing_databases.png)

### Step 3 – Exit MariaDB

```sql
EXIT;
```

This command closes the MariaDB session and returns to the Ubuntu terminal.

---

## 8. Challenges Encountered

### Issue 1 – Incorrect Command Syntax

During the MariaDB verification process, I initially entered:

```bash
sudo mysql-u root -p
```

The terminal returned:

```text
sudo: mysql-u: command not found
```

### Cause

The command was missing a space between `mysql` and `-u`.

As a result, Ubuntu interpreted `mysql-u` as a single command rather than recognizing `-u` as an option.

### Solution

I corrected the command:

```bash
sudo mysql -u root -p
```

After correcting the syntax, I successfully connected to MariaDB.

### What I Learned

This issue helped me understand that Linux commands require accurate syntax.

Even a missing space can cause a command to fail.

I also learned to read terminal error messages carefully to identify and correct problems.

---

## 9. Learning Outcomes

Through this lab, I developed a better understanding of Linux server administration and database services.

### 9.1 Understanding Operating Systems

I learned that Ubuntu is an operating system and can run either directly on a computer or inside a virtual machine.

VirtualBox allows Ubuntu to run as a guest operating system on my Windows laptop.

### 9.2 Understanding Additional Servers

I learned that an additional server is not necessarily another physical computer.

It can be a software service installed on an existing operating system.

Different server applications provide different functions.

### 9.3 Understanding MariaDB

I learned that MariaDB is a database server used to store, organize, and retrieve structured information.

Unlike Apache, which provides web services, MariaDB provides database management services.

### 9.4 Linux Administration

I gained experience using Linux terminal commands to:

- Install software packages.
- Start server services.
- Enable services during startup.
- Check service status.
- Access a database server.

### 9.5 Database Security

I learned the importance of securing a database server by configuring authentication, removing unnecessary accounts, and restricting administrative access which is called ###server hardening


---

## 10. Conclusion

In this lab, I successfully installed MariaDB on Ubuntu, completed its initial security configuration, and verified that I could connect to the database server.

The lab helped me understand the relationship between operating systems, virtualization, and server applications.

Previously, I had configured Apache as a web server. By installing MariaDB, I learned how a database server provides a different service within a Linux environment.



