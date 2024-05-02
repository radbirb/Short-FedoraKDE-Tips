# NOTICE: THIS GUIDE SHOULD NOT BE USED ANYMORE! Read below for more info and updates on the general state of KDE Spin with regards to this guide.

## This guide will be archived. Some parts of this will still obviously work, but don't expect it to. I will link to upstream documentation for certain parts of this guide to direct anyone who'd need it now.

## Anyways, what's up with Fedora KDE?!

This guide was originally written on F35KDE, where I originally started using Fedora, and since then, I think the spin has generally gotten a lot better! to the point I think Fedora KDE stands neck and neck with Workstation's GNOME in regards to how well integrated it is, and I mean, it's so well made now that someone with a loud enough voice in the Fedora community thought it was so good that [it was unironically worth replacing the default desktop in Workstation for](https://fedoraproject.org/wiki/Changes/FedoraPlasmaWorkstation)... need I say more? (though obviously that proposal isn't happening as is, hopefully the KDE spin does get promoted to an edition of some kind though!)

Things may not look so different in the pre-installed package lists now, but the general experience of the Fedora KDE spin has gotten a lot better since F35/36, IBus doesn't nag you anymore because of Plasma Wayland, You can upgrade major Fedora versions through Discover, [dnfdragora is no longer shipped (huzzah!)](https://pagure.io/fedora-kde/SIG/issue/206) and soon, [you'll be able to enable third party repositories through Plasma Welcome Centre](https://invent.kde.org/teams/vdg/issues/-/issues/46) (in Plasma 6.1 and F41), and many major KDE contributors themselves use Fedora KDE which in turn has fostered a really healthy relationship between KDE itself and Fedora, especially nowadays.

I myself will continue using Fedora KDE as my main Plasma distro, and I still fullheartedly recommend it to anyone looking for a great Plasma experience :)

## Is Fedora KDE still bloated?

