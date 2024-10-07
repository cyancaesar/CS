### Module 13: User Administration

Linux is a multi-user operating system

**Objectives**:
- Create a user account
- Delete a user account
- Adding a user to a usergroups

##### Creating a user

```bash
sudo adduser 'user'
```

*sudo* (superuser do) is a command that allows users to run programs with the security privileges of another user, by default the superuser

##### Deleting and Disabling Account

Deleting:
```bash
sudo userdel -r 'user'
# -r to remove user's home directory
```

Disabling (by removing the password):
```bash
sudo passwd -l 'user'
```

##### Adding users to usergroups

Viewing the existing groups:
```bash
groupmod "<TAB><TAB>"
```

Add a user to a group:
```bash
sudo usermod -a -G GROUP USER
```

Check whether the user is in a group:
```bash
cat /etc/group
```

Remove a user from a group:
```bash
sudo deluser USER GROUP
```

##### Modifying users with usermod

```bash
# usermod

-c # username
-d # home_dir
-g # group
-G # grouplist -Ga to append
-s # shell
```

##### Creating group accounts

```bash
groupadd kings
groupadd -g 1325 jokers # group ID
```

Changing a group later:

```bash
groupmod -g 330 jockers
groupmod -n jacks jockers
```

##### Finger

*finger* command is used to procure information of the users on a Linux machine

```bash
finger # all users
finger 'user' # finger the 'user'
```

