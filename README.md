# General Fedora Tips.

**Enable RPMFusion:** https://rpmfusion.org/Configuration / 

``sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm``

**Enable Flathub:** You're on KDE spin, if you want to enable it via discover, go to Settings and click the button "Enable Flathub", or

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

Reboot.

Cuda drivers for people who need them: (an end user usually wouldn't really need them, so don't worry about just skipping this)

`sudo dnf install xorg-x11-drv-nvidia-cuda` 

NOTE: I don't use Nvidia, nor am I very well versed in Nvidia on Linux, but the above should work for *most* people with 900+ series cards.

# Optional "debloating" steps:* 
The Fedora KDE spin is intentionally meant to ship with mostly *only* KDE software, and sometimes, some of the stuff it ships are not needed by most, and are perfectly safe for removal.

**Remove ALL of the Akonadi suite** (includes KMail, Kontact, Korganiser): ``sudo dnf rm kf5-akonadi-*``
 
**Remove additional KDE/Fedora apps**: ``sudo dnf remove akregator kamoso mediawriter elisa-player kmag kgpg qt5-qdbusviewer kcharselect kcolorchooser dragon kmines kmahjongg kpat kruler kwalletmanager kmousetool kmouth kolourpaint libreoffice-*``

Super duper optional:

I am of the opinion that dnfdragora is hot garbage, and should not ship with KDE spin due to DNF's CLI interface (or even Discover.) basically doing its job but better.

**Remove dnfdragora**: ``sudo dnf remove dnf dragora`` 


