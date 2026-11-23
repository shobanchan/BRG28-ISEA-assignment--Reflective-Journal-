
# BRG28-ISEA — Lab 2b & Lab 3b
## Linux Bash Scripting and Automated Cloud Backup

## Introduction

This README documents my practical experience with Ubuntu Linux, Bash scripting, file management, backup automation, cron scheduling, SSH authentication, and cloud file transfers.

The labs were completed using:
- Ubuntu Linux on Oracle VirtualBox
- Microsoft Azure Ubuntu Virtual Machine
- Bash scripting
- Cron scheduler
- SSH and SCP

---

# Lab 2b — Introduction to Bash Scripting

## 1. Objective

The objective of Lab 2b was to understand basic Linux commands and develop fundamental Bash scripting skills.

The activities included:
- Creating files and directories
- Copying, moving, and removing files
- Using variables and arithmetic expressions
- Understanding Bash loops
- Creating and executing scripts
- Displaying system information
- Monitoring system resources

## 2. Basic Linux Commands

### Bash 1 — Creating a Directory

I practised creating directories using the `mkdir` command.

```bash
mkdir labfiles
```

The command creates a directory named `labfiles`.

**Screenshot:**

![Bash 1 - Creating Directory](./screenshots/bash%201.png)

### Bash 2 — File Management Commands

I practised the following Linux commands:

| Command | Description |
|---|---|
| `pwd` | Displays current working directory |
| `ls` | Lists files and directories |
| `mkdir` | Creates a directory |
| `cp` | Copies files |
| `mv` | Moves or renames files |
| `rm` | Removes files |
| `cd` | Changes directory |

These commands helped me understand how Linux manages files and directories.

**Screenshot:**

![Bash 2 - File Management](bash2.png)

## 3. Hello World Bash Script

I created a basic Bash script to understand how commands are executed from a script file.

The `echo` command displays text in the terminal.

**Screenshot:**

![Hello World Script](hello_world_sh.png)

## 4. Bash Variables, Arithmetic and Loops

I practised using variables to store information, arithmetic expressions to perform calculations, and loops to repeat commands.

Example:

```bash
total=0

for i in {1..5}
do
    ((total+=i))
done

echo "Total: $total"
```

The loop adds the numbers from 1 to 5.

Expected output:

```text
Total: 15
```

This demonstrated how loops can automate repetitive calculations.

## 5. System Information Script

I worked with a Bash script that retrieves and displays Linux system information.

This activity helped me understand how Linux commands can be combined into scripts.

**Script Screenshot:**

![System Information Script](system_info_script.png)

**Output Screenshot:**

![System Information Output](system_info_output.png)

## 6. System Resource Monitoring

I worked with a script to display system resource information.

Resource monitoring helps system administrators identify performance issues and understand resource utilization.

**Script Screenshot:**

![System Resource Script](system_resource.png)

**Output Screenshot:**

![System Resource Output](system_resource_output.png)

## 7. Lab 2b Reflection

As a beginner in Bash scripting, I initially found it difficult to understand how scripts, variables, and loops work.

Through practical exercises, I learnt that Bash scripts contain commands executed in sequence.

I also learnt how Linux commands can be combined to automate repetitive tasks.

These concepts provided the foundation for Lab 3b.

---

# Lab 3b — Automated Backup and Cloud Transfer

## 1. Objective

The objective of Lab 3b was to create an automated backup system using Bash scripting.

The activities included:
- Creating test files and directories
- Writing a backup script
- Copying files recursively
- Compressing files using ZIP
- Adding timestamps to backup filenames
- Moving scripts to `/usr/bin`
- Scheduling automatic backups using cron
- Configuring SSH key authentication
- Transferring backup files to Azure using SCP

## 2. Lab Environment

| Component | Configuration |
|---|---|
| Local OS | Ubuntu Linux |
| Virtualization | Oracle VirtualBox |
| Username | shoban |
| Documents | `/home/shoban/Documents` |
| Backup folder | `/home/shoban/backup` |
| Script | `/usr/bin/testscript` |
| Cloud provider | Microsoft Azure |
| Cloud OS | Ubuntu Linux |
| Azure username | azureuser |
| Transfer protocol | SCP over SSH |

---

## Deliverable 1 — Practice Bash Commands

The basic Bash commands, variables, arithmetic operations, and loops were practised during Lab 2b.

These skills were applied when developing the automated backup script.

## Deliverable 2 — Test Files and Directories Created

I created test files and a subdirectory inside the Documents folder.

Commands used:

```bash
echo "This is my first backup test file" > /home/shoban/Documents/file1.txt

mkdir /home/shoban/Documents/School

echo "This is my school assignment" > /home/shoban/Documents/School/assignment.txt
```

I verified the directory structure using:

```bash
ls -R /home/shoban/Documents
```

The `-R` option recursively lists directories and their contents.

**Screenshot:**

![Test Files and Directories](lab3b_02_documents.png)

## Deliverable 3 — Basic Backup Script Working

