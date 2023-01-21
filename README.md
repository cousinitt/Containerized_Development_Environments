# Development Environments

This is sort of a pipe dream. I like to develop for embedded platforms as a
hobby. The problem is that I am a bit fickle, and when I decide that I want to
rush off to the next thing, I don't want to worry about all of the debris from
developing for the board to be left on my filesystem. If it were a simple
matter of uninstalling a package, fine. However most of these vendor
development kits want to just write files everywhere. Some of the larger
platforms almost assume that you have an entire computer to dedicate to their
stuff, or that your computer is a monster high power thing, but mine isn't.

If I could package these up in a Docker container, and develop for a while,
(until I get frustrated or buy a new toy) then cleanup would be as simple as
getting rid of a container. You (should) also be able to flash the firmware,
because it is possible to give your Docker container access to a device file,
like `/dev/ttyUSB0`, by supplying `--device=/dev/ttyUSB0` to the docker
container `run` or `start` command. I do believe that you have to have the
device attached before you start the container.

# So, what do I do with `Dockerfile`?

You will have to load Docker, and will have to build the image. I suggest something like this:

```sh
docker build -f Dockerfile -t esp_8266 .
```

Once you have the image, you would run it with a command like:

```sh
docker run -it --mount type=bind,src=`pwd`,dst=/mnt/host_filesystem \
           --device=/dev/ttyUSB0 \
           esp_8266 /usr/bin/bash
```

Ok, the Docker pros will tell you to use volumes. I am not a pro. You should
probably use volumes. Anyway, Docker shuts down the container when you exit the
shell, and if you want to start it back up:

```sh
docker start my_esp
docker attach my_esp
```

## ESP 8266

I tried to follow the directions [here](https://docs.espressif.com/projects/esp8266-rtos-sdk/en/latest/get-started/index.html).

## ESP32

I tried to follow the directions [here](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/).

## Micro:Bit

This is the low-level development environment, in C. This can be done either
[online or offline](https://lancaster-university.github.io/microbit-docs/).
It is probably a lot easier to do it online, but maybe you can't get online?
The offline installation follows the installation instructions
[here](https://lancaster-university.github.io/microbit-docs/offline-toolchains/).
