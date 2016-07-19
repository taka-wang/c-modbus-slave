# modbus slave simulator in C
[![GitHub tag](https://img.shields.io/github/tag/taka-wang/modbus-cserver.svg)](https://github.com/taka-wang/modbus-cserver/tags) 
[![Release](https://img.shields.io/github/release/taka-wang/modbus-cserver.svg)](https://github.com/taka-wang/modbus-cserver/releases/latest)
[![](https://imagelayers.io/badge/takawang/modbus-cserver:latest.svg)](https://imagelayers.io/?images=takawang/modbus-cserver:latest 'Get your own badge on imagelayers.io')

Dummy modbus slave server in C


## Build
```bash
gcc server.c -o server -Wall -std=c99 `pkg-config --libs --cflags libmodbus`
```

## Docker

### From the scratch
```bash
# build docker image 
docker build -t takawang/c-modbus-slave .

# build arm version image 
#docker build -t takawang/arm-c-modbus-slave -f Dockerfile.arm .

# run the image (host_port:container_port)
docker run -p 502:502 -d --name slave takawang/c-modbus-slave
# Print app output
docker logs <container id>
# Enter the container
docker exec -it <container id> /bin/bash
```

### Pull pre-built docker image
```bash
docker pull takawang/c-modbus-slave
```

## Credit
According to [libmodbus tests](https://github.com/stephane/libmodbus/tree/master/tests).