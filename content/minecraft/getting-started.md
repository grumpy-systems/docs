---
title: "Getting Started"
weight: 1
---

Using Dockerized Minecraft is pretty straightforward.  You'll need a few
requirements and some basic Docker knowledge to get going.

## Requirements

To get started, you'll need [Docker](https://www.docker.com/) installed and
working on your system.  This guide won't go into how to do that, since there
are lots of Docker install tutorials out there.

You'll also need the CPU and memory requirements of whatever verison of
Minecraft you plan on hosting.  Generally, a decent CPU and a few GB of RAM are
a minimum.

{{% notice info %}}

These images are only built for 64 bit systems using a x86 processor (most
servers and desktops).  These images won't work on most embedded devices anyway
due to resource issues, so they aren't even built for them. 

{{% /notice %}}

## Running Things Quickly And With No Regard For Safety

If you don't care about storing your data (ie you're running a quick test), just
run the container with no volumes:

```bash
docker run --rm -p 127.0.0.1:25565:25565 grumpysystems/vanilla:latest
```

You'll get some warnings, but in a few moments you should have a functional
Minecraft server with all the defaults.

## Running Things With Docker Compose

If you want to run things and save your data, I recommend using Docker Compose
to configure volumes and ports in a single file.

Here's an example `docker-compose.yaml` file you can run:

```yaml
version: '3.5'

services:
  mc:
    image: grumpysystems/papermc:latest
    ports:
      - 25565:25565
    volumes:
      - ./data:/opt/minecraft/server/

    environment:
      - "JAVA_MEM=4G"

    restart: always
    user: "5000:5000"
```

This creates a few things:

* Sets the User to a more-safe option.  Running everything in the world as Root
  raises potential issues.
* Sets a data directory for the map and configuration.  This directory is not
  removed and can be backed up, so your world can survive reboots or server
  crashes.
* Sets a Java memory limit.

Once created, then run `docker-compose up` to launch your new server.

## Custom Configuration

The server mounts a directory that will contain your map file and other
configuration files.  You'll probably want to bind this directory to a local
directory on your machine so you can view and backup the files as needed.  That
file is a normal Minecraft Server directory, so you can customize things as
desired.

{{% notice warning %}}

The JAR file for server is overwritten as part of the container startup.  If you
overwrite or update that file, it will be overwritten by the default file the
next container boot.

{{% /notice %}}

## Lifecycles

If you're running these for a while, I go over my [lifecycle
policies](/minecraft/lifecycle/) as well.
 