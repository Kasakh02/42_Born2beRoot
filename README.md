Born2BeRoot (Guide for Evaluation):
## VM (what it is and how it works)

- A virtual Machine is a program that functions as a virtual computer, with its own CPU, memory, network interface, and storage.
- VM allows you to have more than one operating system inside your machine. For example, I may be working on a Linux computer and have Windows installed using a VM. I can do everything I could be working on a typical Windows computer but on my Linux.

## Why Debian and not Rocky?

- Uses apt-get as its package manager
- Easily upgrades from one stable version to another
- Comes with user-friendly apps and GUI
- Has a vast amount of packages

[Image (CentOS vs Debian)](https://www.notion.so/Image-CentOS-vs-Debian-44c5e37d22c14a0ca994438f5aa49d66?pvs=21)

## Aptitude

It is a front-end to advanced packaging tool which adds a user interface to the functionality, thus allowing the user to interactively search for a package and install or remove it. 

## Apt

- Stands for Advanced Packaging Tool. It’s a free and open source. Designed to handle package management and software installation and removal.
- It is a whole command line with no GUI.

Summing up, the main difference is kinda just a visual thing. Both Apt and Aptitude do the same thing…

## APPArmor

It is a Mandatory Access Control (MAC) system which verifies and gives permissions to apps, files, etc…

## Check if UFW and SSH are enabled

**Verify ssh service:** `sudo systemctl status ssh`

**Check if ufw is enabled:** `sudo ufw status`

## User belongs to *sudo* and *user42* groups

`getent group sudo`

`getent group user42`

## Check rules

**Create new user:** `sudo adduser “user”`

**Set password to new user:** `sudo passwd “user”`

**Create new group and assign “user”:** 

- `sudo groupadd “evaluating”`

- `sudo usermod -a -G "evaluating" "user”`

- `getnet group “evaluating”`

 

- **Show password policy:**

`cd /etc && vim login.defs`

`cd /etc/pam.d && sudo vim common-password`

- **Advantages of password policy:**

Password with better security because it has to have a specific number of characters, upper and lower letters, numbers, special characters, etc…

## Hostname and partitions

Check and change hostname:

`hostname`

`sudo hostname “new_hostname”`

**Check partitions:** `lsblk`

**LVM:** logical volume management is a form of storage virtualization. It is a more flexible approach to managing disk storage space. The goal of LVM is to facilitate multiple users' sometimes conflicting storage needs.

## SUDO

Check that sudo is installed: `sudo`

`sudo usermod -aG sudo “user”`

**What is sudo:** allows a system administrator to delegate authority to give certain users the ability to run some or all commands as root. Allows to temporarily (during one command) access root permissions.

**Show sudo rules:** `cd /etc/sudoers.d && sudo visudo`

**Verify that** `/var/log/sudo` exists and has at least one file. Run `sudo` and see if file changes.

## UFW

**What is UFW:** uncomplicated firewall is a simple firewall and easy to use and has a command-line interface.

**List active rules:** `ufw status`

**Add new rule (open port 8080):** `sudo ufw allow 4242/tcp`

**Delete rule:** 

`sudo ufw status numbered`

`sudo ufw delete NUM`

## SSH

**What is SSH:** secure shell is a network communication protocol that enables two computers to communicate and share data. The communication between the two computers is encrypted.

**Verify it only uses port 4242:** `cd /etc/ssh && vim sshd_config`

## Script monitoring

**What is cron:** it is like an agenda, that has various commands to be executed in a previously set time.
