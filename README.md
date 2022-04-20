# Fedora KDE Tips!

## Made with Fedora KDE 35, but should apply to future versions provided they don't change much about the usual Fedora setup process. (Works on 36!)

**Enable RPMFusion:** You may check https://rpmfusion.org/Configuration if you're uncomfortable with the terminal, otherwise run

``sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm``

**Enable Flathub:** Since you're on KDE spin, if you want to enable it via discover go to Settings and click the button "Enable Flathub", otherwise run

``flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`` 

via the terminal.

**Additionnal Multimedia Codecs**

After enabling RPMFusion, run the commands below

```sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel```

```sudo dnf install lame\* --exclude=lame-devel```

```sudo dnf group upgrade --with-optional Multimedia``` 


**Got nvidia?**
After enabling RPMFusion, run 

``sudo dnf install akmod-nvidia  xorg-x11-drv-nvidia``

or if you have a Kelper GPU (600/700 series)

``sudo dnf install akmod-nvidia-470xx xorg-x11-drv-nvidia-470xx ``

Reboot.

**CUDA drivers for people who need them: (an end user usually wouldn't really need them, so don't worry about just skipping this)**

`sudo dnf install xorg-x11-drv-nvidia-cuda` 

**or if you want them for Kelper GPUs (600/700 series)**

``sudo dnf install xorg-x11-drv-nvidia-470xx-cuda``

NOTE: I don't use Nvidia, nor am I very well versed in Nvidia on Linux, but the above should work for *most* people. 

# Optional "debloating" steps:
The Fedora KDE spin is intentionally meant to ship with mostly *only* KDE software, and sometimes some of the stuff it ships is not needed by most, and is perfectly safe for removal.

**Remove ALL of the Akonadi suite** (includes KMail, Kontact, Korganiser): ``sudo dnf rm kf5-akonadi-*``
 
**Remove additional KDE/Fedora apps**: ``sudo dnf remove akregator kamoso mediawriter elisa-player kmag kgpg qt5-qdbusviewer kcharselect kcolorchooser dragon kmines kmahjongg kpat kruler kmousetool kmouth kolourpaint konversation krdc kfind libreoffice-*``

**Super duper optional:**

I am of the opinion that dnfdragora is hot garbage, and should not ship with KDE spin due to DNF's CLI interface (or even Discover) basically doing its job but better.

**Remove dnfdragora**: ``sudo dnf remove dnfdragora`` 


