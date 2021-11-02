# kumk
simple Ubuntu Mainline Kernel manager...

## description
Simple CLI tool for install ([Ubuntu Mainline Kernel](https://wiki.ubuntu.com/Kernel/MainlineBuilds)) or purge (any) kernel

- on system with lower libc6 version than need installed linux-header*arch package, install using workaround  
this is about extracting binaries from last(5.11.16) package supporting libc6 2.31 and replace it in installed kernel  
with faking minimal libc6 version for installed package in dpkg status file...

- if Sicherboot is detected, after installing kernel he ask if set it as default...

## installing
simply copy to any in $PATH directory, ex.
```
sudo cp -a kumk /usr/local/bin
```
or without "installing", run from current directory where kumk file is:
```
sudo ./kumk
```

## usage
```
kumk [s|l|i|d|n|p|b] [ver|latest|latest-rc|norc] <norc>
  s, show         - show avaiable versions
  l, list         - show installed

  i, install      - download and install
  d, download     - download only
  n, only_install - install only
  p, purge        - purge kernel
  b, sicherboot - set default for sicherboot

  ver       - specify version for "i, d, n, p, b" or filter for "s, l"
  latest    - auto detect latest stable version for "i"
  latest-rc - auto detect latest rc version for "i"
  norc      - used only for "s" to disable show rc version
```
