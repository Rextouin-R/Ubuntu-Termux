## PROOT-DISTRO (🟠 UBUNTU)
* [Membuat data username]
* [Membuat passwd username]
* [Memberi akses root pada username]
<br>

---  
---  

<br>

## Langkah pertama <a name=first-steps-ubuntu-proot></a>

> [!NOTE]  
> Semua perintah harus di jalankan dengan benar [Perhatikan]().

Package yang perlu kalian install di Termux: 
```
termux-setup-storage 
pkg update
pkg install x11-repo
pkg install root-repo
pkg install proot-distro
```

Penginstalan dan lagin Ubuntu: 
```
proot-distro list
proot-distro install ubuntu
proot-distro login ubuntu
```

Update dan install package untuk membuat Userbaru: 
```
apt update 
apt upgrade

apt install sudo nano
apt install adduser  
```

---  
<br>

## Langkah ke dua <a name=easy-download-ubuntu-proot></a> 

#### * Membuat data User:
```
adduser nama kalian
```
Bagian `New password:` isi password kalian

Bagian `Retyoe new password:` masukan lagi password kalian

Bagian `Full Name []` (enter)

Bagian `Room Number []` (enter)

Bagian `Work Phone []` (enter)

Bagian `Home Phone []` (enter)

Bagian `Other []` (enter)

Bagian `Is the information correct? [Y/n]` (y) lalu (enter)

#### * Mengedit bagian data:
```
nano /etc/sudoers
```
Edit dan isi bagian data, contoh seperti di bawah ini
```
# User privilege specification
root    ALL=(ALL:ALL) ALL
nama kalian ALL=(ALL:ALL) ALL
# Members of the admin group may gain root privileges
%admin ALL=(ALL) ALL
nama kalian ALL=(ALL) ALL
# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL
nama kalian ALL=(ALL:ALL) ALL
# See sudoers(5) for more information on "@include" directives:
```
Save mengunakan perintah `CTRL+x+y` (enter)

#### * Login menggunakan user kalian:
```
su - username kalian
```
```
whoami
```
```
sudo whoami
```
Lalu masukan password username kalian, setelah masuk silahkan dari TERMUX
```
exit
```
```
exit
```
#### * Perintah untuk login username:
```
root-distro login ubuntu --user (Username kalian)
```

---
<br>

# ⚙️ Installing Desktops <a name=installing-desktops-ubuntu-proot></a> 

I have use the following [post](https://ivonblog.com/en-us/posts/termux-proot-distro-ubuntu/) from Ivon's blog as a reference for some steps. 

<br>

<details>
<summary><strong> GNOME </strong></summary>

<br>

> [!NOTE]  
> All the process is described in more detail in this [video](https://www.youtube.com/watch?v=_vxhzSG2zVQ).

<br>


```
# Commands: 
proot-distro login ubuntu --user droidmaster
```
```
sudo apt install dbus-x11 ubuntu-desktop -y
```
Run this command after it finishes: 
```
for file in $(find /usr -type f -iname "*login1*"); do rm -rf $file
done
```
Disable snapd as it doesn't work on Termux
```
cat <<EOF | sudo tee /etc/apt/preferences.d/nosnap.pref
# To prevent repository packages from triggering the installation of Snap,
# this file forbids snapd from being installed by APT.
# For more information: https://linuxmint-user-guide.readthedocs.io/en/latest/snap.html
Package: snapd
Pin: release a=*
Pin-Priority: -10
EOF
```

Install firefox: 
```
sudo add-apt-repository ppa:mozillateam/ppa
sudo apt-get update
sudo apt-get install firefox-esr
```

Now you can run Ubuntu with GNOME UI from the script I left in the `Download scripts easily` section: 
```
chmod +x startgnome_ubuntu.sh
./startgnome_ubuntu.sh
```
</details>  

<br>

<details>
<summary><strong> Other desktosp (XFCE4, Mate, LXDE, etc) </strong></summary>
<br>

Follow the same [installation steps](https://github.com/LinuxDroidMaster/Termux-Desktops/blob/main/Documentation/proot/debian_proot.md#installing-desktops) as for Debian.

</details>  

---  
  
