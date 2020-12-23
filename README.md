# MultiROM 7.1 ( TWRP 3.1.1 )
-----------------------------

## Setup PC / Laptop / Server
```bash
- Need :
    + : CPU Core I3 / I5 / I7 / I9 / ...
    + : CPU Core Dual ...
    + : CPU Xeon ...
    + : Min 4Gb Ram ( Like 8Gb And More )
    + : 80Gb HDD ( Liker More And SSD )
    + : Internet
    + : Linux ( Ubuntu / Fedora / Debian / ArchLinux ) Or ( WSL / WSL2 )
```

```bash
On Debian :

sudo apt update

sudo apt upgrade -y

sudo apt-get install git ccache lzop bison gperf build-essential zip curl zlib1g-dev g++-multilib python-networkx libxml2-utils bzip2 libbz2-dev libghc-bzlib-dev squashfs-tools pngcrush liblz4-tool optipng libc6-dev-i386 gcc-multilib libssl-dev gnupg flex lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev xsltproc unzip python-pip python-dev libffi-dev libxml2-dev libxslt1-dev libjpeg8-dev openjdk-8-jdk

sudo rm -rf /usr/bin/repo

curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/repo

sudo mv ~/repo /usr/bin/repo

sudo chmod a+x /usr/bin/repo
```

## Repo Sync
```bash
repo init -u https://github.com/KernelPanic-OpenSource/manifest.git -b mr-7.1

repo sync -vf -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

## Start Build
```bash
export ALLOW_MISSING_DEPENDENCIES=true

source build/envsetup.sh

lunch tipsy_bacon-eng

mka -j$(nproc --all) recoveryimage

mka -j$(nproc --all) multirom_zip

mka -j$(nproc --all) multirom_uninstaller
```

## Info Devices
```bash
- Devices : OnePlus One
- Code name : Bacon
- Devices name : A0001
```
```bash
- SoC :
    - Snapdragon 801 :
		+ : MSM8974AC
		+ : 4 Core
		+ : 28mn HPm
		+ : Krait 400
		+ : ARMv7
		+ : 2.5Ghz
    - DSP :
		+ : Hexagon
		+ : QDSP6V5A
		+ : 600Mhz
    - Adreno 330 :
		+ : 578Mhz
		+ : 2160p
```
```bash
- RAM : 3Gb
    - LPDDR3
    - 1888Mhz
```
```bash
- ROM :
    - 64Gb :
		+ : Sandstone Black
    - 16Gb :
		+ : Silk White
```
```bash
- Battery : 
    + : 3100mAh
    + : LI-PO
```
```bash
- Display : 
    + : 1920x1080
    + : 401 PPI Pixel
```
```bash
- Camera :
    - : Rear camera
       		+ : Sony Exmor RS IMX214
		+ : 13 megapixels
       		+ : 4128×3096 Pixel
       		+ : AutoFocus, Dual-LED Flash
       		+ : DCI 4K@24FPS
       		+ : 2160p@30FPS
       		+ : 1080p@60FPS
       		+ : 720p@120FPS
       		+ : HDR
       		+ : 100Mbps If 30FPS
     - : Front camera
		+ : 5 megapixels
		+ : 1080p@30FPS
		+ : extra-wide 80º viewing angle
```
```bash
- Sound :
    + : Dual mono speakers
    + : 3.5 mm
    + : Stereo audio jack
```
```bash
- Wifi :
    + : Support Dual -> 2Ghz / 5Ghz
```