I created a Bash script using:

```bash
nano /home/shoban/testscript
```

Initial script:

```bash
#!/bin/bash

cp -R /home/shoban/Documents/. /home/shoban/backup/

echo "Backup completed successfully"
```

The `cp -R` command recursively copies files and subdirectories.

I granted execute permissions:

```bash
chmod 777 /home/shoban/testscript
```

I executed the script:

```bash
/home/shoban/testscript
```

I verified the backup using:

```bash
ls -R /home/shoban/backup
```

The test files and School subdirectory were successfully copied.

**Screenshot:**

![Basic Backup Script](lab3b_03_script.png)

## Deliverable 4 — Script Moved to /usr/bin

I moved the script into `/usr/bin`:

```bash
sudo mv /home/shoban/testscript /usr/bin/testscript
```

I changed its ownership:

```bash
sudo chown root:root /usr/bin/testscript
```

I then applied execute permissions:

```bash
sudo chmod 755 /usr/bin/testscript
```

The `/usr/bin` directory is normally included in the Linux PATH environment variable.

This allows the script to be executed from different directories.

I tested it using:

```bash
cd /tmp
testscript
```

The script executed successfully.

**Screenshot:**

![Script Moved to usr bin](lab3b_04_usrbin.png)

## Deliverable 5 — ZIP Archive with Date Filename

I modified the backup script to create compressed ZIP archives.

The date variable was defined as:

```bash
now=$(date +"%d_%m_%y_%H_%M")
```

The date format includes:

| Format | Meaning |
|---|---|
| `%d` | Day |
| `%m` | Month |
| `%y` | Year |
| `%H` | Hour |
| `%M` | Minute |

The ZIP command was:

```bash
zip -r "$zip_file" backup/
```

I verified the ZIP files using:

```bash
ls -lh /home/shoban/*.zip
```

The filenames included the date and time, allowing multiple backups to be distinguished.

**Screenshot:**

![Dated ZIP Backup](lab3b_05_zip.png)

## Deliverable 6 — Cron Job Setup

I checked whether the cron service was running:

```bash
sudo systemctl status cron
```

The service was active.

I opened the cron configuration:

```bash
sudo nano /etc/crontab
```

I added:

```text
9 * * * * shoban /usr/bin/testscript
```

This schedules the backup script to execute at nine minutes past every hour.

I verified the configuration:

```bash
tail -n 2 /etc/crontab
```

**Screenshot:**

![Cron Configuration](lab3b_06_cron.png)

## Deliverable 7 — Successful Cron Execution

To test automatic execution without waiting an hour, I temporarily changed the cron schedule:

```text
* * * * * shoban /usr/bin/testscript
```

This instructed cron to run the script every minute.

I verified the resulting backup files:

```bash
ls -lt /home/shoban/*.zip
```

New ZIP files appeared with different timestamps.

After testing, I restored the hourly schedule:

```text
9 * * * * shoban /usr/bin/testscript
```

**Screenshot:**

![Cron Execution Verification](lab3b_07_cron_output.png)

## Deliverable 8 — SCP Cloud Transfer

I used SCP to securely transfer ZIP backup files from my VirtualBox Ubuntu machine to Microsoft Azure.

SCP transfers files through an encrypted SSH connection.

The transfer command followed this format:

```bash
scp -i ~/.ssh/azure_backup_key \
/home/shoban/backup_file.zip \
azureuser@<AZURE_PUBLIC_IP>:/home/azureuser/
```

I replaced the example filename and IP address with the actual values during execution.

The transfer reached 100%.

I then connected to Azure and verified the transferred files:

```bash
ls -lt /home/azureuser/*.zip
```

The ZIP files appeared in the Azure home directory.

**SCP Screenshot:**

![SCP File Transfer](lab3b_08_scp.png)

**Azure Verification Screenshot:**

![Azure Backup Verification](lab3b_08_azure.png)

## Deliverable 9 — SSH Key Authentication

I generated an Ed25519 SSH key pair:

```bash
ssh-keygen -t ed25519 -f ~/.ssh/azure_backup_key
```

This created:
- `azure_backup_key` — private key
- `azure_backup_key.pub` — public key

I registered the public key with my Azure Ubuntu VM.

I tested the SSH connection using:

```bash
ssh -i ~/.ssh/azure_backup_key \
azureuser@<AZURE_PUBLIC_IP>
```

I also tested SSH using administrator privileges:

```bash
sudo ssh -i /home/shoban/.ssh/azure_backup_key \
azureuser@<AZURE_PUBLIC_IP>
```

The connection succeeded.

SSH host key verification helps confirm the identity of the remote server before establishing a trusted connection.

**Screenshot:**

![SSH Authentication](lab3b_09_ssh.png)

## Deliverable 10 — Final Automated Backup Script

The final Bash script combines recursive copying, ZIP compression, timestamp generation, and SCP transfer.

