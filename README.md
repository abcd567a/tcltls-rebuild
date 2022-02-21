# tcltls FlightAware rebuild

This is a rebuild of the upstream Debian/Raspbian tcl-tls package,
building with `--enable-ssl-fastpath` to work around an upstream
bug that affects PiAware.

The upstream bug is reported here:
https://core.tcl-lang.org/tcltls/tktview?name=6dd5588df6

This repository also includes infrastructure for backport builds
for Buster / stretch / jessie

The package is otherwise the same as the Debian 1.7.22-1 package.


## How to Build & Install
```
sudo apt install git wget devscripts debhelper libssl-dev tcl-dev chrpath 

git clone https://github.com/abcd567a/tcltls-rebuild  

```
</br>

**For Bullseye:**
```
cd tcltls-rebuild 
sudo bash prepare-build.sh bullseye  
cd package-bullseye 
sudo dpkg-buildpackage -b --no-sign  
cd ../
sudo dpkg -i tcl-tls_1.7.22-1+fa1_*.deb
```
</br>

**For Buster:** </br>

```
cd tcltls-rebuild 
sudo bash prepare-build.sh buster  
cd package-buster 
sudo dpkg-buildpackage -b --no-sign  
cd ../
sudo dpkg -i tcl-tls_1.7.22-1+fa1~bpo10+1_*.deb

```
