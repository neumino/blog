---
layout: post
category : Tinkering
tags : [linux, archlinux, dual-boot]
title: Windows not found by os-prober
---
{% include JB/setup %}

I recently bought a new computer (a Lenovo IdeaCentre G5 in case someone is
curious). When installing archlinux (in dual boot), I couldn't get
`os-prober` to detect Windows even though I could see all the Windows file in
`/boot/EFI/...`.

I eventually just manually added a grub entry

```
menuentry 'Window' {
	search.fs_uuid <UUID>
	chainloader /EFI/Microsoft/Boot/bootmgfw.efi
}
```

Where you can get the UUID of your `/boot` partition with `blkid`. Interesting
enough if you put the wrong uuid, grub will complain but will still boot Windows.
