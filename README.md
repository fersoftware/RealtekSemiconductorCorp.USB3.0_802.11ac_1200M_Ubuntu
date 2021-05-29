# RealtekSemiconductorCorp.USB3.0_802.11ac_1200M_Ubuntu
*** Este Usb Wifi acessa o protocolo A e C atingindo maiores velocidades de internet <br>
Pode ser que o ubuntu não detecte, então segue abaixo como fazer detectar. Testado no Ubuntu 20.4
***

![rBVaqGBt87eAYQLYAAD_dmEtkhU415](https://user-images.githubusercontent.com/3814117/120053729-509f0b00-c002-11eb-8b58-03ddbb4d509f.jpg)
![Captura de tela_2021-05-28_22-19-35](https://user-images.githubusercontent.com/3814117/120053844-df138c80-c002-11eb-87c6-9709b6b9218d.png)

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
