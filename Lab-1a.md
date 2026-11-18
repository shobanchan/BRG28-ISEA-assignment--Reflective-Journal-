# Day 1a : Introduction to GitHub

## Lab Ojective
The objective of this activity was to become familiar with GitHub and understand how repositories can be used to document laboratory activities, track changes, and record learning progress.

## Activites Performed

1) I accessed Github.com and created am account. From there , i created a repository named BRG28-ISEA-assignment--Reflective-Journal-.
2) I then created a README.md file using GitHub's online editor. 
3) An introduction to my repository, a summary of my lab activities, and my learning objectives are all included in the file.
4) I made my first commit after making adjustments to the README file.
5) Cloning my GitHub repository to my local machine by installing Git. 
6) I then opened Command Prompt and used the following command to clone my GitHub repository:
   git clone https://github.com/shobanchan/BRG28-ISEA-assignment--Reflective-Journal-.git
   After cloning, I navigated into the repository directory and executed:
   git status



## Observation 

Being new to GitHub, i didn't understand what is the function of GitHub and the relantionship between Git and GitHub. Everything was foriegn to me. With the help of Youtube and Chatpgt , i understood the functionality of GitHUb.
I observed the function of "markdown" and usage for formatting documentation. For example, the # symbol creates headings, while hyphens can be used to create bullet points.
"Commit" records changes through commit, allowing users to review the development of the project.
I learned the difference between Git and GitHub. Git is a version-control tool that tracks changes locally, while GitHub hosts repositories online.
I also learned that cloning creates a local copy of a repository, allowing me to work on project files directly from my laptop. Furthermore, as i continue working on GitHub online, using the - git pull- command on cmd will save my progress locally. 

## Challenges Encounterd

Asforementioned, the initial stages to understand GIt and create a repository was rather confusing for me. Fiddling around the GUI helped me understand what GitHub is about and how useful it can be.
had difficulty locating my repository because I was viewing the GitHub Copilot dashboard. After navigating to the repository's main page, I was able to create and edit the README file.
I faced an issue for pasting my screenshot on GITHub. Microsoft manner for sniping and pasting is entierly differernt for GIT.


## Reflection and Learning
Through this activity, I began to understand the difference between GitHub, repositories, README files, and commits.

This activity helped me understand how it can serve as a platform for recording my laboratory experiences and developing a portfolio of technical projects which can benefit me in the near future.

## Evidence

### Screenshot 1: GitHub Repository Creation
![GitHub Repository](screenshots/GitHub%20Repository%20Creation.png)

### Screenshot 2: README File
![README](screenshots/Readme.png)

### Screenshot 3: First Commit
![First Commit](screenshots/Commit%20Changes.png)

### Screenshot 4: Git Installation
![Install Git](screenshots/Install%20GIT.png)

### Screenshot 5: Git Clone
![Git Clone](screenshots/Git%20Clone.png)

### Screenshot 6: Git Version Verification
![Git Version](screenshots/GIT%20version.png)


# Day 1a : Introduction to Ubuntu Linux

## Lab Objectives
The ojective was to install a VM plus Unbuntu Linux in a virtual environment and become familiar with the Linux operating system. 

## Activites Performed
1) Download Ubuntu ISIO
2) Install VirtualBox and create a new virtual machine.
3) Configure VM settings
4) Mount ISO and install Ubuntu through guided installer

## Challenges Encountered
i didn't face much challenges from this part of the installation as I've created a Virtual Machine previously but the main challenge, I encountered during this lab was understanding the purpose of the Ubuntu ISO file. Initially, I was unsure why I needed to download an ISO file when I had already installed Oracle VirtualBox.
I later understood that VirtualBox provides the virtual hardware environment, whereas the Ubuntu ISO contains the files needed to install the operating system. 

