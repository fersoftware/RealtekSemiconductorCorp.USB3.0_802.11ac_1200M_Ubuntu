# RealtekSemiconductorCorp.USB3.0_802.11ac_1200M_Ubuntu
![rBVaqGBt87eAYQLYAAD_dmEtkhU415](https://user-images.githubusercontent.com/3814117/120053729-509f0b00-c002-11eb-8b58-03ddbb4d509f.jpg)
```
sudo apt update
sudo apt install git dkms build-essential
git clone https://github.com/cilynx/rtl88x2bu.git
cd rtl88x2bu
VER=$(sed -n 's/\PACKAGE_VERSION="\(.*\)"/\1/p' dkms.conf)
sudo rsync -rvhP ./ /usr/src/rtl88x2bu-${VER}
sudo dkms add -m rtl88x2bu -v ${VER}
sudo dkms build -m rtl88x2bu -v ${VER}
sudo dkms install -m rtl88x2bu -v ${VER}
sudo modprobe 88x2bu
```
