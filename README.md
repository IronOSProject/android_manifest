# IronLOS-Project #

<img src="https://i.imgur.com/IJLaeaS.png">

A Small Description of the Iron V2
----------------------------------

This ROM is a based on ProtonAOSP for this Android Version (A12), so it will follow all its developments.
I just added the features that I think are useful for my use of the device.
Since I worked on it, I thought I'd share the work with those who make the same use of the device as me !!
Good building.

Credits
-------

- ProtonAOSP
- CyanogenMod/LineageOS
- Shapeshift
- Derpfest
- AICP
- AOSiP
- AOSPA
- BootleggersROM
- CrDroid
- DirtyUnicorns
- NitrogenOS
- OmniROM
- PixelExperience
- POSP
- RevengeOS
- ... and my friend @Bicet
### For Building
--------

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    apt update
    apt install repo git gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 rsync lib32ncurses-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
    exit

Create IronLOS folder
----------------------------------

    mkdir ~/Iron
    cd ~/Iron

GIT config (nickname, e-mail)
-----------------------------

    git config --global user.email "mail@domain.com"
    git config --global user.name "login"

To initialize your local repository use
---------------------------------------

    repo init -u https://github.com/Iron-temp/android_manifest.git -b twelve

If you want to save time and space you can do a shallow clone
---------------------------------------

    repo init -u https://github.com/Iron-temp/android_manifest.git -b twelve --depth=1
    
Then to sync up:
----------------

    repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

OR to sync up without spam in your term:
----------------------------------------

    repo sync -c -q --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)

Build command are:
------------------
    . build/envsetup.sh
    lunch aosp_$device-userdebug
    mka bacon
