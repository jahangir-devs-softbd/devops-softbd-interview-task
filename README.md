# Geoservice

Download gerservice from this link

https://medium.com/r/?url=https%3A%2F%2Fdocs.geoserver.org%2Flatest%2Fen%2Fuser%2Finstallation%2Findex.html

extract it and move it to root location
```shell
sudo mv ./geoserver-2.25.2-bin /usr/share/geoserver
```

install java version 17 and check version
```shell
sudo apt install openjdk-17-jdk
java -version
```

add environment variable and add permission
```shell
echo "export GEOSERVER_HOME=/usr/share/geoserver" >> ~/.profile
sudo chown -R jahangir_devs /usr/share/geoserver/
```

go to installed location and run this command to run geoservice
```shell
cd geoserver/bin
sh startup.sh
```

# openVpn

**installation guideline**
https://community.openvpn.net/openvpn/wiki/OpenVPN3Linux?_gl=1*9o30it*_ga*MTgxMjYzODU1NC4xNzE5NzM5MjUz*_ga_E45Z33NTV7*MTcxOTczOTI1My4xLjEuMTcxOTczOTM1Ny4wLjAuMTA4NDY1NDU2OQ..*_fplc*VHVWeEUlMkZyVWZWZWZUY1RnVzE1c2plckYzZ3VmNnFnJTJGTHA2U2s4YkpkTWtnNzZqM29GZ3d5ZGVXZTFJTEREJTJCM0ZVQXcyTUlXdHZQUjlpamFneTJFNWJBTDRLMHlvbnJNOFJFdXd2OGZoak5QOWt1b3d0TENMYWl2TkZTVGVRJTNEJTNE*_gcl_au*MTM5Nzg5NTI3Mi4xNzE5NzM5MjUw*_ga_SPGM8Y8Y79*MTcxOTczOTI1Mi4xLjEuMTcxOTczOTM1Ny4wLjAuMA..

install depandancy packages for security
```shell
sudo -s
apt install apt-transport-https curl
mkdir -p /etc/apt/keyrings
curl -sSfL https://packages.openvpn.net/packages-repo.gpg -o /etc/apt/keyrings/openvpn.asc
echo "deb [signed-by=/etc/apt/keyrings/openvpn.asc] https://packages.openvpn.net/openvpn3/debian $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/openvpn3.list
apt update
apt install openvpn
```

or we can install it from ubuntu official repository
```shell
sudo apt install openvpn
```

further reading

https://openvpn.net/openvpn-client-for-linux/


# Percona

percona installation guideline

https://medium.com/r/?url=https%3A%2F%2Fdocs.percona.com%2Fpercona-server%2F8.0%2Fquickstart-apt.html%23installation-steps

# Create virtual machine in ubuntu

create virtual machine using **KVM** which is build in tools in ubuntu machine.
```shell
sudo apt update
sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virtinst virt-manager
```

add user so we don't need to use sudo 
```shell
sudo adduser $USER libvirt
sudo adduser $USER libvirt-qemu
newgrp libvirt
```

# Virtual host

ubuntu has build in virtualization tools called kvm.

first we need to install depandancy packages
```shell
sudo apt update
sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virtinst virt-manager
```


then create group and permission for this 
```shell
sudo adduser $USER libvirt
sudo adduser $USER libvirt-qemu
newgrp libvirt
```

restart this service
```shell
sudo systemctl start libvirtd
sudo systemctl enable libvirtd
```

install virt manager for gui
```shell
sudo apt install virt-manager
```


download alpine image from linux alpine site `https://www.alpinelinux.org/downloads/`

then run this command to virtualization this linux image
```shell
sudo virt-install --name alpinevm --memory 1024 --vcpus 1 --disk size=10 --cdrom /home/jahangir_devs/torrent/alpine-standard-3.20.1-x86_64.iso --os-variant=generic --graphics=none --network bridge=virbr0 --console pty,target_type=serial
```
It should ask us user and password it will be `user: root, password: root`

N:B: If command line can't work then open virt-manager then load it from gui `file > create new virtual machine`

