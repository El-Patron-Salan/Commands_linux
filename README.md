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
