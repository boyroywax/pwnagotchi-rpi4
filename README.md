# pwnagotchi-rpi4
Im gonna get pwnagotchi working on rpi4.

## Install dependencies
```shell
sudo apt install golang git build-essential libpcap-dev libusb-1.0-0-dev libnetfilter-queue-dev
```

## Install python3 and pip3 on the rpi


## Install bettercap
```shell
git clone https://github.com/bettercap/bettercap
cd bettercap/
make build
sudo make intall
```

## Setup bettercap for start with system
```shell
sudo nano /etc/systemd/system/bettercap.service
```

```text
[Unit]
Description=bettercap api.rest service.
Documentation=https://bettercap.org
Wants=network.target

[Service]
Type=simple
PermissionsStartOnly=true
ExecStart=/usr/bin/bettercap-launcher
Restart=always
RestartSec=30

[Install]
WantedBy=multi-user.target
```


```shell
sudo nano /usr/local/share/bettercap/caplets/pwnagotchi-auto.cap
```

```text
# enable interface monitor mode and define wifi interface to be mon0
set wifi.interface wlx00

# api listening on http://127.0.0.1:8081/ and ui to http://127.0.0.1
set api.rest.address 127.0.0.1
set api.rest.port 8081
set api.rest.username pwnagotchi
set api.rest.password pwnagotchi
set api.rest.websocket true

# go!
api.rest on
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
sudo mv pwngrid /usr/bin/
```

## Set the pwngrid peer service
```shell
sudo nano /etc/systemd/system/pwngrid-peer.service
```

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

### Install

## Install pwnagotchi
```shell
wget "https://github.com/evilsocket/pwnagotchi/archive/v1.4.3.zip"
unzip v1.4.3.zip
```
