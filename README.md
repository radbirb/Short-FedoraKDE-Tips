# Fedora KDE Tips!

## Made with Fedora KDE 35, but should apply to future versions provided they don't change much about the usual Fedora setup process. (Works on 36!)

**Let's start off with the obvious.**

``sudo dnf update``

Update your system first before proceeding further.

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

# Optional "debloating" steps
The Fedora KDE spin is intentionally meant to ship with mostly *only* KDE software, and sometimes some of the stuff it ships is not needed by most, and is perfectly safe for removal.

One of the major pain points for most is the inclusion of the Akonadi suite (Kmail, Kontact, Korganiser, etc), in the next section are commands listed to either remove the Akonadi suite itself while keeping the necessary Akonadi libaries for programs like KGpg or remove all Akonadi libraries and its programs alongside additional KDE apps. 

Alternatively, you can remove all Akonadi programs/libraries separately with a separate command shown below.

``sudo dnf rm kf5-akonadi-*``

## The two ways of "debloating" Fedora KDE

**Full additional KDE/Fedora program removal (includes "DeAkonadisation")**: 

``sudo dnf remove akregator kamoso mediawriter elisa-player kmag kgpg qt5-qdbusviewer kcharselect kcolorchooser dragon kmines kmahjongg kpat kruler kmousetool kmouth kolourpaint konversation krdc kfind kaddressbook kmail kontact korganizer ktnef libreoffice-* kf5-akonadi-*``

**Additional KDE/Fedora app removal without removing necessary Akonadi libraries (No full "DeAkonadisation", only to keep stuff like KGpg, which some may find useful, but is not needed)** 

``sudo dnf remove akregator kamoso mediawriter elisa-player kmag qt5-qdbusviewer kcharselect kcolorchooser dragon kmines kmahjongg kpat kruler kmousetool kmouth kolourpaint konversation krdc kfind kaddressbook kmail kontact korganizer ktnef libreoffice-*``
 
You may remove ``libreoffice-*`` or anything else (if you do "DeAkonadisation", expect apps that depend on it to install Aknoadi libraries back) from the commands above if you would like to keep it.

**Results**

All in all, this brings down the default package count from around 1700-1800~ to around 1600~.

**Notice!**

Do not worry about ``dnf`` spitting out ``cannot remove '*insertprogramhere': No such file or directory``, it usually means you either removed the package already, misspelled the package name if you manually typed the commands, or you, for some reason, don't have that package already, eitherway, it'll proceed with the command just fine, and uninstall what it finds.

### Super duper optional stuff

I am of the opinion that dnfdragora is *hot garbage*, and should not ship with KDE spin due to DNF's CLI interface (or even Discover) basically doing its job but better.

**Remove dnfdragora**: 

``sudo dnf remove dnfdragora`` 

# Enjoy your Fedora! <3
