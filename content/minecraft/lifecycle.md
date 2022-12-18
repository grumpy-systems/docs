---
title: Lifecycle
weight: 10
---

Images are maintained for a certain amount of time according to a fixed
lifecycle.  This lifecycle is purely internal and only means that tooling or OS
updates will be included.  It **does not** mean that any updates to the actual
server Jar file are available.

## Lifecycle Versions

Each server flavor has its own lifecycle rules that are found on the page for
that image.  Generally speaking, the last few upstream releases are supported
and will get an update if the base container image updates.  These updates are
marked by `u0` in the container version, where `0` increments with each release.

The internal updates may contain a few changes, but generally are the result of
updated software in the Base Debian image used (like a security update) or an
update to internal tooling scripts.

When an image is no longer supported, that simply means that it will not receive
any OS or tooling updates.  You are free to continue using it and it will likely
work fine, though it may be missing security patches.

{{% notice warning %}}

Using an unsupported version means that you are no longer getting security
updates for the container.  For this reason, use one of the recommended tag
chains for the server you are running.

{{% /notice %}}

## How to Keep Updated

The best way to ensure that you are always on a supported version is to use a
tag chain that will be automatically updated.  If you want your server always on
the latest version, just use `latest`, and your server will be upgraded
automatically.

## New Releases

New releases of Minecraft and server forks are detected and released
automatically without much fanfare.  If you are wanting to keep things on a
specific version, it's up to you to watch for new versions and ensure you are
not out of date.
