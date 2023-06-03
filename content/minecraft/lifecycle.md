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
that image.  Each tag will contain the upstream version that's in that container
(like `1.18.2`) and an internal update number (starts at `u0` and counts up).

The internal updates may contain a few changes, but generally are the result of
updated software in the Base Debian image used (like a security update) or an
update to internal tooling scripts.  These versions are released every Tuesday
to keep the underlying containers up to date.

When an image is no longer supported, that simply means that it will not receive
any OS or tooling updates.  You are free to continue using it and it will likely
work fine, though it may be missing security patches.

{{% notice warning %}}

Using an unsupported version means that you are no longer getting security
updates for the container.  For this reason, use one of the recommended tag
chains for the server you are running.

{{% /notice %}}

### Version Example

Let's say you have two version tags, `vanilla-1.18.1-u0` and `vanilla-1.19-u0`.
Between these versions, a new minecraft image was released and updating will
bring you to the new version.  There may also be new OS patches applied as well.

In contrast, if you have `vanilla-1.18.1-u0` and `vanilla-1.18.1-u1`, that means
the underlying container was updated.  Both of these containers have the same
minecraft version, just different patches or updates applied to the base
container.

## How to Keep Updated

The best way to ensure that you are always on a supported version is to use a
tag chain that will be automatically updated.  If you want your server always on
the latest version, just use `latest`, and your server will be upgraded
automatically.

Recommended tag chains will be outlined on the page for each image.

## New Releases

New releases of Minecraft and server forks are detected and released
automatically without much fanfare.  If you are wanting to keep things on a
specific version, it's up to you to watch for new versions and ensure you are
not out of date.
