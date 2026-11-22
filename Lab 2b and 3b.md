
# Lab 2b-2: Introduction to Bash Scripting & System Automation

## 1. Objective

The objective of this lab was to develop foundational skills in Linux Bash scripting and system automation.

The activities included:
- Navigating the Linux file system
- Creating, copying, renaming and deleting files
- Writing and executing Bash scripts
- Understanding file permissions
- Implementing loops and conditional statements
- Automating CPU, memory and disk monitoring

### Lab Environment

| Component | Description |
|---|---|
| Operating System | Ubuntu 20.04.4 LTS |
| Virtualisation | Oracle VirtualBox |
| Shell | Bash |
| Text Editor | GNU Nano |
| Username | shoban |

---

## 2. Part 1: File System Navigation and Management

### Activities Performed

I practised basic Linux commands to create directories, navigate the file system and manipulate files.

The commands included `pwd`, `mkdir`, `cd`, `touch`, `cat`, `cp`, `mv`, `rm` and `ls`.

### Evidence 1: Creating a Directory

I used the `mkdir LabFiles` command to create a new directory and navigated into it using the `cd` command.

![Creating LabFiles Directory](./screenshots/Bash%201.png)

### Evidence 2: Basic File Management Commands

I practised using the `cp`, `mv` and `rm` commands to copy, rename and delete files.

![Basic Linux Commands](./screenshots/Bash%202.png)

### Reflection Questions

**Q1. What command did you use to create a new directory?**

I used `mkdir LabFiles` to create a new directory named LabFiles. The `mkdir` command allows users to create directories directly from the Linux terminal.

**Q2. How can you view the contents of a file without opening a GUI?**

I used `cat notes.txt` to display the contents of the text file directly in the terminal.

**Q3. What is the difference between cp and mv?**

The `cp` command copies a file while keeping the original file intact. The `mv` command moves a file to another location or renames it.

---

## 3. Part 2: Creating and Executing Basic Bash Scripts

### Activities Performed

I created a Bash script named `hello_world.sh` using GNU Nano.

The script displays a personalised greeting message.

I used `chmod 777` to change the file permissions and executed the script through the Linux terminal.

### Evidence 3: Hello World Script Execution

The screenshot below shows the output after executing the Bash script.

![Hello World Script Output](./screenshots/bash%203.png)

### Reflection Questions

**Q1. What is the purpose of chmod 777?**

The command `chmod 777` gives the file owner, group and other users permission to read, write and execute the file.

The permission values are:
- Read = 4
- Write = 2
- Execute = 1

Therefore, 7 represents read, write and execute permissions.

However, using 777 is generally not recommended in production environments because it allows all users to modify the file.

**Q2. What is chmod +x used for?**

The `chmod +x` command adds execute permission to a file, allowing it to be executed as a script or program.

**Q3. Why is #!/bin/bash used at the beginning of a script?**

The line `#!/bin/bash` is called a shebang. It tells Linux to use the Bash interpreter to execute the script.

**Q4. How can you personalise script output?**

I personalised the script by using the `echo` command to display my name.

---

## 4. Part 3: Implementing Loops and Conditionals

### Activities Performed

I created a Bash script named `system_info.sh`.

The script:
- Displays the current Linux username using `whoami`
- Uses a `for` loop to count from 1 to 5
- Accepts numerical input from the user
- Uses `if`, `elif` and `else` statements
- Validates invalid user input

### Evidence 4: System Information Script

The screenshot below shows the Bash script created using GNU Nano.

![System Information Script](./screenshots/system_info_script.png)

### Evidence 5: System Information Output

The screenshot below shows the execution of the script, including the loop and conditional statements.

![System Information Output](./screenshots/output_system_info.png)

### Reflection Questions

**Q1. How does the for loop work?**

A for loop executes a set of commands repeatedly.

In my script, the variable `i` takes values from 1 to 5. During each iteration, the `echo` command displays the current number.

**Q2. What happens if the number entered is greater than 10?**

The script evaluates the condition using `-gt`, which means greater than.

If the user enters 15, the script displays the message "Your number is greater than 10."

**Q3. What happens when invalid input is entered?**