Nowadays? I honestly don't feel that it is, even though the package count still seems similar now from back then, it's pretty much shipping the KDE equivalents to apps you'd find in Fedora Workstation. I've began using a lot of the preincluded apps more aswell, moving aside stuff I still uninstall like the Akonadi suite (I'm mostly waiting on the future Merkuro suite to stablise), my Fedora KDE installs remain pretty stock. 

P.S. I've also ventured on to check out OpenSUSE Tumbleweed KDE in the meantime... and frankly, the ""bloat"" often brought up against Fedora KDE is just as existent in Tumbleweed, if not harder to uninstall due to the UX mess that is patterns. I bring up Tumbleweed as it's often championed as "the KDE distro". (it's not, and any openSUSE contributor will tell you that it's not, but that's another topic for another time.)

## I still want to "debloat" Fedora KDE!

Feel free to! you can use the commands here as a sort of reference, but keep in mind that packages names will certainly have changed since back then, and of course, some apps aren't shipped anymore due to them getting abandoned or not surviving the transition to Qt6. Dnf is still a fantastic package manager interface wise and will make things incredibly easy for you to find package names and such. (`dnf search` *app* and then `rpm -q` *packagename* to check if installed)

Alternatively, you may want to check out [Fedora Everything](https://fedoraproject.org/everything/download/), Fedora's Netinstall image, you can get a Fedora KDE install that way and remove any of the app groups you may not want. (ie. Akonadi, Games, etc)

and lastly, if you're willing to learn a new way to use Desktop Linux, Fedora KDE's [atomic equivalent, Kinoite](https://fedoraproject.org/atomic-desktops/kinoite/), is pretty minimal out of the box but some KDE apps were added as flatpaks in F40, though since they're flatpaks, they're very easy to uninstall yourself graphically through Discover. 

## Upstream Documentation for parts of this guide

Enabling RPMFusion: https://rpmfusion.org/Configuration

Installing Nvidia Drivers: https://rpmfusion.org/Howto/NVIDIA?highlight=%28%5CbCategoryHowto%5Cb%29#Current_GeForce.2FQuadro.2FTesla - Please take note of the warning there! it'll save you a scare :) 

Installing Nvidia Drivers (on Kinoite/Atomic KDE): https://docs.fedoraproject.org/en-US/fedora-kinoite/troubleshooting/#_using_nvidia_drivers

Installing Multimedia Codecs: https://docs.fedoraproject.org/en-US/quick-docs/installing-plugins-for-playing-movies-and-music/ and https://rpmfusion.org/Howto/Multimedia (You only really need to swap ffmpeg-free for full ffmpeg, you can also follow the Hardware Accelerated Codecs part, but if you're on a recent enough Intel GPU, it may not be entirely needed.)

Flathub can be enabled through Discover (and will be automatically enabled if you choose to enable third party repositories in F41), but you can still enable Flathub manually by following their guide: https://flathub.org/setup/Fedora

P.S. Nvidia Wayland on Plasma has gotten FAR better since this guide was written, especially on Plasma 6, and expect it get a lot less weird with Xwayland apps in June with Plasma 6.1 landing explicit sync support (which Fedora 40 KDE will most certainly get.) alongside Nvidia releasing the beta version of 555 in May. Read more here: https://zamundaaa.github.io/wayland/2024/04/05/explicit-sync.html

## An additional tip.

As you may know, Fedora 40 KDE doesn't ship the X11 session anymore, and while I am in full support of this decision, I do recognise the fact that some may have certain usecases where they simply can't use Wayland (mainly accessibility for now), so I do want to mention how to install the X11 session just in case someone stumbles upon this ancient guide and needs it.

### WARNING - THE PLASMA X11 SESSION IS !!!NOT!!! SUPPORTED BY THE FEDORA KDE SIG, PLEASE DO NOT REPORT BUGS RELATED TO IT TO THE FEDORA KDE ISSUE TRACKER, OR ASK FOR SUPPORT IN THE KDE SIG MATRIX CHAT. PLEASE CONTACT THE ACTUAL MAINTAINER OF THE PACKAGE FOR SUPPORT INSTEAD, [SEE HERE.](https://packages.fedoraproject.org/pkgs/plasma-workspace-x11/plasma-workspace-x11/)

Installing the Plasma X11 session - `sudo dnf install plasma-workspace-x11`

To switch to it, log out of the KDE Plasma session, and then click the drop down menu located at the bottom left, and select "Plasma (X11)", and then log in as usual.

## The future of this guide and a me-update

I will be archiving this guide as is, I might write a new guide whenever I get my blog up and running, though I'm not sure on what it'd be beyond a general guide to doing all the post-install initial setup you'd wanna do on Fedora. 

I've gotten very busy in recent times, and I'm also trying to become more involved in Fedora and KDE as well, so I generally don't have too much free time nowadays unfortunately :( You can check out one of my first initial contributions to Fedora (https://fedoraproject.org/wiki/KDE), which was rewriting the Fedora Wiki page for KDE to prep it for the [eventual moving of it to Fedora Docs](fedora-kde/SIG/issue/498). Hopefully I can contribute more in the future! :)

Alas, that's enough typing away for now, thank you to those who've starred this guide, and I'm incredibly grateful to those who found any sort of usefulness in this guide (seriously! It made me really happy to hear that from my fellow users back in the day :])

### Here's to many more great years with KDE Plasma on Fedora! <3

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

**Additional Multimedia Codecs**

After enabling RPMFusion, run the commands below

```sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel```

```sudo dnf install lame\* --exclude=lame-devel```

```sudo dnf group upgrade --with-optional Multimedia``` 


**Got nvidia?**
After enabling RPMFusion, run 

``sudo dnf install akmod-nvidia  xorg-x11-drv-nvidia``

or if you have a Kepler GPU (600/700 series)

``sudo dnf install akmod-nvidia-470xx xorg-x11-drv-nvidia-470xx ``

Reboot.

**CUDA drivers for people who need them: (an end user usually wouldn't really need them, so don't worry about just skipping this)**

`sudo dnf install xorg-x11-drv-nvidia-cuda` 

**or if you want them for Kepler GPUs (600/700 series)**

``sudo dnf install xorg-x11-drv-nvidia-470xx-cuda``

NOTE: I don't use Nvidia, nor am I very well versed in Nvidia on Linux, but the above should work for *most* people. 

**NOTE 2/IMPORTANT NVIDIA-ONLY NOTICE ON PLASMA WAYLAND IN GENERAL**: While Wayland by default on Nvidia-Only systems is good on GNOME (they have had a LOT more time to figure out those quirks compared to Plasma's true wayland efforts only starting around 5.20+), Nvidia Wayland is not very good on Plasma, with numerous visual bugs and crashes compared to AMD/Intel Wayland on Plasma (I daily drive Plasma Wayland on an Intel iGPU, and it's pretty usable for the most part), so if you come across a really weird visual bug or crash and you're unaware of your current session, check your current Plasma session (System Settings->About System), if it's Wayland, switch to X11 for the time being. (This was written around the time of 5.24.5, things may have changed since.)

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

# Super duper optional stuff

I am of the opinion that dnfdragora is *hot garbage*, and should not ship with KDE spin due to DNF's CLI interface (or even Discover) basically doing its job but better.

**Remove dnfdragora**: 

``sudo dnf remove dnfdragora``

I like the default Plasma wallpapers that Fedora doesn't ship, thankfully Fedora still does package them and include them in its repos

**Install default Plasma wallpapers:**

``sudo dnf in plasma-workspace-wallpapers``


# Enjoy your Fedora! <3
