---
title: mender-connect
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-connect 2.3.2-build2

_Released 02.11.2026_

### Changelogs

#### mender-connect (2.3.2-build2)

New changes in mender-connect since 2.3.1:

##### Bug Fixes

* make StopShell function re-entrant by protecting stop channel
  ([MEN-9029](https://northerntech.atlassian.net/browse/MEN-9029))


## mender-connect 2.3.1

_Released 07.24.2025_

### Changelogs

#### mender-connect (2.3.1)

New changes in mender-connect since 2.3.0:

##### Bug Fixes

* Preserve group assignments by retrieving GIDs for users
  and adding them when executing a shell.
  ([ME-530](https://northerntech.atlassian.net/browse/ME-530))


#### mender-connect (2.3.0)

New changes in mender-connect since 2.2.1:

##### Bug fixes

* systemd: Always try restarting the client if it exits.

##### Features

* added back-off in connectionmanager
  ([MEN-5782](https://northerntech.atlassian.net/browse/MEN-5782))

##### Other

* --version no longer outputs the text "mender-connect version".
  ([MEN-6965](https://northerntech.atlassian.net/browse/MEN-6965))


## mender-connect 2.2.0

_Released 12.28.2023_

### Statistics

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 9 (50.0%) |
| Krzysztof Jaskiewicz | 3 (16.7%) |
| Andreas Henriksson | 2 (11.1%) |
| Roberto Giovanardi | 1 (5.6%) |
| Fabio Tranchitella | 1 (5.6%) |
| Kristian Amlie | 1 (5.6%) |
| Peter Grzybowski | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Krzysztof Jaskiewicz | 644 (71.6%) |
| Lluis Campos | 158 (17.6%) |
| Peter Grzybowski | 55 (6.1%) |
| Kristian Amlie | 28 (3.1%) |
| Andreas Henriksson | 9 (1.0%) |
| Fabio Tranchitella | 3 (0.3%) |
| Roberto Giovanardi | 2 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Fabio Tranchitella | 3 (1.1%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Lluis Campos | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 16 (88.9%) |
| andreas@fatal.se | 2 (11.1%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 890 (99.0%) |
| andreas@fatal.se | 9 (1.0%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 6 (85.7%) |
| andreas@fatal.se | 1 (14.3%) |

### Changelogs

#### mender-connect (2.2.0)

New changes in mender-connect since 2.1.1:

##### Bug fixes

* In Mender client v4.0, the `mender` binary has been split
  into `mender-update` and `mender-auth`. Modify `mender-connect` to call
  the right binary to trigger `check-update` and `send-inventory`
  ([MEN-6827](https://northerntech.atlassian.net/browse/MEN-6827))
* `mender-connect` systemd service can use either the old
  `mender-client` service or the new `mender-authd` service, which is the
  name of the authentication daemon of new Mender client. They are both
  kept as `Wants` and not `Require` so that `mender-connect` can run with
  either.
  ([MEN-6858](https://northerntech.atlassian.net/browse/MEN-6858))

##### Features

* build and test using the latest version of golang (1.21 today)
  ([QA-614](https://northerntech.atlassian.net/browse/QA-614))


## mender-connect 2.1.2

_Released 06.12.2024_

### Changelogs

#### mender-connect (2.1.2)

New changes in mender-connect since 2.1.1:

##### Bug fixes

* In Mender client v4.0, the `mender` binary has been split
  into `mender-update` and `mender-auth`. Modify `mender-connect` to call
  the right binary to trigger `check-update` and `send-inventory`
  ([MEN-6827](https://northerntech.atlassian.net/browse/MEN-6827))
* `mender-connect` systemd service can use either the old
  `mender-client` service or the new `mender-authd` service, which is the
  name of the authentication daemon of new Mender client. They are both
  kept as `Wants` and not `Require` so that `mender-connect` can run with
  either.
  ([MEN-6858](https://northerntech.atlassian.net/browse/MEN-6858))
* Stop shell after the ping/pong health check fails, so that
  the `mender-connect` can recover after disruption of connectivity.
  For already released versions of `mender-connect` the workaround is to
  force the stop of shells for expired sessions adding to the
  configuration options the fields:
  ```
    "Sessions": {
      "StopExpired": true,
      "ExpireAfterIdle": 600
    }
  ```
  Setting a limit for expiration high enough (10 minutes, above) so that it
  doesn't interfere with regular operations.
  See https://docs.mender.io/add-ons/mender-connect#remote-terminal-configuration
  ([MEN-6888](https://northerntech.atlassian.net/browse/MEN-6888))


## mender-connect 2.1.1

_Released 10.18.2023_

### Statistics

| Developers with the most changesets | |
|---|---|
| Andreas Henriksson | 1 (20.0%) |
| Lluis Campos | 1 (20.0%) |
| Krzysztof Jaskiewicz | 1 (20.0%) |
| Peter Grzybowski | 1 (20.0%) |
| Kristian Amlie | 1 (20.0%) |


| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 55 (57.9%) |
| Kristian Amlie | 28 (29.5%) |
| Krzysztof Jaskiewicz | 7 (7.4%) |
| Andreas Henriksson | 3 (3.2%) |
| Lluis Campos | 2 (2.1%) |


| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |


| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (80.0%) |
| andreas@fatal.se | 1 (20.0%) |


| Top lines changed by employer | |
|---|---|
| Northern.tech | 92 (96.8%) |
| andreas@fatal.se | 3 (3.2%) |


| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| andreas@fatal.se | 1 (20.0%) |

### Changelogs

#### mender-connect (2.1.1)

New changes in mender-connect since 2.1.0:

##### Bug fixes

* fix unstable unit test


## mender-connect 2.1.0

_Released 09.25.2022_

### Statistics

A total of 130 lines added, 20 removed (delta 110)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 4 (57.1%) |
| Uri Ishon | 1 (14.3%) |
| Fabio Tranchitella | 1 (14.3%) |
| Manuel Zedel | 1 (14.3%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 115 (88.5%) |
| Manuel Zedel | 8 (6.2%) |
| Uri Ishon | 5 (3.8%) |
| Fabio Tranchitella | 2 (1.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 6 (85.7%) |
| uishon@gmail.com | 1 (14.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 125 (96.2%) |
| uishon@gmail.com | 5 (3.8%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| uishon@gmail.com | 1 (25.0%) |

### Changelogs

#### mender-connect (2.1.0)

New changes in mender-connect since 2.0.2:

##### Features

* if the `/etc/shells` file does not exit, fall back to the default shell


## mender-connect 2.0.2

_Released 06.14.2022_

For internal consumption only.


## mender-connect 2.0.1

_Released 02.02.2022_

### Statistics

A total of 111 lines added, 16 removed (delta 95)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 2 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 111 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 111 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (2.0.1)

New changes in mender-connect since 2.0.0:

* fix: Global spawned shells count is not always decremented.


## mender-connect 2.0.0

_Released 01.24.2022_

### Statistics

A total of 572 lines added, 949 removed (delta -377)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 8 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 996 (100.0%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 377 (39.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 8 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 996 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (2.0.0)

New changes in mender-connect since 1.2.0:

* Deprecate configuration fields `ServerURL` , `Servers`,
  `ServerCertificate`, `ClientProtocol`, `HTTPSClient` and `SkipVerify`.
  The server configuration is obtained via D-Bus API, for which from
  Mender 3.2 onwards is a local proxy which uses `mender.conf` client
  settings to securely authenticate with the backend server, making the
  client settings in `mender-connect.conf` redundant.
  ([MEN-5203](https://northerntech.atlassian.net/browse/MEN-5203))
* Several robustness fixes around re-connection

  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://northerntech.atlassian.net/browse/MEN-5290))


## mender-connect 1.2.1

_Released 02.09.2022_

### Statistics

A total of 215 lines added, 306 removed (delta -91)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 2 (50.0%) |
| Lluis Campos | 2 (50.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 290 (72.3%) |
| Peter Grzybowski | 111 (27.7%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 186 (60.8%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 401 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.2.1)

New changes in mender-connect since 1.2.0:

* Several robustness fixes around re-connection
  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://northerntech.atlassian.net/browse/MEN-5290))
* fix: Global spawned shells count is not always decremented.


## mender-connect 1.2.0

_Released 07.14.2021_

### Statistics

A total of 2823 lines added, 957 removed (delta 1866)

| Developers with the most changesets | |
|---|---|
| Alf-Rune Siqveland | 8 (40.0%) |
| Ole Petter Orhagen | 5 (25.0%) |
| Peter Grzybowski | 4 (20.0%) |
| Manuel Zedel | 2 (10.0%) |
| Kristian Amlie | 1 (5.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 1949 (64.8%) |
| Alf-Rune Siqveland | 862 (28.7%) |
| Ole Petter Orhagen | 152 (5.1%) |
| Manuel Zedel | 42 (1.4%) |
| Kristian Amlie | 1 (0.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 20 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 3006 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

### Changelogs

#### mender-connect (1.2.0)

New changes in mender-connect since 1.1.0:

* stat(2) file path and verify conditions before starting upload
* Add option to pass src_path to file upload requests
* FIX: Filetransfer owner restrictions checks username not (optional) real-name
* A Fix for group and owner file transfer limits
* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://northerntech.atlassian.net/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://northerntech.atlassian.net/browse/MEN-4694))

## mender-connect 1.1.1

_Released 07.14.2021_

### Statistics

A total of 183 lines added, 47 removed (delta 136)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 3 (75.0%) |
| Peter Grzybowski | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 132 (72.1%) |
| Peter Grzybowski | 51 (27.9%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 183 (100.0%) |

| Employers with the most signoffs (total 0) | |
|---|---|

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.1.1)

New changes in mender-connect since 1.1.0:

* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://northerntech.atlassian.net/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://northerntech.atlassian.net/browse/MEN-4694))

## mender-connect 1.1.0

_Released 04.16.2021_

### Changelogs

#### mender-connect (1.1.0)

New changes in mender-connect since 1.0.0:

* Add remote triggers for Mender client's check-update and send-inventory
* [examples/mender-connect.conf] Remove unnecessary ServerURL
* Add handler for File Transfer protocol.
([MEN-4322](https://northerntech.atlassian.net/browse/MEN-4322))
* filetransfer: Add handler for fetching file and file info
* New feature: TCP and UDP port-forwarding
* stat(2) file path and verify conditions before starting upload
* Add option to pass src_path to file upload requests

## mender-connect 1.0.3

_Released 02.09.2022_

### Statistics

A total of 122 lines added, 428 removed (delta -306)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 3 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 428 (100.0%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 306 (71.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 428 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (1.0.3)

New changes in mender-connect since 1.0.2:

* Several robustness fixes around re-connection
  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://northerntech.atlassian.net/browse/MEN-5290))


## mender-connect 1.0.2

_Released 07.14.2021_

### Statistics

A total of 184 lines added, 47 removed (delta 137)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 2 (66.7%) |
| Peter Grzybowski | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 133 (72.3%) |
| Peter Grzybowski | 51 (27.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 184 (100.0%) |

| Employers with the most signoffs (total 0) | |
|---|---|

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.0.2)

New changes in mender-connect since 1.0.1:

* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://northerntech.atlassian.net/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://northerntech.atlassian.net/browse/MEN-4694))

## mender-connect 1.0.1

_Released 16.04.2021_

### Changelogs

#### mender-connect (1.0.1)

New changes in mender-connect since 1.0.0:

* [examples/mender-connect.conf] Remove unnecessary ServerURL


## mender-connect 1.0.0

_Released 01.20.2021_

### Changelogs

#### mender-connect (1.0.0)

* First release of mender-connect

