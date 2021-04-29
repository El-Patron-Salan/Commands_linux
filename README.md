# Commands_linux
**Just a bunch of commands that I usually forget**    
> Check version of distro and kernel
```
hostnamectl
```
> More detailed info about distro
```
cat /etc/os-release
```
> Basic info
```
lsb_release -a
```
> One liner for ROT 13
```
echo "smth_to_translate" | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```
> Test C code with many warnings enabled
```
gcc -std=c17 -Wall -Wextra -Wwrite-strings -Wno-parentheses -Wpedantic -Warray-bounds  -Wstrict-prototypes -Wconversion
```
> Show running process of files in range (TCP:1-1024)
```
lsof -i TCP:1-1024
```
> Show all groups
```
getent group
```
> Show groups that specific user belongs to
```
getent group | grep user_name | awk -F: '{ print $1 }'
```
```
grep user_name /etc/group | awk -F: '{ print $1 }'
```
> Get all sudo or super users
```
grep '^sudo:.*$' /etc/group | cut -d: -f4
```
<details>
  <summary>Just in case Ubuntu crashed</summary>
 
  ## step by step  
  ```
  sudo rm /var/lib/apt/lists/lock
  ```
  ```
  sudo rm /var/lib/dpkg/lock
  ```
  ```
  sudo rm /var/lib/dpkg/lock-frontend
  ```
  ```
  sudo dpkg --configure -a
  ```
  ```
  sudo apt clean
  ```
  ```
  sudo apt update --fix-missing
  ```
  ```
  sudo apt install -f
  ```
  ```
  sudo dpkg --configure -a
  ```
  ```
  sudo apt upgrade
  ```
  ```
  sudo apt dist-upgrade
  ```
  ```
  sudo reboot
  ```
</details>

> Show partition table
```
parted -l
```
> Remove non empty directory (v for view)
```
rm -vrf dir_name
```
> Restore given directory in ~
```
vim ~/.config/user-dirs.dirs
XDG_GIVEN DIRECTORY_DIR="$HOME/Given_directory"
```
> Change background
```
gsettings set org.gnome.desktop.background picture-uri file:////usr/share/backgrounds/[picture]
```
