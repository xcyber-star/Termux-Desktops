# 📚 Index

## PROOT-DISTRO (🍥 DEBIAN)
* 🏁 [First steps](#first-steps)
* ⚙️ [Installing Desktops](#installing-desktops)
* 💻 [Running the Desktops to use them with Termux X11](#running-desktops)
* ⬇️ [Download scripts to run the desktops](#easy-download)
* 🎨 [Customizations - Themes](#customizations)

<br>

---  
---  

<br>

## 🏁 First steps <a name=first-steps></a>
We are going to use Termux and Termux X11 in order to have a full Linux Desktop in our Android devices. 





<details>
<summary><strong> [Commands] How to install a Linux Distro on Termux with proot-distro (No Root)</strong></summary>

You can check the video described in the First Steps section. The written steps are the following ones: 

1. Open Termux
2. Install proot-distro  
```
pkg update
pkg install proot-distro
```
3. Install Debian (or the distor you prefer)
```
proot-distro install debian
```
4 Log in to the distro 
```
proot-distro login debian
```
</details>

<details>
<summary><strong>[Commands ]Create an user with sudo privileges</summary></strong>

The steps are described in the video linked in the previous point. 

1. Install needed packages
```
apt update -y
apt install sudo nano adduser -y
```
2. Create an user
```
adduser roygoldfx
```
3. Give the user sudo privileges
```
nano /etc/sudoers

# Add the following line to the file
roygoldfx ALL=(ALL:ALL) ALL
```
4. Check you can execute sudo commands (it should return `root`)
```
sudo whoami 
```  

</details>  

---  
<br>

# ⚙️ Installing Desktops <a name=installing-desktops></a> 

I have installed different desktops, if you want me to test any other just leave a comment in any video and I will check it: 




```
# Commands: 
proot-distro login debian --user roygoldfx
```
```
sudo apt install xfce4
```

* [How to install LXDE]
```
# Commands: 
proot-distro login debian --user roygoldfx
```
```
sudo apt install lxde
```

* [ How to install Cinnamon]
```
# Commands: 
proot-distro login debian --user roygoldfx
```
```
sudo apt install cinnamon -y
```

* [How to install GNOME]
```
# Commands: 
proot-distro login debian --user roygoldfx
```
```
sudo apt install dbus-x11 nano gnome gnome-shell gnome-terminal gnome-tweaks gnome-software nautilus gnome-shell-extension-manager gedit tigervnc-tools gnupg2 -y
```
```
for file in $(find /usr -type f -iname "*login1*"); do rm -rf $file
done
```

* [How to install KDE Plasma]- Not recommended due to performance issues (KDE Plasma requires more resources)
```
# Commands: 
proot-distro login debian --user roygoldfx
```
```
sudo apt install kde-plasma-desktop
```

---  
<br>

## 💻 Running the Desktops for use with Termux X11 <a name=running-desktops></a>
All the scripts in this repository are prepared to run the different Desktops with audio in an easy way. 

First you need to install the following packages in Termux: 
```
pkg update
pkg install x11-repo
pkg install termux-x11-nightly
pkg install pulseaudio
```

Then, you just need to download the script corresponding to the Desktop you have installaded, give it permissions to execute it and run it (in Termux, not in proot-distro): 
```
# Download the script to Termux
chmod +x startxfce4_debian.sh
./startxfce4_debian.sh
```

---  
<br>

## ⬇️ Download scripts easily: <a name=easy-download></a> 

> [!NOTE]  
> By default this script works with the user "roygoldfx". If you create a user with a different name in proot-distro, please change where it says "roygoldfx" inside the scripts.

* startgnome_debian.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_debian/startgnome_debian.sh
```

* startxfce4_debian.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_debian/startxfce4_debian.sh
```

* startlxde_debian.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_debian/startlxde_debian.sh
```

* startcinnamon_debian.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_debian/startcinnamon_debian.sh
```

* startkde_debian.sh
```
wget https://raw.githubusercontent.com/xcyber-star/Termux-Desktops/main/scripts/proot_debian/startkde_debian.sh
```
---  
<br>

## 🎨 Customizations <a name=customizations></a>



* How to install nerd fonts (this allows you to have icons in the terminal):
```
bash -c  "$(curl -fsSL https://raw.githubusercontent.com/officialrajdeepsingh/nerd-fonts-installer/main/install.sh)"
```

* Whisker menu and MugShot (to improve default desktop default menu) 

```
sudo apt install xfce4-whiskermenu-plugin
sudo apt install mugshot
```

* Install icon themes: 
```
apt search icon-theme
sudo apt install papirus-icon-theme moka-icon-theme
```

* Install GTK themes (system themes)
```
apt search gtk-themes
sudo apt install numix-gtk-theme greybird-gtk-theme
```

* Install alternative dock (bottom panel)
```
sudo apt install plank
plank --preferences
```

* Install Conky (desktop widgets)
```
sudo apt install conky-all
