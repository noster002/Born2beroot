# Born2beroot
42 School - Level01

A Linux server developed in a virtual machine with some safety requirements

As it is done in a virtual machine, there is for evaluation purposes only the signature of the machine's virtual disk present.

## Requirements

+ Latest stable version of [Debian](https://www.debian.org) (*Debian 10 Buster* at the time of writing)
+ 2 encrypted partitions using LVM
+ SSH service on port 4242 (no root access)
+ UFW firewall (only port 4242 open)
+ Modify hostname
+ Install and configure sudo:
  + Maximum 3 attempts for incorrect passwords
  + Custom message on error
  + Archive sudo actions in /var/log/sudo/ folder
  + Enable TTY mode
  + Restrict paths accessible by sudo
+ Create user
+ Add user to groups (also sudo)
+ Password policy:
  + Expires every 30 days
  + Minimum 2 days in between modification
  + Warning 7 days before expiration
  + Minimum 10 characters long
  + Minimum 1 uppercase letter
  + Minimum 1 lowercase letter
  + Minimum 1 number
  + Cannot contain more than 3 consecutive identical characters
  + Must not include username
  + Minimum 7 characters that where not part of the former password (only non-root passwords)
+ Monitoring.sh script to display some data at server startup and every 10 minutes (cron)
  + The architecture of your operating system and its kernel version
  + The number of physical processors
  + The number of virtual processors
  + The current available RAM on your server and its utilization rate as a percentage
  + The current available memory on your server and its utilization rate as a percentage
  + The current utilization rate of your processors as a percentage
  + The date and time of the last reboot
  + Whether LVM is active or not
  + The number of active connections
  + The number of users using the server
  + The IPv4 address of your server and its MAC (Media Access Control) address
  + The number of commands executed with the sudo program
