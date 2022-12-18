---
title: "Base"
weight: 1
---

The base image is the image on which all the downstream images are based on.
This image is basically Debian with a JRE and some base tooling to make things
work.

## Tagging

This image has a few tag chains that are maintained:

* `latest` always points to the highest JRE version.
* `java-xx` always points to the latest revision with that JRE version.
* `java-xx-u0` always points to a static build of a JRE image.

Pointing to `latest` or `java-xx` will ensure that your JRE is always up to date.

{{% notice info %}}

Using a specific build (`java-xx-uy`) is intended only for bug troubleshooting
or edge cases.  Setting this version will disable any sort of updates
**including security updates**.

{{% /notice %}}

## Tooling

The key thing this image contains (other than a JRE) is some tooling to start
and control the server.  This is really just a shell script that is the
entrypoint for Docker, but downstream images rely on it to start things correctly.
