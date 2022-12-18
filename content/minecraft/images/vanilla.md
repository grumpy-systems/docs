---
title: "Vanilla"
weight: 5
---

This image is an installation of a purely vanilla Minecraft instance straight
from Mojang.  It has no mods and no extra forks or configuration.

## Tagging

This image has a few tag chains that are maintained:

* `latest` always points to the highest Minecraft Version.
* `vanilla-xx` always points to the most recent build of a specific Minecraft Version.
* `vanilla-xx-u0` always points to a static build of a Minecraft version.

Pointing to `latest` will ensure that your server is always up to date.
Eventually, a major version tag will likely come along, so you can hold on
`1.19` and still get patches without jumping to new versions.

{{% notice info %}}

Using a build _other than_ `latest` can cause you to fall behind, including
security updates that Mojang releases.  Since they increment the Minecraft
version number, holding on `vanilla-1.19` will prevent you from getting any
security updates that may come.

{{% /notice %}}

## Supported Versions

The last 5 releases are supported, meaning they'll get updates if the `base`
image is updated.
