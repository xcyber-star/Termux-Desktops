# 📚 Index



## PROOT-DISTRO (🌌 VOID)
* 🏁 [First steps](#first-steps-void-proot)
* 💻 [How to install XFCE4 Desktop](#xfce-void)
* ⬇️ [Download scripts to run the desktops](#easy-download-void-proot)

---

## 🏁 First steps <a name=first-steps-void-proot></a>

* First you need to install the following packages in Termux: 
```
pkg update
pkg install x11-repo
pkg install termux-x11-nightly
pkg install pulseaudio
pkg install proot-distro
```
* Then install Void proot: 
```
proot-distro install void
```

---  
<br>

## 💻 How to install XFCE4 Desktop <a name=xfce-void></a>

* Update and upgrade the default packages: 
```
xbps-install -u xbps
xbps-install -Suv
```

* Install some basic packages to check that everything is running well: 
```
 xbps-install nano vim net-tools sudo git
```

* Install XFCE4 packages (we need to install LXDE to install some fonts needed by XFCE4)
```
xbps-install lxde xfce4 xfce4-terminal
```

* Create a new user and give it sudo privileges: 
```
useradd roygoldfx
passwd 123456

nano /etc/sudoers

# Add the following line to the sudoers file
roygoldfx All=(ALL:ALL) ALL
```

* If you want to install Chromium or Firefox: 
```
xbps-install chromium firefox
```

* If you want to install Nerd Fonts (1,5 GB): 
```
xbps-install nerd-fonts
```


---  
<br>

## ⬇️ Download scripts to run the desktops <a name=easy-download-void-proot></a>

* startxfce4_void.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_void/startxfce4_void.sh
chmod +x startxfce4_void.sh
./startxfce4_void.sh
```
