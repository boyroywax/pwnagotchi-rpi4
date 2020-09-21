# pwnagotchi-rpi4
Im gonna get pwnagotchi working on rpi4.

## Install bettercap
```shell
git clone https://github.com/bettercap/bettercap
cd bettercap/
make build
sudo make intall
```

## Running bettercap manually
```shell
sudo bettercap -caplet https-ui -iface wlxxxx
```

## Install pwngrid
```shell
wget "https://github.com/evilsocket/pwngrid/releases/download/v1.10.3/pwngrid_linux_amd64_v1.10.3.zip"
unzip pwngrid_linux_amd64_v1.10.3.zip
sudo chmod +x pwngrid
sudo mv pwngrid /usr/bin
```
## Set the pwngrid peer service
```shell
sudo nano /etc/systemd/system/pwngrid-peer.service
```


## Install dependencies

## Install python3 and pip3 on the rpi


## Install pip3 packages
```shell
sudo pip3 install tensorflow
pip3 install scikit-build
```

### Create cMake binary by hand.
```shell
wget https://github.com/Kitware/CMake/releases/download/v3.18.2/cmake-3.18.2.tar.gz
tar -zxf cmake-3.18.2.tar.gz
cd cmk-3.18.2/
./bootstrap && make && sudo make install
cd bin/
sudo mv * /usr/bin
```

## Install pwnagotchi
```shell
wget "https://github.com/evilsocket/pwnagotchi/archive/v1.4.3.zip"
unzip v1.4.3.zip
```
