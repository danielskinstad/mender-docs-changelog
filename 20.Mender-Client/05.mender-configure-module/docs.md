---
title: mender-configure-module
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-configure-module 1.1.4

_Released 02.17.2026_

### Changelogs

#### mender-configure-module (1.1.4)

New changes in mender-configure-module since 1.1.3:

##### Bug Fixes

* Updated path to LED on raspberrypi to allow for blinking LED
  demo.
  ([MEN-9002](https://northerntech.atlassian.net/browse/MEN-9002))
* Fixed an issue where passing either `on` or `off` to
  mender-demo-raspberrypi-led resulted in an invalid config error. The
  previous value for the trigger was `gpio` which is no longer valid.
  Set the LED config to `default-on` when passing `on` and `none` when passing
  off. ([MEN-9375](https://northerntech.atlassian.net/browse/MEN-9375))


## mender-configure-module 1.1.3

_Released 11.03.2025_

### Changelogs

#### mender-configure-module (1.1.3)

New changes in mender-configure-module since 1.1.2:

##### Bug Fixes

* Exit with returncode 0 in `mender-inventory-mender-configure`
  if no JWT token is obtained over D-Bus. This stops `mender-update` from logging
  errors from the inventory script before `mender-auth` is ready or if the
  device isn't accepted.
  ([MEN-8591](https://northerntech.atlassian.net/browse/MEN-8591))


## mender-configure-module 1.1.2

_Released 01.15.2024_

### Statistics

A total of 68 lines added, 55 removed (delta 13)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 5 (83.3%) |
| Josef Holzmayr | 1 (16.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 42 (61.8%) |
| Josef Holzmayr | 26 (38.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 6 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 68 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-configure-module (1.1.2)

New changes in mender-configure-module since 1.1.1:

##### Bug fixes

* make systemd installation systemd_unitdir aware


## mender-configure-module 1.1.1

_Released 08.19.2023_

### Statistics

A total of 1 lines added, 1 removed (delta 0)

| Developers with the most changesets | |
|---|---|
| Roberto Giovanardi | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Roberto Giovanardi | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-configure-module (1.1.1)

New changes in mender-configure-module since 1.1.0:

##### Features

* fix pyyaml dependency issue > 6.0
  ([QA-607](https://northerntech.atlassian.net/browse/QA-607))


## mender-configure-module 1.1.0

_Released 07.28.2023_

### Statistics

A total of 180 lines added, 97 removed (delta 83)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 14 (36.8%) |
| Ole Petter Orhagen | 8 (21.1%) |
| Fabio Tranchitella | 7 (18.4%) |
| Manuel Zedel | 4 (10.5%) |
| Peter Grzybowski | 2 (5.3%) |
| Krzysztof Jaskiewicz | 1 (2.6%) |
| Alf-Rune Siqveland | 1 (2.6%) |
| Kristian Amlie | 1 (2.6%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 67 (30.0%) |
| Ole Petter Orhagen | 56 (25.1%) |
| Manuel Zedel | 45 (20.2%) |
| Fabio Tranchitella | 44 (19.7%) |
| Alf-Rune Siqveland | 5 (2.2%) |
| Peter Grzybowski | 4 (1.8%) |
| Krzysztof Jaskiewicz | 1 (0.4%) |
| Kristian Amlie | 1 (0.4%) |

| Developers with the most lines removed | |
|---|---|
| Alf-Rune Siqveland | 4 (4.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 38 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 223 (100.0%) |

| Employers with the most hackers (total 8) | |
|---|---|
| Northern.tech | 8 (100.0%) |

### Changelogs



## mender-configure-module 1.0.4

_Released 06.14.2022_

For internal consumption only.

### Changelogs


## mender-configure-module 1.0.3

_Released 01.24.2022_

### Statistics

A total of 10 lines added, 7 removed (delta 3)

| Developers with the most changesets | |
|---|---|
| Fabio Tranchitella | 2 (50.0%) |
| Ole Petter Orhagen | 1 (25.0%) |
| Lluis Campos | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Fabio Tranchitella | 7 (70.0%) |
| Ole Petter Orhagen | 2 (20.0%) |
| Lluis Campos | 1 (10.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 10 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |


### Changelogs

New changes in mender-configure-module since 1.0.2:

* set default permissions to 0600 on device-config.json
  ([MEN-5357](https://northerntech.atlassian.net/browse/MEN-5357))

## mender-configure-module 1.0.2

_Released 09.28.2021_

### Statistics

A total of 5 lines added, 3 removed (delta 2)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 3 (75.0%) |
| Lluis Campos | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 4 (80.0%) |
| Lluis Campos | 1 (20.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 5 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

## Changelogs

#### mender-configure-module (1.0.2)

New changes in mender-configure-module since 1.0.1:

* Mute the `curl` request progress bar in the
  `mender-inventory-mender-configure` script.
  ([MEN-4949](https://northerntech.atlassian.net/browse/MEN-4949))


## mender-configure-module 1.0.1

_Released 07.14.2021_

### Statistics

A total of 39 lines added, 10 removed (delta 29)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 2 (66.7%) |
| Fabio Tranchitella | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Fabio Tranchitella | 22 (56.4%) |
| Lluis Campos | 17 (43.6%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 39 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |


### Changelogs

#### mender-configure-module (1.0.1)

New changes in mender-configure-module since 1.0.0:

* include the current JWT token in the reported config checksum
  ([MEN-4769](https://northerntech.atlassian.net/browse/MEN-4769))

## mender-configure-module 1.0.0

_Released 04.16.2021_

### Statistics

A total of 2388 lines added, 409 removed (delta 1979)

| Developers with the most changesets | |
|---|---|
| Fabio Tranchitella | 23 (46.0%) |
| Kristian Amlie | 20 (40.0%) |
| Lluis Campos | 6 (12.0%) |
| Krzysztof Jaskiewicz | 1 (2.0%) |

| Developers with the most changed lines | |
|---|---|
| Fabio Tranchitella | 1261 (49.2%) |
| Kristian Amlie | 953 (37.2%) |
| Lluis Campos | 332 (13.0%) |
| Krzysztof Jaskiewicz | 16 (0.6%) |

| Developers with the most lines removed | |
|---|---|
| Krzysztof Jaskiewicz | 8 (2.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 49 (98.0%) |
| RnDity | 1 (2.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 2546 (99.4%) |
| RnDity | 16 (0.6%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| RnDity | 1 (25.0%) |

### Changelogs

#### mender-configure-module (1.0.0)

* First release of mender-configure-module
