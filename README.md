[Video] How to install java JDK in Ubuntu 12.04, 11.10 LTS April 5, 2012
http://forums.team-nocturnal.com/index.php/topic/629-video-how-to-install-java-jdk-in-ubuntu-1204-1110-lts-april-5-2012/


[Video] How to install ADB in Ubuntu Linux 12.04 & 11.10 LTS 32bit & 64 April 5, 2012
http://forums.team-nocturnal.com/index.php/topic/630-video-how-to-install-adb-in-ubuntu-linux-1204-1110-lts-32bit-64-april-5-2012/

This is strictly just a reference guide/tutorial! If you cannot simply follow directions and copy/paste, I'm not going to help you! This is idiot-proof.

Build Environment

Operating system -- Tested on Ubuntu 12.xx and 13.04 (64bit)
Terminal
Decent hardware (minimum of at least a dual core CPU and 4 GB of RAM)
Optimally have an SSD (standard mechanical drives work as well but slow down the process drastically)
Must have required packages for building installed, I will list them further down
Required Packages

Simply copy and paste this in a terminal window:

$ sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib mingw32 openjdk-6-jdk tofrodos python-markdown libxml2-utils xsltproc zlib1g-dev:i386

Let that install and then proceed.

More copy and paste:

$ sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so

Getting the Source
Make required directories
Obtain repo binary
Add repo binary to your path
Give repo binary proper permissions
Initialize empty repo

Sync repo

Alright, so now we're getting there. I have outlined the basics of what we're about to do and broke them down as I know them. This is all pretty much going to be copy/paste so it'll be fairly difficult to screw this up :)

Copy/paste:

Make directory for repo binary

$ mkdir ~/bin

Add directory for repo binary to your path

$ PATH=~/bin:$PATH

Download repo binary and place it in the proper directory

$ curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo

Give the repo binary the proper permissions

$ chmod a+x ~/bin/repo

Create directory for where the SofaKingAndroid repo will be stored and synced

$ mkdir ~/dev

$ mkdir ~/dev/sofa

Move to our new sofa directory

$ cd ~/dev/sofa

Initialize the sofa repo and download the manifest

Init core trees without any device/kernel/vendor :

$ repo init -u https://github.com/SofaKingAndroid/platform_manifest.git -b ska43

sync repo :

$ repo sync
use the Make clean script if you want to do a clean build

$ make clean && make clobber

Build the rom for mako

$ . build/envsetup.sh && brunch mako



If you wish to post your rom using our source, please follow our thread format and guide lines found here. 
http://forums.team-nocturnal.com/index.php/forum/61-sofaking-development/
