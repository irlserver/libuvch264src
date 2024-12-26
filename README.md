## Build Steps

sudo apt install build-essential cmake git meson pkg-config
sudo apt install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
sudo apt install libusb-1.0-0 libusb-1.0-0-dev

cd libuvc
cmake .
make & sudo make install

cd ..
mkdir build
meson setup build libuvch264src/

cd build
meson compile
meson install

sudo mv /usr/local/lib/aarch64-linux-gnu/gstreamer-1.0/libgstlibuvch264src.so /lib/aarch64-linux-gnu/gstreamer-1.0/
sudo cp /usr/local/lib/libuvc.* /usr/lib/aarch64-linux-gnu/

