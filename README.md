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


# Parcona

percona installation guideline

https://medium.com/r/?url=https%3A%2F%2Fdocs.percona.com%2Fpercona-server%2F8.0%2Fquickstart-apt.html%23installation-steps






