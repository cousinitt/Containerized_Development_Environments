# VERY UNTESTED
FROM ubuntu:latest
WORKDIR /home
RUN apt update -y; \
    apt install -y git yotta srecord; \
    git clone --depth=1 https://github.com/lancaster-university/microbit-samples
CMD ["/usr/bin/bash"]
