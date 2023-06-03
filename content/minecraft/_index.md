---
title: "Dockerized Minecraft"
---

This is a system to run Minecraft in automatically-updated docker containers.
These containers are updated daily, and by setting a tag such as `1.19.3`, you
can always ensure your Minecraft server is the latest version.

## Motivation

I run a few Minecraft servers for family and friends, and I was always
struggling to keep them up to date.  Especially with forks like PaperMC, builds
are released nearly daily.

I found other containers that did a similar thing, but they all were lacking a
few key things:

* Build Immutability - Most of these just downloaded the Minecraft Jar files on
  the fly, so having things locked to a specific version was not possible.  I
  went a step further and even have immutability for specific OS patch versions
  too, in case that causes some issue.
* Lack of updates - It was up to the container's author to update things, and
  there was usually some delay.  These containers update daily for any new
  Minecraft versions, and weekly for OS patches.
* No shared images - When an update is released, you're downloading a large
  image over and over, which is just inefficient.

These containers are immutable, meaning `v1234` is always containing `v1234` of
whatever Minecraft version is in there.

## Documentation

{{% children style="h3" depth="1" description="true" %}}