The script validates whether the input contains only digits.

If the user enters letters or invalid characters, the script displays an error message asking the user to enter a whole number.

**Q4. How could invalid input be handled more gracefully?**

The script could be improved by allowing users to re-enter their input instead of terminating immediately.

This could be implemented using a `while` loop that repeatedly prompts the user until valid input is entered.

---

## 5. Part 4: Automating System Monitoring Tasks

### Activities Performed

I created a Bash script named `system_resource_monitoring.sh` to automate the monitoring of system resources.

The script uses:
- `top` to display CPU and process information
- `free -h` to display memory usage
- `df -h` to display disk usage
- `sleep` to control monitoring intervals
- A `for` loop to repeat monitoring tasks

I used `chmod 745` to set the script permissions and executed the script through the terminal.

I entered `4` when prompted for the number of monitoring checks.

### Evidence 6: System Resource Monitoring Script

The screenshot below shows the Bash script used to automate system resource monitoring.

![System Resource Monitoring Script](./screenshots/system_resource.png)

### Evidence 7: System Resource Monitoring Output

The screenshot below shows the system monitoring results, including CPU, memory and disk usage.

![System Resource Monitoring Output](./screenshots/system_resource_output.png)

### System Monitoring Observations

The first monitoring round displayed the following information:

| Resource | Observed Value |
|---|---|
| CPU Idle | 93.3% |
| Total Memory | 5.4 GiB |
| Used Memory | 835 MiB |
| Available Memory | 4.4 GiB |
| Root Disk Size | 9.0 GB |
| Root Disk Usage | 65% |

These results provided a snapshot of the virtual machine's resource utilisation.

### Reflection Questions

**Q1. What does free -h show?**

The command `free -h` displays system memory information, including total, used, free and available RAM, as well as swap memory.

The `-h` option displays the values in a human-readable format.

**Q2. How can the script be modified to monitor network usage?**

The script could be extended using Linux monitoring tools such as `sar`, `iftop` or `vnstat`.

For example, the `sar -n DEV 1 1` command can display network interface statistics if the `sysstat` package is installed.

This would allow administrators to observe incoming and outgoing network traffic.

**Q3. Why is automation important for system administrators?**

Automation helps system administrators reduce repetitive manual work, improve efficiency and maintain consistency.

Instead of manually checking CPU, memory and disk usage, Bash scripts can perform these checks automatically at regular intervals.

Automation also supports system troubleshooting, maintenance and early detection of performance issues.

---

## 6. Challenges Encountered

### Ubuntu Graphical Interface Issue

During the lab, my Ubuntu virtual machine started in a text-based login environment instead of the graphical desktop.

I investigated the login environment and restored the Ubuntu graphical interface.

### Incorrect Script Filename

While creating my first Bash script, I encountered errors because the filename used in the terminal did not match the saved filename.

I used `ls -la` to inspect the directory and corrected the filename.

### File Permission Issues

I initially encountered difficulties executing Bash scripts because execute permissions were not enabled.

I used `chmod` to modify file permissions and `ls -l` to verify the changes.

### Incorrect Shebang

One of my scripts initially failed because the Bash interpreter path was incorrect.

After correcting the first line to `#!/bin/bash`, the script executed successfully.

### VirtualBox Clipboard Limitations

I experienced difficulties copying and pasting commands between Windows and Ubuntu.

To continue the lab, I manually entered the commands and Bash scripts.

These challenges helped me gain practical troubleshooting experience with Linux commands, permissions and Bash syntax.

---

## 7. Conclusion

This lab provided practical experience in Linux Bash scripting and basic system automation.

I learned how to navigate the Linux file system, manage files and directories, create executable scripts, implement loops and conditional statements, and automate system resource monitoring.

The system monitoring exercise demonstrated how Bash scripts can reduce repetitive administrative tasks by automatically collecting CPU, memory and disk usage information.

Although I encountered several challenges involving file permissions, script syntax and the Ubuntu environment, I was able to troubleshoot these issues and successfully execute the scripts.

Overall, this lab strengthened my understanding of Linux administration and provided a foundation for further learning in system automation.
