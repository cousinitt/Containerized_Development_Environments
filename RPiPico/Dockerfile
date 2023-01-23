# VERY UNTESTED
FROM ubuntu:latest
WORKDIR /home
RUN apt update -y; \
    apt install -y git yotta srecord; \
    git clone --depth=1 https://github.com/lancaster-university/microbit-samples
CMD ["/usr/bin/bash"]

# sudo apt update
# sudo apt install git cmake gcc-arm-none-eabi gcc g++ libstdc++-arm-none-eabi-newlib
# sudo apt install automake autoconf build-essential texinfo libtool libftdi-dev libusb-1.0-0-dev

# mkdir ~/raspberry-pi-pico
# cd ~/raspberry-pi-pico
# wget https://raw.githubusercontent.com/raspberrypi/pico-setup/master/pico_setup.sh
# chmod +x pico_setup.sh
# ./pico_setup.sh

# https://circuitdigest.com/microcontroller-projects/how-to-program-raspberry-pi-pico-using-c
