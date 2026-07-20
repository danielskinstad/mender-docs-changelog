---
title: mender-binary-delta
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-binary-delta 1.5.3

_Released 02.17.2026_

### Changelogs

#### mender-binary-delta (1.5.3)

New changes in mender-binary-delta since 1.5.2:

##### Bug Fixes

* Add missing license to the OS licenses manifest


## mender-binary-delta 1.5.2

_Released 11.03.2025_

### Changelogs

#### mender-binary-delta (1.5.2)

New changes in mender-binary-delta since 1.5.1:

##### Bug Fixes

* Fix segfault when configured with partitions that do not end with a number

  This was a hidden bug that surfaced now while fixing the support for
  PARTUUID and PARTLABEL. Or, in other words, when handling Mender
  configuration with partitions that do not end with a number. In this
  case `pass_num` is `NULL` and `xasprintf` will try to dereference it.
* Correctly apply deltas with PARTUUID and PARTLABEL configuration

  This fixes the bug where `mender-binary-delta` fails to apply the delta
  when partitions are configured with PARTUUID or PARTLABEL options.

  Fixes the issue by first resolving the device symlinks like
  `/dev/disk/by-partuuid/*`, `/dev/disk/by-partlabel/*`, and `/dev/root` to
  their actual device paths (e.g., `/dev/sda2`, `/dev/mmcblk0p2`) and then
  extracting the partition numbers.

  Related to (https://github.com/mendersoftware/mender/pull/1613/commits/80ac1f8c1ccac16efa28ed1075eee2d789258af1)
  ([MEN-7160](https://northerntech.atlassian.net/browse/MEN-7160))


## mender-binary-delta 1.5.1

_Released 03.27.2025_

### Changelogs

#### mender-binary-delta (1.5.1)

New changes in mender-binary-delta since 1.5.0:

##### Bug fixes

* Convert the boot partition numbers to int before comparison.
  ([MEN-8043](https://northerntech.atlassian.net/browse/MEN-8043))


## mender-binary-delta 1.5.0

_Released 03.21.2024_

### Changelogs

#### mender-binary-delta (1.5.0)

New changes in mender-binary-delta since 1.4.1:

##### Bug fixes

* Fix a few memory leaks.

##### Features

* Implement support for UBIFS. This requires either
  mender-flash or ubiupdatevol to be installed on the device. The
  `FlashTool` option decides which one to use. Currently the default is
  to not use either, but build systems may provide their own defaults.
  ([MEN-6774](https://northerntech.atlassian.net/browse/MEN-6774))


## mender-binary-delta 1.4.1

_Released 09.25.2022_

### Changelogs

#### mender-binary-delta (1.4.1)

New changes in mender-binary-delta since 1.4.0:

##### Features

* Licenses are now available in the package, instead of only
  online. ([MEN-5517](https://northerntech.atlassian.net/browse/MEN-5517))


## mender-binary-delta (1.4.0)

_Released 07.06.2022_

### Changelogs

#### mender-binary-delta (1.4.0)

New changes in mender-binary-delta since 1.3.1:

##### Bug fixes

* Delta Artifacts should now be significantly faster to apply, since
  the extra checksum check done by Mender has been removed, and only the checksum
  done by the xdelta3 algorithm is used. Therefore, there is no double read of the
  newly written partititon, which speeds up the installation significantly.
  ([MEN-5607](https://northerntech.atlassian.net/browse/MEN-5607))

##### Other

* Additional arguments to xdelta3 with -D/--decoder-arguments
  ([MEN-5193](https://northerntech.atlassian.net/browse/MEN-5193))
* style: Extra log for the decoder arguments.
* Passing all the arguments to the xdelta3 for decoder.
  ([MEN-5491](https://northerntech.atlassian.net/browse/MEN-5491))

##### Dependabot bumps

* Aggregated Dependabot Changelogs:
  * Bumps tests/unit/cmocka from `5a4b158` to `59f4792`.

      ```
      updated-dependencies:
      - dependency-name: tests/unit/cmocka
        dependency-type: direct:production
      ```
  * Bumps tests/unit/cmocka from `59f4792` to `6066c5c`.

      ```
      updated-dependencies:
      - dependency-name: tests/unit/cmocka
        dependency-type: direct:production
      ```

## mender-binary-delta 1.3.1

_Released 06.14.2022_

For internal consumption only.

## mender-binary-delta 1.3.0

_Released 09.28.2021_

### Changelogs

#### mender-binary-delta (1.3.0)

New changes in mender-binary-delta since 1.2.0:

* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Fix integer overflow bug in the Artifact creation logic, where the
  `rootfs_image_checksum` would get truncated through the use of the 32-bit
  interface for JSON values in the JSON libary used.
  ([MEN-4516](https://northerntech.atlassian.net/browse/MEN-4516))
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.
* Support for new grub-mender-grubenv tool names.
  ([MEN-3978](https://northerntech.atlassian.net/browse/MEN-3978))
* Aggregated Dependabot Changelogs:
  * Bumps tests/unit/cmocka from `314602b` to `5a4b158`.
  * Bumps [libntech](https://github.com/cfengine/libntech) from `4b59844` to `f49189e`.
    - [Release notes](https://github.com/cfengine/libntech/releases)
    - [Commits](https://github.com/cfengine/libntech/compare/4b598446c54fd9e784a6dd86be99a317c3531dff...f49189eba92f7a0c9bb37141a7a84dfca7d6ba75)
    ---
    updated-dependencies:
    - dependency-name: libntech
      dependency-type: direct:production
    ...


## mender-binary-delta 1.2.1

_Released 04.16.2021_

### Changelogs

#### mender-binary-delta (1.2.1)

New changes in mender-binary-delta since 1.2.0:

* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.
* Fix integer overflow bug in the Artifact creation logic, where the
`rootfs_image_checksum` would get truncated through the use of the 32-bit
interface for JSON values in the JSON libary used.
([MEN-4516](https://northerntech.atlassian.net/browse/MEN-4516))

## mender-binary-delta 1.2.0

_Released 01.11.2021_

### Changelogs

#### mender-binary-delta (1.2.0)

New changes in mender-binary-delta since 1.1.0:

* Improve error message when mender-artifact is not found.
([MEN-4044](https://northerntech.atlassian.net/browse/MEN-4044))
* Mender-binary-delta and its Artifact generator now supports
the new "Provides" fields for individial application software names.
([MEN-3483](https://northerntech.atlassian.net/browse/MEN-3483), [MEN-3484](https://northerntech.atlassian.net/browse/MEN-3484))
* The format of the Artifact checksum field has been changed
in mender-artifact 3.5.0, from `rootfs_image_checksum` to
`rootfs-image.checksum`, to conform to the namespaced "Provides"
fields. Mender-binary-delta now supports this new field. This should
not have any practical effect, but will cause meta data of delta
Artifacts to look different.
([MEN-3483](https://northerntech.atlassian.net/browse/MEN-3483), [MEN-3484](https://northerntech.atlassian.net/browse/MEN-3484))
* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://northerntech.atlassian.net/browse/MEN-4246))

## mender-binary-delta 1.1.2

_Released 16.04.2021_

#### mender-binary-delta (1.1.2)

New changes in mender-binary-delta since 1.1.0:

* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://northerntech.atlassian.net/browse/MEN-4246))
* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.

## mender-binary-delta 1.1.1

_Released 01.11.2021_

### Changelogs

#### mender-binary-delta (1.1.1)

New changes in mender-binary-delta since 1.1.0:

* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://northerntech.atlassian.net/browse/MEN-4246))

## mender-binary-delta 1.1.0

_Released 07.15.2020_

#### mender-binary-delta (1.1.0)

New changes in mender-binary-delta since 1.0.1:

* Make the CLI artifact-name argument optional
([MEN-2642](https://northerntech.atlassian.net/browse/MEN-2642))
* Now the binary delta tools supports depends and provides
([MEN-2642](https://northerntech.atlassian.net/browse/MEN-2642))
* Add the ability to write transitional artifacts
([MEN-2948](https://northerntech.atlassian.net/browse/MEN-2948))

## mender-binary-delta 1.0.1

_Released 12.06.2019_

### Changelogs

#### mender-binary-delta (1.0.1)

New changes in mender-binary-delta since 1.0.0:

* MEN-2928: Fix: Enable file-systems larger than approx 2-GiGs
([MEN-2928](https://northerntech.atlassian.net/browse/MEN-2928))

## mender-binary-delta 1.0.0

_Released 10.16.2019_