```bash
#!/bin/bash

# Get current date and time
now=$(date +"%d_%m_%y_%H_%M")

# Define directories
source_dir="/home/shoban/Documents"
backup_dir="/home/shoban/backup"
zip_file="/home/shoban/$now.zip"

# Create backup directory
mkdir -p "$backup_dir" || exit 1

# Copy documents recursively
cp -R "$source_dir/." "$backup_dir/" || exit 1

# Create ZIP archive
cd /home/shoban || exit 1
zip -r "$zip_file" backup/ || exit 1

# Transfer ZIP to Azure
scp -o BatchMode=yes -o ConnectTimeout=15 \
-i /home/shoban/.ssh/azure_backup_key \
"$zip_file" azureuser@<AZURE_PUBLIC_IP>:/home/azureuser/ || exit 1

# Display completion message
echo "Backup and cloud transfer completed: $now.zip"
```

**Note:** `<AZURE_PUBLIC_IP>` is a placeholder that must be replaced with the actual Azure VM public IP address before running the script.

### Final Testing

I executed the final script:

```bash
testscript
```

The script successfully created a ZIP archive and transferred it to Azure.

I also tested the automatic cloud transfer by temporarily scheduling the script every minute.

After verifying the uploaded backups on Azure, I restored the hourly cron schedule.

**Final Script Screenshot:**

![Final Backup Script](lab3b_10_final_script.png)

**Final Execution Screenshot:**

![Final Cloud Backup](lab3b_10_final_output.png)

---

# Lab 3b — Reflection Questions

## 1. Why is using absolute paths important in scripts run by cron?

Absolute paths specify the complete location of files and directories.

Cron may execute scripts from a different working directory and with a different environment from an interactive terminal.

Using absolute paths ensures that the script can locate the required files regardless of its working directory.

For example:

```bash
/home/shoban/Documents
```

## 2. What are the benefits of cloud exporting for backups?

Cloud exporting provides an additional copy of important files on a remote system.

If the local computer experiences hardware failure, accidental deletion, or data corruption, a separate cloud backup may help restore the files.

Cloud storage also provides remote accessibility and reduces dependence on a single physical computer.

## 3. How does cron differ from manual execution?

Manual execution requires a user to enter a command.

Cron automatically executes commands according to a predefined schedule.

For example:

```bash
testscript
```

runs the script manually.

However:

```text
9 * * * * shoban /usr/bin/testscript
```

runs it automatically at nine minutes past every hour while the machine is running.

## 4. What happens if SSH keys are not accepted ahead of time?

SSH may prompt the user to verify the remote server's fingerprint or request authentication.

These prompts can interrupt automated cron jobs because cron cannot interact with the terminal.

For automated backups, the remote server's identity should be verified in advance, and the appropriate SSH public key must be authorized.

## 5. How can login messages help improve user/system engagement?

Login messages can display useful information when users access a Linux system.

Tools such as `figlet` and `neofetch` can display customized messages or system information.

These features may improve user experience and help administrators identify the system they are accessing.

Login messages can also communicate maintenance notices and security reminders.

---

# Challenges Encountered

## 1. Incorrect Script Paths

I encountered errors caused by entering incorrect file paths and accidentally combining commands.

I resolved these issues by checking the file locations and executing commands separately.

## 2. Bash Variable Syntax

I encountered a `command not found` error because the date variable was incorrectly assigned.

I corrected it to:

```bash
now=$(date +"%d_%m_%y_%H_%M")
```

This helped me understand that Bash variable assignments must not contain spaces around the equals sign.

## 3. Incorrect ZIP File Path

I initially used an incorrect directory path when checking ZIP files.

The corrected command was:

```bash
ls -lh /home/shoban/*.zip
```

This reinforced the importance of correct directory paths and wildcard syntax.

## 4. SSH Authentication Problems

My initial SSH connection failed because the VirtualBox Ubuntu machine did not have the required private key.

I generated an SSH key pair and registered the public key with Azure.

I also corrected an SSH command that contained an additional `ssh` argument.

## 5. SSH Public Key Formatting

Azure initially rejected the public key because the manually transcribed key contained incorrect characters.

I verified the original key using:

```bash
ssh-keygen -lf ~/.ssh/azure_backup_key.pub
```

After correcting the public key, Azure accepted it.

## 6. Cron Scheduling Verification

Initially, I could not verify automatic execution because the script was scheduled to run only once per hour.

I temporarily changed the schedule to every minute.

After confirming automatic backup creation and cloud transfer, I restored the hourly schedule.

---

# Conclusion

Lab 2b introduced me to basic Linux commands, Bash variables, loops, file management, and script execution.

Lab 3b expanded these skills by introducing automated backups, ZIP compression, cron scheduling, SSH authentication, and SCP cloud transfers.

Through these exercises, I developed a better understanding of how Linux commands can be combined to automate routine administrative tasks.

The final backup system demonstrated how files can be copied, compressed, timestamped, and securely transferred to a remote Azure virtual machine.

The troubleshooting process also reinforced the importance of correct syntax, file permissions, absolute paths, and SSH key management.
