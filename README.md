# Modbus slave simulator in C

[![Docker](https://img.shields.io/badge/docker-ready-brightgreen.svg)](https://hub.docker.com/r/edgepro/c-modbus-slave/)

Dummy modbus slave server in C

## Continuous Integration

I do continuous integration and build docker images after git push by self-hosted [drone.io](http://armdrone.cmwang.net) server for armhf platform , [circleci](http://circleci.com) server for x86 platform and [dockerhub](https://hub.docker.com/r/edgepro/c-modbus-slave/) service.

| CI       | Platform  | Status                                                                                                                                 |
|----------|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| Travis   | x86       | [![Build Status](https://travis-ci.org/taka-wang/c-modbus-slave.svg)](https://travis-ci.org/taka-wang/c-modbus-slave)    |
| CircleCI | x86       | [![CircleCI](https://circleci.com/gh/taka-wang/c-modbus-slave.svg?style=shield)](https://circleci.com/gh/taka-wang/c-modbus-slave)     |
| Drone    | armhf     | [![Build Status](http://armdrone.cmwang.net/api/badges/taka-wang/c-modbus-slave/status.svg)](http://armdrone.cmwang.net/taka-wang/c-modbus-slave)|

## Pre-built docker images

You can download pre-built docker images from the [dockerhub](https://hub.docker.com/r/edgepro/c-modbus-slave/tags/).

## From source code

```bash
gcc server.c -o server -Wall -std=c99 `pkg-config --libs --cflags libmodbus`
```

## From docker file (x86)

```bash
docker build -t c-modbus-slave:x86 .
```

## From docker file (armhf)

```bash
docker build -t c-modbus-slave:armhf -f Dockerfile.armhf .
```

## Credit

This simulator is derived from [libmodbus tests](https://github.com/stephane/libmodbus/tree/master/tests).

---

## License

MIT
