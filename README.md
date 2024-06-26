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
<details>
  <summary>Compilers flags</summary>
  
  ### g++ accepts mostly the same options as gcc and vice versa
  
  > Test C code with many warnings enabled
  ```
  gcc -std=c17 -Wall -Wextra -Wwrite-strings -Wno-parentheses -Wpedantic -Warray-bounds  -Wstrict-prototypes -Wconversion
  ```
  > Test C++ code with g++
  ```
  g++ -pedantic -Wall -Wextra -Wcast-align -Wcast-qual -Wctor-dtor-privacy -Wdisabled-optimization -Wformat=2 -Winit-self -Wlogical-op -Wmissing-declarations       -Wmissing-include-dirs -Wnoexcept -Wold-style-cast -Woverloaded-virtual -Wredundant-decls -Wshadow -Wsign-conversion -Wsign-promo -Wstrict-null-sentinel           -Wstrict-overflow=5 -Wswitch-default -Wundef -Werror -Wno-unused
  ```
</details>

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
> Open project in vs code from terminal
```
code -r <path-to-working-directory>
```
> Open project when already inside
```
code -n
```
> Show list of packages to upgrade
```
apt list --upgradable
```

> Docker run kali container with volumes and remove after exit
```
docker run -ti --rm --mount src=kali-root,dst=/root --mount src=kali-postgres,dst=/var/lib/postgresql image_name
```
> Get sha256 of docker image (here pihole) with manifest and piping
```
docker manifest inspect --verbose pihole/pihole | jq -r '.[].SchemaV2Manifest.config.digest' | head -n 1
```

> Copy file into Docker container
```
docker cp file.ext container_id:/destination_file.ext
```

> Load and list packages
```
pacman -Syup
```

> Connect to RPI regardless of LAN addressing
```
ssh `whoami`@`arp -na | grep "e4:5f:01:12:ed:a9" | awk -F '[()]' '{print $2}'` -p 2137
```

> Get public IP from CLI (via Cloudflare DNS)
```
dig +short txt ch whoami.cloudflare @1.0.0.1
```
