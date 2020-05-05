#### Compiling from Source
```
src : this folder is where the source code is located
install gcc
bash configure : to create the makefile
make
sudo make install : to install what was compiled
after makefile is made and need to make changes the command below can be ran
make && sudo make install
```

#### Software Repositories
```
https://help.ubuntu.com/community/Repositories/Ubuntu : Repositories
https://packages.ubuntu.com/ : Packages
lsb_release - a : will tell you your distributions codename
```

#### Download Source Code
````
Undo the # in the /etc/apt/sources.list file
sudo apt install dpkg-dev
sudo apt source <package name>
````

#### Uninstalling Software
````
sudo apt purge <package name> : to remove the package and configuration files
sudo apt autoremove : remove any dependencies
````