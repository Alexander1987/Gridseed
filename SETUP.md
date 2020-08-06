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
