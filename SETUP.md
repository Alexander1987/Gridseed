# Gridseed


sudo apt-get update

sudo apt-get install build-essential autoconf automake libtool pkg-config libcurl4-gnutls-dev

sudo apt-get install libjansson-dev uthash-dev libncurses5-dev libudev-dev libusb-1.0-0-dev libevent-dev

git clone https://github.com/dtbartle/cgminer-gc3355.git

cd cgminer-gc3355

sudo ./configure CFLAGS="-O3" --enable-scrypt --enable-gridseed

sudo make

sudo chmod +x cgminer

./cgminer -o "POOL" -u "USER" -p "PASSWORD" --gridseed-options=baud=115200,freq=850,chips=5,usefifo=0,btc=16 --hotplug 0

EXAMPLE: $ ./cgminer -o stratum+tcp://beyondcoinpool.com:3333 -u BKJKT5ZpdxppVa8LDNxCYnfHHNNAA1Xdi1 -p x --gridseed-options=baud=115200,freq=850,chips=5,usefifo=0,btc=16 --hotplug 0


#Dual Miner USB 

wget https://github.com/gridseed/cpuminer/archive/master.zip

unzip master.zip

cd cpuminer-master

#Or git clone

git clone git@github.com:gridseed/cpuminer.git

cd cpuminer

#Install automake:

sudo apt-get install automake

#Compile:

./autogen.sh

./configure CFLAGS="-O3"

make

#Find correct USB device:

ls /dev/*USB*

#..or watch syslog while plugging in ASIC:

tail -f /var/log/syslog

#Start Mining

sudo ./minerd --freq=600 --gc3355=/dev/ttyUSB0 --url="your pool" --userpass="username":"password"
