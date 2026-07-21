---
title: monitor-client
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## monitor-client 1.5.0 (2026-02-23)

### 1.5.0 - 2026-02-23

##### Bug Fixes

* Add user warning when possible message flood is detected.
  ([MEN-7216](https://northerntech.atlassian.net/browse/MEN-7216))

##### Features

* Add support for `version` argument in monitor ctl tool
  ([MEN-8249](https://northerntech.atlassian.net/browse/MEN-8249))

## monitor-client 1.4.4

_Released 02.17.2026_

### Changelogs

#### monitor-client (1.4.4)

New changes in monitor-client since 1.4.3:

##### Bug Fixes

* Removed curl verbose data from logs


## monitor-client 1.4.3

_Released 11.03.2025_

### Changelogs

#### monitor-client (1.4.3)

New changes in monitor-client since 1.4.2:

##### Bug Fixes

* Fix USB monitoring regex pattern to correctly match journalctl's format.
  ([MEN-8704](https://northerntech.atlassian.net/browse/MEN-8704))
* Fix log monitoring at startup, which was affecting Monitor USB disconnects
  tutorial from Get Started guide

  USB monitoring was not working with getting started because of 1) the log collecting commands
  were started only once at `mender-monitor` startup - if `mender-monitorctl enable` was called
  for a log collector that uses a command (as opposed to log file) while `mender-monitor` was
  running already, the command was not started, and 2) log regex was wrong for use with journalctl.
  ([MEN-8704](https://northerntech.atlassian.net/browse/MEN-8704))
* Fix an issue where short reads produced malformed entries for false positives
  ([MEN-8710](https://northerntech.atlassian.net/browse/MEN-8710))

##### Other

* Cleanup routine improvements to make it faster.
  ([MEN-8704](https://northerntech.atlassian.net/browse/MEN-8704))
* Add handshake to `pattern_expiration_sweep`, so that log monitoring command
  makes sure that it is working before sending data to it.
  ([MEN-8710](https://northerntech.atlassian.net/browse/MEN-8710))


## monitor-client 1.4.2

_Released 07.24.2025_

### Changelogs

#### monitor-client (1.4.2)

New changes in monitor-client since 1.4.1:

##### Bug Fixes

* Redirect USB disconnect log to journal instead of log file
  ([MEN-8348](https://northerntech.atlassian.net/browse/MEN-8348))


#### monitor-client (1.4.1)

New changes in monitor-client since 1.4.0:

##### Bug fixes

* Fix a bug in detection of flapping that can make the device
  erroneously trigger alerts continuously.
  ([MEN-8068](https://northerntech.atlassian.net/browse/MEN-8068))
* Incorrect value for STATUS_BY_LOG_NAME
  ([ME-474](https://northerntech.atlassian.net/browse/ME-474))


## monitor-client 1.4.0

_Released 12.18.2024_

### Changelogs

#### monitor-client (1.4.0)

New changes in monitor-client since 1.3.0:

##### Features

* Implemented an exponential backoff algorithm on 429 and 5xx
  HTTPS responses from the server.
  ([MEN-5783](https://northerntech.atlassian.net/browse/MEN-5783))


## monitor-client 1.3.1

_Released 03.27.2025_

### Changelogs

#### monitor-client (1.3.1)

New changes in monitor-client since 1.3.0:

##### Bug fixes

* Fix a bug in detection of flapping that can make the device
  erroneously trigger alerts continuously.
  ([MEN-8068](https://northerntech.atlassian.net/browse/MEN-8068))
* Incorrect value for STATUS_BY_LOG_NAME
  ([ME-474](https://northerntech.atlassian.net/browse/ME-474))


## monitor-client 1.3.0

_Released 07.28.2023_

### Statistics

A total of 202 lines added, 89 removed (delta 113)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 8 (66.7%) |
| Peter Grzybowski | 2 (16.7%) |
| Kristian Amlie | 1 (8.3%) |
| Fabio Tranchitella | 1 (8.3%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 74 (33.6%) |
| Kristian Amlie | 66 (30.0%) |
| Fabio Tranchitella | 49 (22.3%) |
| Lluis Campos | 31 (14.1%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 13 (14.6%) |
| Fabio Tranchitella | 3 (3.4%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 220 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### monitor-client (1.3.0)

New changes in monitor-client since 1.2.1:

##### Bug fixes

* do not remove the check for not built in subsystems.
  ([MEN-6559](https://northerntech.atlassian.net/browse/MEN-6559))


## monitor-client 1.2.1

_Released 09.25.2022_

### Changelogs

#### monitor-client (1.2.1)

New changes in monitor-client since 1.2.0:

##### Bug fixes

* `mender-monitord` detects not valid patterns when calling any log related checks. `mender-monitorctl` prevents creation of checks that lead to errors in pattern matching.
  ([MEN-5748](https://northerntech.atlassian.net/browse/MEN-5748))

##### Other

* Licenses are now available in the package, instead of only
  online. ([MEN-5517](https://northerntech.atlassian.net/browse/MEN-5517))


## monitor-client 1.2.0

_Released 06.14.2022_

### Statistics

A total of 168 lines added, 114 removed (delta 54)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 14 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 241 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 14 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 241 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### monitor-client (1.2.0)

New changes in monitor-client since 1.1.0:

##### Bug fixes

* Use and honour ALERT_OFFLINE_STORE_MAX_COUNT setting.
* Increasing read timeout in the pattern expiration worker.
* Clean the variables each time the main loop continues. This was a bug, which manifested itself only when a certain order of sourced files came to be. As we use find for gathering of the files, special cirtumstances must occur for it to be triggered.
  ([MEN-5508](https://northerntech.atlassian.net/browse/MEN-5508))
* Include log pattern and log path in the alert emails.
  ([MEN-5600](https://northerntech.atlassian.net/browse/MEN-5600))

##### Features

* Make the log subssytem general enough to be a base for any user-defined subsystem.
  ([MEN-5508](https://northerntech.atlassian.net/browse/MEN-5508))
* Use the core log subsystem to create a pseudo subsystem: dockerevents.
  ([MEN-5508](https://northerntech.atlassian.net/browse/MEN-5508))

##### Other

* Handle exiting commands in the streamline logs case.
* Do not alert when daemon is being shutdown.

  After the introduction of the proxy, on shutdown the device is always
  considered to be offline. That in combination with the aletrs storing
  and service monitoring means that all monitored services will report
  CRITICAL on the next boot. Those criticals will never disapear
  (without restarting a given service), since on boot everything
  is in an OK state again.

  When daemon is being shutdown, now we will not monitor any services.
* Return from monitor_send_alert immediately if shutdown is in progress.

  It is possible that during the shutdown we are in the middle of a check,
  in that case monitor_send_alert can be called while the daemon is being
  shutdown. This closes the possibility of sending the alerts at that time.
* Do not alert when log check is already in CRITICAL state.

  If log check is in the critical state: do not send the alert.
  This means that once the pattern is present in the logs,
  only one alert will be sent. Note: the behaviour can be further
  configured with LOG_PATTERN_EXPIRATION setting, to trigger
  OK/CRITICAL chain as needed.
  ([MEN-5458](https://northerntech.atlassian.net/browse/MEN-5458))
* dockerevents is moved away from examples directory, it is now based on the log subsystem.
  ([MEN-5508](https://northerntech.atlassian.net/browse/MEN-5508))


## monitor-client 1.1.0

_Released 01.24.2022_

### Changelogs

#### monitor-client (1.1.0)

New changes in monitor-client since 1.0.0:

* monitorctl: warn on non-existent command.
* Clean excessive warning from the periodical alert store check.
* Fix failure when sending many stored alerts. Previously, an attempt to send large local alert store could trigger `126 Argument list too long` error and  no alerts would be sent.
  ([MEN-5133](https://northerntech.atlassian.net/browse/MEN-5133))
* Correctly escape especial characters when saving alerts in the local store.
  ([MEN-5133](https://northerntech.atlassian.net/browse/MEN-5133))
* Move local store unlock calls away from the trap, which may lead to races
* monitorctl: report error and exit when enabling/disabling non available checks
  ([MEN-5190](https://northerntech.atlassian.net/browse/MEN-5190))
* monitorctl: Return the exit code properly and no output on successful execution. Previously monitorctl would always exit with code 0 even on errors
  ([MEN-5172](https://northerntech.atlassian.net/browse/MEN-5172))
* monitorctl: Fix the issue with enable, disable, delete and create commands not returning the exit code correctly, which in turn leads to improper exit code of monitorctl tool
  ([MEN-5172](https://northerntech.atlassian.net/browse/MEN-5172))
* Store configuration data on enabled checks.
  ([MEN-5185](https://northerntech.atlassian.net/browse/MEN-5185))
* Remove device_online check, treating all errors to reach the
  Mender server as "device is offline", saving the alerts in the store for
  later re-send.
  ([MEN-5216](https://northerntech.atlassian.net/browse/MEN-5216))
* Add a variable for permanent in-memory key-values for subsystems

  This is then used in the subsystems like so:

  subsystem=disk

  PERMANENT_STORAGE_FOR_DISK[LAST_ALARM]=OK

  or similar, which means now that every subsystem has a unified way of storing
  state data.
* Add example monitor implementation to the examples/monitors, and
  examples/subsystems directory. Install and uninstall them with the
  make (un)install-example-monitors targets in the Makefile. Enable them with the
  'enable-example-monitors' target. The added subsystems are a connectivity
  system, for HTTP HEAD requests to a given server on an optional interface. A
  container subsystem for monitoring container actions as given by docker events,
  and a subsystem for monitoring disk usage of an optional disk, and warn on a
  given treshold, if the disk starts filling up.
  ([MEN-5137](https://northerntech.atlassian.net/browse/MEN-5137))
* Remove records older than given time from alerts store.
  ([MEN-5336](https://northerntech.atlassian.net/browse/MEN-5336))
* Increase the log lines sent within alerts
  ([MEN-5361](https://northerntech.atlassian.net/browse/MEN-5361))
* Handle exiting commands in the streamline logs case.


## monitor-client 1.0.1

_Released 02.09.2022_

### Changelogs

#### monitor-client (1.0.1)

New changes in monitor-client since 1.0.0:

* monitorctl: warn on non-existent command.
* Clean excessive warning from the periodical alert store check.
* Fix failure when sending many stored alerts. Previously, an attempt to send large local alert store could trigger `126 Argument list too long` error and  no alerts would be sent.
  ([MEN-5133](https://northerntech.atlassian.net/browse/MEN-5133))
* Correctly escape especial characters when saving alerts in the local store.
  ([MEN-5133](https://northerntech.atlassian.net/browse/MEN-5133))
* Move local store unlock calls away from the trap, which may lead to races
* monitorctl: report error and exit when enabling/disabling non available checks
  ([MEN-5190](https://northerntech.atlassian.net/browse/MEN-5190))
* monitorctl: Return the exit code properly and no output on successful execution. Previously monitorctl would always exit with code 0 even on errors
  ([MEN-5172](https://northerntech.atlassian.net/browse/MEN-5172))
* monitorctl: Fix the issue with enable, disable, delete and create commands not returning the exit code correctly, which in turn leads to improper exit code of monitorctl tool
  ([MEN-5172](https://northerntech.atlassian.net/browse/MEN-5172))


## monitor-client 1.0.0

_Released 09.28.2021_

### Changelogs

#### monitor-client (1.0.0)

* First release of monitor-client
