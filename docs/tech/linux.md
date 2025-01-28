# Linux
```query
children:.
```
---

Linux-based operating systems are the most common choice for servers for a number of reasons, including it being open source, flexible, and lightweight.

This page contains a number of learnings, tips, and tricks for Ubuntu specifically.

## SSH
Secure Shell (SSH) is the standard way to securely connect to a server over an unsecured network. There are two main ways to require authentication on ssh connections:

1. Passwords
2. SSH keys

If `PasswordAuthentication` is set to true in `/etc/ssh/sshd_config`, then users can log into ssh users their account passowrds.

If not, then a user can only log in using SSH keys, which are a public-private key pairing. Your public key must be a line in the file `~/.ssh/authorized_keys` on the server, and your private key must be in your own `~/.ssh` folder. Note that on windows, `~/` is generally equivalent to `%HOME%/`.

## Linux Filesystem

### Linux Folder Structure
The linux folder structure is not super rigid, but there are some guidelines to follow when using them. Below includes a table of the folders that can be meddled with:

| Folder | Description |
| --- | --- |
| `/home/<user>` | This stores the user directories for `user`. This should not contain anything that affects the general function of the server. It should only contain things that `user` decides to put in there for their own use of the server. |
| `/usr/local` | This stores binaries, configurations, scripts, and source code for locally written and installed software. |
| `/opt` | This stores binaries, configurations, and scripts for self-contained static external packages. |
| `/etc/opt` | This stores host specific configuration for the packages in `/opt` |
| `/srv` | This stores the data for the services provided by the server. |
| `/var` | This stores variable data files such as logs. Commonly, `/var/www` is used for generated web files. |
| `/tmp` | This stores temporary files that can be deleted on reboot. |

Files in any other folders should only be used or edited if need be, never added to manually. Important software packages such as NGINX that see themselves as too cool for `/opt` may install in other places such as `/bin` or `/sbin`, with configuration files in `/etc`.

Source html, css, and javascript files for a website should go in `/srv`, and their generated web files should go in `/var/www`.

### Linux File Permissions
#### Viewing File Permissions
Using the command `ls` will list all of the files and folders of the current folder you're in, with some useful options:

| Flag | Effect |
| --- | --- |
| `-l` | Uses the long listing format, detailing: `permissions num-hardlinks file-owner file-group file-size modification-time filename` |
| `-d` | Instead of listing the files and folders in the current directory, the command will list the current directory itself only |
| `-h` | All file sizes are now human readable |
| `-a` | All files and folders are shown, including those starting with a `.` |

This way, we can view the permissions of a file. They look something like this:

`drwxr-x--x`

* Character **1** is a `d` if the file is a directory, `-` if not.
* Characters **2-4** are the read `r`, write `w`, and execute `x` permissions for the owner of the file. If a letter is present, the owner has that permission. If instead there is a `-`, the owner does not have that permission.
* Characters **5-7** are the read `r`, write `w`, and execute `x` permissions for the group of the file. If a letter is present, users of the group have that permission. If instead there is a `-`, users of the group do not have that permission.
* Characters **8-10** are the read `r`, write `w`, and execute `x` permissions for any other users. If a letter is present, other users have that permission. If instead there is a `-`, other users do not have that permission.

#### Changing file permissions
The file permissions of a file or folder can be changed using the `chmod` command, . The permmissions are set to a number, where each digit in binary represents the permissions.

For example, `chmod 764 filename` would set the permissions of `filename` to 764 = 111 101 100 = rwxr-xr--.

The owner and group of a file or folder can be changed using `chown` command.

## Services
System services are services that run whenever the server is running, while user services only run when that user is logged in. To see all running services run `sudo systemctl list-units --type=service --state=running`.

See [here](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units) for more.

## UFW
Use `sudo ufw status` for the firewall status.

See [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu#step-3-allowing-ssh-connections) for more.
