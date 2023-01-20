# UNTESTED
FROM ubuntu:latest
WORKDIR /home
RUN apt update -y; \
    apt install -y git wget flex bison gperf python3 python3-venv cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0; \
    git clone --depth=1 --recurse-submodules https://github.com/espressif/esp-idf.git; \
    /home/esp/esp-idf/install.sh esp32,esp32s2; \
    source /home/esp/esp-idf/export.sh
CMD ["/usr/bin/bash"]
