# InVEST
[Natural Capital InVEST](https://naturalcapitalproject.stanford.edu/invest/) powered by Docker

# Prerequisites

Packages:
- docker

Config:
- X Server configuration (to be improved)

Ubuntu instructions:
```console
foo@bar:~$ sudo apt-get install -y docker.io
foo@bar:~$ xhost +local:root
```

# Start the application
```console
foo@bar:~$ sudo docker run -it \
-e DISPLAY=unix$DISPLAY \
-e USERNAME=$USER \
--workdir="/home/$USER" \
--volume="/home/$USER:/home/$USER:rw" \
--volume="/etc/group:/etc/group:ro" \
--volume="/etc/passwd:/etc/passwd:ro" \
--volume="/etc/shadow:/etc/shadow:ro" \
--volume="/etc/sudoers.d:/etc/sudoers.d:ro" \
--volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
--volume="/etc/localtime:/etc/localtime:ro" \
--volume="/etc/timezone:/etc/timezone:ro" \
rpn80/natcap.invest
```