## Observations
Virtualization: I observed that Oracle VirtualBox allowed me to install and run Ubuntu Linux within my Windows laptop without replacing my existing operating system.
Resource allocation: While creating the virtual machine, I noticed that I had to allocate hardware resources such as RAM, CPU cores and storage. This helped me recognize that a virtual machine uses resources from the physical computer.
ISO installation: I observed that the Ubuntu ISO file was used as the installation medium for the virtual machine, similar to how a bootable USB drive is used to install an operating system on a physical computer.
Operating system independence: After installing Ubuntu, I could operate Linux within VirtualBox while Windows continued running as my main operating system.
Virtual machine configuration: I noticed that VirtualBox provided settings to configure the virtual machine's hardware without physically modifying my laptop. Understanding in layman's term that an ISO is basically a digital installation DVD. It contains the installation files for Ubuntu. Hence the ISO is the boot content to "image" my virtual machine.

-Before installation: The ISO provides the Ubuntu installation files.
-During installation: Ubuntu is installed onto the VM's virtual hard disk.
-After installation: Ubuntu boots directly from the virtual hard disk.

## What I learned
To grasp the concept of Virtual Machine, i needed to know the skeleton behind this. The link between my physical laptop to Oracle VirtualBox to Ubuntu Virtual Machine. 
Think of VirtualBox as software that allows you to run another computer inside your existing computer.
- VirtualBox: Creates and runs virtual machines.
- Virtual Machine (VM): A simulated computer with its own allocated RAM, processors and storage.
- Ubuntu: The operating system installed inside the VM.
- ISO file: A virtual installation disc containing the Ubuntu installer.


## Evidence

### Screenshot 7: ISO Link
![ISO Link](screenshots/ISO%20link.png)

### Screenshot 8: General Config
![General Config](screenshots/General%20Config.png)

### Screenshot 9: Storage Configuration
![Storage Config](screenshots/Storage%20Config.png)

### Screenshot 10: System Config
![System Config](screenshots/System%20Config.png)



# Day 1a : Familiarity with Ubuntu Linux – Basic command line navigation and utilities.  

## Lab Objectives
The objective is to run basic Linux command and see the result of that command executed. 

## Activities Performed
1) Practice using `pwd`, `ls`, `cd`, `mkdir`, and `touch`. 
2) Understand directory structure (`/etc`, `/var`, `/home`). 
3) Use `man` to explore Linux manual pages.

## Challenges Faced

While running sudo apt install, i faced this error "404 Not Found"
Error: The repository 'http://sg.archive.ubuntu.com/ubuntu resolute Release' no longer has a Release file. I couldn't do anything about it. Sudo apt clean didn't manage solve the issue.
With the help of chatgpt and Stackflow forum, i got find out that a repository configuration problem. It may be pointing to an Ubuntu release that is no longer supported, or your repository settings may be incorrect.

i needed to edit the main repository http://sg.archive.ubuntu.com/ubuntu/ ---->  http://archive.ubuntu.com/ubuntu/
By running this command first - sudo nano /etc/apt/sources.list.d/ubuntu.sources
which will show me

Types: deb
URIs: http://sg.archive.ubuntu.com/ubuntu/
Suites: resolute resolute-updates resolute-backports
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg

## Observations

During this lab, I observed that Ubuntu allows users to navigate directories and manage files through the terminal without relying on a graphical interface.

Commands Practised:

pwd
ls
cd Documents
cd
mkdir LinuxLab
cd LinuxLab
touch notes.txt
ls
pwd

I observed that pwd displayed my current directory as /home/shobanchan, while ls listed the available files and folders. The cd command allowed me to navigate between directories, mkdir was used to create a folder, and touch was used to create an empty text file.

Additional Commands Covered – Linux File System:

cd /etc
pwd
ls

cd /var
pwd
ls

cd ~
pwd

man ls

I also observed that /home stores personal user files, /etc contains system configuration files, and /var/log commonly stores system and application logs. The man command provides documentation for Linux commands.

## What I learned

Through this lab, I learned how to navigate the Ubuntu file system using basic Linux commands such as pwd, ls and cd. I also learned how to create directories and files using mkdir and touch. Additionally, I gained a better understanding of the purpose of Linux directories such as /home, /etc and /var/log. Overall, this activity helped me become more familiar with the Linux terminal and understand how files and directories are managed without using a graphical interface.
