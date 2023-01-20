# Development Environments

I like to develop for embedded platforms as a hobby. The problem is that I am a
bit fickle, and when I decide that I want to rush off to the next thing, I
don't want to worry about all of the debris from developing for the board to be
left on my filesystem. Here, I just toss all of the stuff in a container, and
develop for a while, until I get frustrated or buy a new toy. Then, cleanup is
as simple as getting rid of a container.

The good news is that you have a containerized development environment, the bad
news is that you have zero access to hardware. If there is some nice script to
flash your board, you are out of luck. You will have to hack something together
on your filesystem, or perhaps use a virtual machine.

# So, what do I do with `Dockerfile`?

You will have to load Docker, and will have to build the image. I suggest something like this:

```sh
docker build -f Dockerfile -t esp_8266 .
```

Once you have the image, you would run it with a command like:

```sh
docker run -it --mount type=bind,src=`pwd`,dst=/mnt/host_filesystem \
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
TODO: How to flash firmware once built.

## ESP32

I tried to follow the directions [here](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/).
TODO: How to flash firmware once built.
