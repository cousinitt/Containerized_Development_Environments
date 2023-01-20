FROM ubuntu:latest
WORKDIR /home
RUN apt update -y; \
    apt install -y curl gcc git wget make libncurses-dev flex bison gperf python3 python3-pip python3-serial; \
    curl -O https://dl.espressif.com/dl/xtensa-lx106-elf-gcc8_4_0-esp-2020r3-linux-amd64.tar.gz; \
    tar xzf xtensa-lx106-elf-gcc8_4_0-esp-2020r3-linux-amd64.tar.gz; \
    git clone --recurse-submodules --depth=1 https://github.com/espressif/ESP8266_RTOS_SDK.git; \
    python3 -m pip install -r /home/ESP8266_RTOS_SDK/requirements.txt
    
ENV IDF_PATH=/home/ESP8266_RTOS_SDK
ENV PATH=$PATH:/home/esp/xtensa-lx106-elf/bin  

# COPY c_callgraph.py c_callgraph.py
CMD ["/usr/bin/bash"]
