# Images

This repository contains a bunch of images designed for use with Pterodactyl's egg system.  Each image is rebuilt
periodically to ensure dependencies are always up-to-date.

Images are hosted on `ghcr.io`.

To use any of these images, use `ghcr.io/rafi67000/images:<IMAGE>`.

Any images ending with `-install` should only be used as a install image for running an install script, these images
will not work to run the actual server and are only designed to reduce installation time and network usage by
pre-installing common installation dependencies such as `curl` and `wget`.

## Available Images
### Java

#### Java 8

- [`java8-zulu`](https://github.com/matthewpi/images/tree/master/java/8-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java8-zulu`
  - Supported Architectures
    - `linux/amd64`

#### Java 11

- [`java11-zulu`](https://github.com/rafi67000/images/tree/master/java/11-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java11-zulu`
  - Supported Architectures
    - `linux/amd64`

#### Java 16

- [`java16-zulu`](https://github.com/rafi67000/images/tree/master/java/16-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java16-zulu`
  - Supported Architectures
    - `linux/amd64`
    - `linux/arm64`

#### Java 17

- [`java17-zulu`](https://github.com/rafi67000/images/tree/master/java/17-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java17-zulu`
  - Supported Architectures
    - `linux/amd64`
    - `linux/arm64`
    
#### Java 18

- [`java18-zulu`](https://github.com/rafi67000/images/tree/master/java/18-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java18-zulu`
  - Supported Architectures
    - `linux/amd64`
    - `linux/arm64`
    
#### Java 19

- [`java19-zulu`](https://github.com/rafi67000/images/tree/master/java/19-zulu)
  - Tags
    - `ghcr.io/rafi67000/images:java19-zulu`
  - Supported Architectures
    - `linux/amd64`
    - `linux/arm64`
