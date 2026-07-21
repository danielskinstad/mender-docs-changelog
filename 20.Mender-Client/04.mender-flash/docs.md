---
title: mender-flash
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-flash 1.1.0 (2026-02-27)

### 1.1.0 - 2026-02-27

##### Bug Fixes

* Fixed handling of the '-f' short option for '--fsync-interval'

##### Features

* Two new CLI options are now supported:
  --write-everything to force write of all bytes instead of comparing blocks and only writing the ones that differ, and
  --fsync-interval to specify the interval (in bytes) after which the written bytes should be synced to the target device/file.
  ([MEN-7862](https://northerntech.atlassian.net/browse/MEN-7862))
* In-kernel copying utilizing the sendfile() and
  splice() syscalls to avoid user-space buffers and
  unnecessary context-switching is now used when possible.
  ([MEN-7862](https://northerntech.atlassian.net/browse/MEN-7862))

##### Other

* No dependencies are now needed (no submodules)
  and the builds are faster.
  ([MEN-7862](https://northerntech.atlassian.net/browse/MEN-7862))
* The binary is now smaller, less than 10 KiB big.
  ([MEN-7862](https://northerntech.atlassian.net/browse/MEN-7862))

## mender-flash 1.0.0

_Released 12.8.2023_

### Changelogs

#### mender-flash (1.0.0)

* First release of mender-flash


## mender-flash 1.0.1

_Released 10.17.2024_

### Changelogs

#### mender-flash (1.0.1)

New changes in mender-flash since 1.0.0:

##### Bug fixes

* Fix detection of UBI devices.
  ([MEN-7156](https://northerntech.atlassian.net/browse/MEN-7156))
* Fix overflow on 32-bit platforms when writing big files.
  ([MEN-7613](https://northerntech.atlassian.net/browse/MEN-7613))
