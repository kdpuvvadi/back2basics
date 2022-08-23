---
title: Adding sudo user in Linux
date: 2022-08-22 10:14:15 +0530
categories: [Basics, Linux, User]
tags: [basics, linux, bash, user]
---

`Sudo` user is special user in the linux system. To grant administrative permissions, user has to have sudo permissions. Normally only `root` user have `sudo` access. To run any operation as `root` first we need to grant `sudo` permissions to the user.

## Adding user

To create or add a new user in the linux system, we'll use `adduser` command. Syntax as follows

```bash
useradd [options] USERNAME
```

Add user by running

```bash
sudo adduser USERNAME
```

> To add user with `adduser`, current user needs root permissions.
{: .prompt-tip }

> Replace `USERNAME` with desired username.
{: .prompt-tip }
To complete the setup enter details in the interactive shell. Sample output as bellow. `user1` is new user's username.

```shell
$ sudo adduser user1
Adding user `user1' ...
Adding new group `user1` (1001) ...
Adding new user `user1` (1001) with group `user1` ...
Creating home directory `/home/user1' ...
Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for user1
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n]
```

## Add user to SUDO

`usermod` is used to add user to `sudo` group. Syntax as follows

```shell
usermod -a -G sudo USERNAME
```

- `-G` is to add the given user to the said group.
- `-a` is to append.

Add `user1` to `sudo` group by running

```shell
sudo usermod -a -G user1
```

To test the permissions, switch to user `user1` by running.

```shell
su - user
```

Enter password when prompts.

Run following to view the current release info of the system

```shell
sudo cat /etc/os-release
```

if you see something like `user1 is not in the sudoers file.  This incident will be reported`, it means changes didn't take effect. Try logout and then login.

If the problem still persists, try running command again.

> `sudo` comes with lot of responsibility and gives admin permissions, please be carefull. It can break the system.
{: .prompt-tip }
