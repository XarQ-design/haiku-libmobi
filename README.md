# libmobi for Haiku

The [Haiku](https://www.haiku-os.org/) package of [libmobi](https://github.com/bfabiszewski/libmobi) 0.12, which
[XarQ](https://xarq.org) uses to open the cover and pictures of Mobipocket and Kindle e-books (.mobi, .azw3). HaikuPorts doesn't have it, so we build it
and publish it in XarQ's own package repository.

## Install

Add the XarQ repository once, then install it like any other package:

```
pkgman add-repo https://xarq.org/haiku/x86_64/current
pkgman install libmobi
```

For development, install `libmobi_devel` too. The packages are built on Haiku R1/beta6
(x86_64) and also work on newer nightlies.

## What's here

`media-libs/libmobi/` is a HaikuPorts recipe, in the same layout as the
[haikuports](https://github.com/haikuports/haikuports) tree. 

To build it yourself, copy that folder into your haikuports tree and run:

```
haikuporter -S --get-dependencies libmobi
```

Set `VENDOR="XarQ"` in `haikuports.conf` first if the package is going into the XarQ
repository: Haiku's repository tool only accepts packages whose vendor matches the
repository's.

## Releases

Each release has the built `.hpkg` files. The XarQ repository at
https://xarq.org/haiku picks them up automatically, through the workflow in
[XarQ-design/xarq](https://github.com/XarQ-design/xarq/blob/main/.github/workflows/haiku-repo.yml).

## Licence

libmobi is under the LGPL 3 licence; see the upstream project. The recipe is under the MIT
licence, like the HaikuPorts tree, and any patch is under libmobi's own licence.
