# General Fedora Tips.

**Enable RPMFusion:** https://rpmfusion.org/Configuration / 

``sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm``

**Enable Flathub:** You're on KDE spin, if you want to enable it via discover, go to Settings and click the button "Enable Flathub", or

``flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`` 
via the terminal.

**Got nvidia?**
After enabling RPMFusion, run 

``sudo dnf install akmod-nvidia  xorg-x11-drv-nvidia-cuda``

Reboot.

NOTE: I don't use Nvidia, nor am I very well versed in Nvidia on Linux, but the above should work for *most* people with 900+ series cards.

# Optional "debloating" steps:* 
The Fedora KDE spin is intentionally meant to ship with mostly *only* KDE software, and sometimes, some of the stuff it ships are not needed by most, and are perfectly safe for removal.

**Remove ALL of the Akonadi suite** (includes KMail, Kontact, Korganiser): ``sudo dnf rm kf5-akonadi-*``
Remove Dragon Media Player: ``sudo dnf rm dragon`` (I prefer ``mpv``) 
Remove Elisa: ``sudo dnf rm Elisa``

Will be updated in a bit, but everything in general tips should be good.
