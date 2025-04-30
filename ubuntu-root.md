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

Penginstalan dan login Ubuntu: 
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
adduser (username kalian)
```
Bagian `New password:` isi password kalian

Bagian `Retyoe new password:` masukan lagi password kalian

Bagian `Full Name []` (enter)

Bagian `Room Number []` (enter)

Bagian `Work Phone []` (enter)

Bagian `Home Phone []` (enter)

Bagian `Other []` (enter)

Bagian `Is the information correct? [Y/n]` (y) lalu (enter)

## Langkah ke tiga mengedit bagian data:
```
nano /etc/sudoers
```
Edit dan isi bagian data, contoh seperti di bawah ini
```
# User privilege specification
root    ALL=(ALL:ALL) ALL
Username kalian ALL=(ALL:ALL) ALL
# Members of the admin group may gain root privileges
%admin ALL=(ALL) ALL
Username kalian ALL=(ALL) ALL
# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL
Username kalian ALL=(ALL:ALL) ALL
# See sudoers(5) for more information on "@include" directives:
```
Save mengunakan perintah `CTRL+x+y` (enter)

#### * Login menggunakan user kalian:
```
su - (username kalian)
```
```
whoami
```
```
sudo whoami
```
* Lalu masukan password username kalian, setelah masuk silahkan keluar dari TERMUX
```
exit
```
```
exit
```
#### * Perintah untuk login Username dan install package terakhir:
```
proot-distro login ubuntu --user (Username kalian)
```
```
sudo apt install dbus-x11 ubuntu-desktop -y
```

---
<br>

# 🙏 Terima kasih banyak <a name=installing-desktops-ubuntu-proot></a> 
