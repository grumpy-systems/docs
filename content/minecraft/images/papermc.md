---
title: PaperMC
weight: 5
---

This is an installation of the [PapermC](https://papermc.io/) server fork.

## Tagging

PaperMC releases new builds frequently, so tags for this image are released
frequently.  These tag chains are created:

* `latest` - The latest Minecraft and PaperMC build version.
* `paper-xx` - This always points to the most recent build of paper for the
  specified Minecraft version.
* `paper-xx-yy` - This points to a specific PaperMC build number.
* `paper-xx-yy-u0` - This points to a specific build of the PaperMC container.

`latest` and `paper-xx` are the recommended tags to use.

{{% notice info %}}

Using a build that includes a specific PaperMC build number of an update version
will cause you to not receive any security updates.

{{% /notice %}}

## Supported Versions

The last 10 builds of each Minecraft version are built.  As an example, if there
are two active versions (`1.19` and `1.19.1`), the last 10 builds of _both_
versions are kept updated.
