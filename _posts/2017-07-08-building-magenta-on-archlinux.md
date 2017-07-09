---
layout: post
category : Geek
tags : [google, magenta, fuchsia, arch, linux, kernel]
title: Building Magenta on Archlinux
---
{% include JB/setup %}

I have been a bit curious about Fuchsia/Magenta. From the README:

_Magenta is the core platform that powers the Fuchsia OS. Magenta is composed of
a microkernel (source in kernel/...) as well as a small set of userspace
services, drivers, and libraries (source in system/...) necessary for the
system to boot, talk to hardware, load userspace processes and run them, etc.
Fuchsia builds a much larger OS on top of this foundation._

I decided to poke a bit around. Here are a quick notes on how to build it on
Arch. These instructions assume you have the usual tools like `base-devel`.

The canonical git repository is at
[https://fuchsia.googlesource.com/magenta](https://fuchsia.googlesource.com/magenta).
There is also a mirror (read only) on GitHub
[https://github.com/fuchsia-mirror/magenta](https://github.com/fuchsia-mirror/magenta).

Download the tool chain:

```bash
./scripts/download-toolchain
```

Install libtinfo from AUR:

```bash
yaourt -S libtinfo
```

Archlinux comes with `/usr/lib/libtinfo.so.6` (not
`/usr/lib/libtinfo.so.5`) and I didn't feel like installing another version of
libtinfo, so i just created a symlink to the new version. So far, everything
seems to work fine.

```bash
sudo ln -s /usr/lib/libncursesw.so.6.0 /usr/lib/libtinfo.so.5
```

Build it:

```bash
make -j4 magenta-pc-x86-64
```

Install QEMU except if you plan to just test it on real hardware:
```
sudo pacman -S qemu
```

Run it:
```
./scripts/run-magenta-x86-64
```
