# lenovo yoga slim 7 pro 14ACH5
Ubuntu 20.04 installation notes

## Wifi 

Realtek 8852 don't work by default in 20.04.3

I find this solution

https://github.com/lwfinger/rtw89





## External Wifi adapter TP-Link Archer T3U Plus AC1300

sudo apt update

sudo apt install dkms

git clone https://github.com/cilynx/rtl88x2bu.git

cd rtl88x2bu

VER=$(sed -n 's/\PACKAGE_VERSION="\(.*\)"/\1/p' dkms.conf)

sudo rsync -rvhP ./ /usr/src/rtl88x2bu-${VER}

sudo dkms add -m rtl88x2bu -v ${VER}

sudo dkms build -m rtl88x2bu -v ${VER}

sudo dkms install -m rtl88x2bu -v ${VER}

sudo modprobe 88x2bu



\# _source:_ https://community.tp-link.com/en/home/forum/topic/208022

