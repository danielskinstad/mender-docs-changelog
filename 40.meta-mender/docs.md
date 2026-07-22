---
title: meta-mender
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## meta-mender wrynose-v2026.07

### Changelogs

New changes in meta-mender since wrynose-v2026.06:

##### Bug Fixes

* Revert erroneous change to LICENCE checksum for mender-artifact_git recipe.
  Commit introducing the regression: 3a6807e8f5f06190472c7b6b2ef1ab46bff39cc5
* Ship esp32 mock interface in mender-orchestrator-support demo
  The demo mock-env now provides an esp32 interface under
  interfaces/v1. It is installed by install-mock-interfaces but was
  not listed in FILES, so do_package_qa failed with an
  installed-but-not-shipped error when building the demo image.
  ([MEN-9793](https://northerntech.atlassian.net/browse/MEN-9793))

##### Features

* Add recipes for mender-orchestrator and mender-orchestrator-support 0.6.0
  ([MEN-9793](https://northerntech.atlassian.net/browse/MEN-9793))
* Add recipes for mender-artifact 4.4.1.
  ([MEN-9793](https://northerntech.atlassian.net/browse/MEN-9793))

## meta-mender wrynose-v2026.06

### Changelogs

#### meta-mender (wrynose-v2026.06)

New changes in meta-mender since scarthgap-v2026.04:

##### Bug Fixes

* Copy grow-data template to B before sed substitution.
  Otherwise subsequent runs will not find the `@...@` markers in the
  already modified template in workdir and nothing gets updated.
  Fixes an issue were `mender-growfs-data` script is not updated after
  changing relevant `MENDER_*` variables unless we do a full sstate clean
  and rebuild.
* Fix installing folders to boot directory
* Fix PSEUDO_INCLUDE_PATHS in mender-bootstrap-artifact.bbclass
* Upgrade U-Boot to 2026.01 and Yocto LTS release Wrynose
* Replace cp -a with cp -R in mender-helpers.bbclass
* Add wrynose to meta-mender-qemu LAYERSERIES_COMPAT
* Add wrynose to remaining sublayer LAYERSERIES_COMPAT
* Use host strip for envtools in uboot auto-configure
* Use full ESP GUID instead of deprecated EF00 partition type
* Set CONFIG_BOOTCOUNT_ALTBOOTCMD for U-Boot 2025.04+
* Remove scarthgap from LAYERSERIES_COMPAT
* Migrate from WORKDIR to UNPACKDIR
* Remove S = WORKDIR/git from grub recipes
* Add destsuffix to Go recipe SRC_URI
* Use BPN in SRC_URI in `mender-wait-for-timesync` and
  `example-state-scripts` to fix fatal QA errors.
  ([MEN-9619](https://northerntech.atlassian.net/browse/MEN-9619))
* Fix U-Boot bootcount rollback being disabled on U-Boot 2025.04 and
  newer, where an empty CONFIG_BOOTCOUNT_ALTBOOTCMD overrode Mender's altbootcmd.
  ([MEN-9619](https://northerntech.atlassian.net/browse/MEN-9619))
* Fix devices booting with a 2011 clock on wrynose, which made server
  TLS fail with "certificate is not yet valid" until time sync.
  ([MEN-9619](https://northerntech.atlassian.net/browse/MEN-9619))
* Fix an issue where the version check for mender-gateway
  was too strict for binaries compiled with newer golang versions.

##### Features

* Add commercial recipe for mender-orchestrator
  ([MEN-7015](https://northerntech.atlassian.net/browse/MEN-7015))
* Add mender-orchestrator-support recipes
  ([MEN-7201](https://northerntech.atlassian.net/browse/MEN-7201))
* Add demo mock environment for mender-orchestrator
  ([MEN-8786](https://northerntech.atlassian.net/browse/MEN-8786))
* Added a new `MENDER_FEATURE`, `mender-orchestrator-install`,
  to make the installation of mender-orchestrator easier. `mender-orchestrator-install`
  will append mender-orchestrator, mender-orchestrator-support and default
  the Device tier to `system`.
  ([MEN-9052](https://northerntech.atlassian.net/browse/MEN-9052))
* Add support for main branches for commercial recipes
  ([MEN-9583](https://northerntech.atlassian.net/browse/MEN-9583))
* Set layer compatibility in meta-mender-ci to `wrynose`
* Add recipes for mender-orchestrator and mender-orchestrator-support 0.5.0
* Add recipes for mender-gateway 2.1.0
  ([QA-1634](https://northerntech.atlassian.net/browse/QA-1634))
* Added recipe for `mender` 5.0.5
* Added recipe for `mender-connect` 2.3.3

##### Other

* Added journal log collection at the end of acceptance test run
  ([QA-1099](https://northerntech.atlassian.net/browse/QA-1099))
* Remove recipe for `mender-artifact` 4.3.0
* Remove recipe for `mender-binary-delta` 1.4.0
* Remove recipe for `mender-binary-delta` 1.4.1
* Remove recipe for `mender-gateway` 1.1.0
* Remove recipe for `mender-artifact` 3.10.0
* Remove recipe for `mender-artifact` 3.10.1
* Remove recipe for `mender-artifact` 3.10.2
* Remove recipe for `mender-client` 3.5.0
* Remove recipe for `mender-client` 3.5.1
* Remove recipe for `mender-client` 3.5.2
* Remove recipe for `mender-client` 3.5.3
* Remove recipe for `mender-connect` 2.1.0
* Remove recipe for `mender-connect` 2.1.1
* Remove recipe for `mender-connect` 2.1.2
* Remove recipe for `grub-efi-precompiled` for GRUB v2.04
* Remove recipes for `mender-monitor` 1.3 series
* Remove recipes for `mender-gateway` 1.2 series
* Remove recipes for `mender-artifact` 3.11, 4.0 and 4.1 series
* Remove recipes for `mender` 4.0 series
* Remove recipes for `mender-connect` 2.2 series

## meta-mender scarthgap-v2026.07

### Changelogs

New changes in meta-mender since scarthgap-v2026.06:

##### Features

* Add recipe for mender-artifact 4.4.1.

## meta-mender scarthgap-v2026.06

### Changelogs

#### meta-mender (scarthgap-v2026.06)

New changes in meta-mender since scarthgap-v2026.04:

##### Bug Fixes

* Fix an issue where the version check for mender-gateway
  was too strict for binaries compiled with newer golang versions.

##### Features

* Add recipe for `mender` 5.0.5
* Add recipe for `mender-connect` 2.3.3
* Add recipes for `mender-gateway` 2.1.0
  ([QA-1634](https://northerntech.atlassian.net/browse/QA-1634))


## meta-mender scarthgap-v2026.04

### Changelogs

#### meta-mender (scarthgap-v2026.04)

New changes in meta-mender since scarthgap-v2025.11:

##### Bug Fixes

* Amend condition for "major upgrade warning"
  Correctly show the warning only when no preferred version is selected,
  regardless of the user setting with the explicit
  `PREFERRED_VERSION_mender` variable (recommended) or through an override.
  ([MEN-9094](https://northerntech.atlassian.net/browse/MEN-9094))
* Support new file output in do_check_config_efi_stub
* Extend list of mender variables
  ([MEN-5271](https://northerntech.atlassian.net/browse/MEN-5271))
* increase ssh server limits on connections for the testing QEMU image
  ([QA-472](https://northerntech.atlassian.net/browse/QA-472))
* Fix a SDK build issue.

##### Features

* Add new `meta-mender-extended` layer to group Mender
  components that have requirements beyond Poky's core layer.
  ([MEN-8739](https://northerntech.atlassian.net/browse/MEN-8739))
* Add `mender-container-modules` to provide
  `mender-docker-compose` package. To add the package to the build
  `meta-virtualization` layer is required and a bigger rootfs is
  recommended. Sample configuration:
  ```
  IMAGE_INSTALL:append = " mender-docker-compose"
  DISTRO_FEATURES:append = " virtualization"
  MENDER_STORAGE_TOTAL_SIZE_MB_DEFAULT = "2048"
  ```
  ([MEN-8739](https://northerntech.atlassian.net/browse/MEN-8739))
* Add image recipe for meta-mender-extended
  ([MEN-8871](https://northerntech.atlassian.net/browse/MEN-8871))
* Add virtualization DISTRO_FEATURE in meta-mender-extended conf
* Add a variable `MENDER_DOCKER_DATA_ROOT` that allows
  specifying Docker's `data-root`, i.e. the storage directory the Docker
  daemon will use.
  ([MEN-9089](https://northerntech.atlassian.net/browse/MEN-9089))
* Add mender-binary-delta_git.bb recipe
  ([QA-1178](https://northerntech.atlassian.net/browse/QA-1178))
* Add support for specifying MENDER_DEVICE_TIER
  in the mender conf.
  ([MEN-8650](https://northerntech.atlassian.net/browse/MEN-8650))
* Add `mender-client-version-inventory-script` recipe
  ([MEN-9018](https://northerntech.atlassian.net/browse/MEN-9018))
* Add package configuration `version-inventory-script`
  This new configuration is enabled by default from `mender-update` 5.1
  on, where the report of the `mender_client_version` inventory attribute
  is provided through an script.
  ([MEN-9018](https://northerntech.atlassian.net/browse/MEN-9018))
* Allow disabling strict dependency checks for
  `mender-client-version-inventory-script`. This makes it easier
  to cherry-pick the recipe to maintenance branches that have
  conflicting subcomponent versions. When disabled, the
  build will log a warning instead of failing if a conflict
  occurs, and the script will not be installed.
  ([MEN-9502](https://northerntech.atlassian.net/browse/MEN-9502))

##### Other

* Updating pre-build Grub 2.12 binary to version crosscompiled
  on Debian 12 instead of Debian 11.
* Port fix for handling rootfs parition with leading 0
* Add recipe for mender-artifact 4.3
  ([QA-1493](https://northerntech.atlassian.net/browse/QA-1493))
* Add recipe for mender-artifact 4.4
  ([QA-1552](https://northerntech.atlassian.net/browse/QA-1552))
* Add recipe for `mender` 5.0.4
* Add recipe for `mender-connect` 2.3.2
* Add recipe for `mender-configure` 1.1.4
* Add recipe for `mender-binary-delta` 1.5.3
* Add recipe for `mender-monitor` 1.4.4
* Add recipes for Mender Client 6.0.0
  * `mender-client-version-inventory-script` 6.0.0
  * `mender` 5.1.0
  * `mender-connect` 3.0.0
  * `mender-flash` 1.1.0
  * `mender-monitor` 1.5.0
  ([QA-1538](https://northerntech.atlassian.net/browse/QA-1538))


## meta-mender scarthgap-v2025.11

### Changelogs

#### meta-mender (scarthgap-v2025.11)

New changes in meta-mender since scarthgap-v2025.09:

##### Bug Fixes

* Fix image name for custom WIC imager
* Fix a circular dependency in uboot recipe
* Fix an invalid condition check when generating
  fw_env.config.default.
* Add missing `curl` dependency to `mender-monitor` recipes
  ([MEN-8986](https://northerntech.atlassian.net/browse/MEN-8986))
* Clear warning on `mender-migrate-configuration`

##### Other

* Add recipe for `mender-artifact` 4.1.1
* Add recipe `mender` 5.0.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-binary-delta` 1.5.2
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-configure` 1.1.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-monitor` 1.4.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* **Warning**: Forced upgrade to `mender` v5 when using default
  versions. There was an oversight at the time of releasing `mender` 5.0.2
  in `scarthgap` which, in effect, sets the default `mender` recipe for
  the build to the v5 series, forcing a major upgrade on users that did
  not pin `mender` to an specific version or series. This change adds a
  warning. A revert was considered but deemed more risky, as forcing a
  downgrade is a known path for breakage
  ([MEN-8977](https://northerntech.atlassian.net/browse/MEN-8977))


## meta-mender scarthgap-v2025.09

### Changelogs

#### meta-mender (scarthgap-v2025.09)

New changes in meta-mender since scarthgap-v2025.07:

##### Bug Fixes

* mender-part-images handling of inactive partition


## meta-mender scarthgap-v2025.07

### Changelogs

#### meta-mender (scarthgap-v2025.07)

New changes in meta-mender since scarthgap-v2025.04:

* Add recipe for `mender-artifact` 4.1.0
* Add recipe for `mender` 5.0.2
* Add recipe for `mender-connect` 2.3.1
* Add recipe for `mender-monitor` 1.4.2


#### meta-mender (scarthgap-v2025.04)

New changes in meta-mender since scarthgap-v2024.12:

##### Bug fixes

* Restore GRUB integration for ARMv7 boards (Beaglebone Black)
  ([MEN-7854](https://northerntech.atlassian.net/browse/MEN-7854))
* Fixes an issue with Mender GRUB integration when using rootfs
  partitions definitions with leading `0` (ie partition `02`) and the GRUB
  integration was not correctly doing integers comparisons.
  ([ME-458](https://northerntech.atlassian.net/browse/ME-458))

##### Features

* Support setting the u-boot redundant environment in a
  separate storage with the variable
  `MENDER_UBOOT_MMC_ENV_LINUX_DEVICE_PATH_REDUND`. This feature is
  backwards compatible.

##### Other

* Add recipe for `grub-efi-precompiled` for GRUB v2.12
  ([MEN-7854](https://northerntech.atlassian.net/browse/MEN-7854))
* Prevent secondary rootfs from being mounted by udev-extraconf.
* Add recipe for `mender` 4.0.7
* Add recipe for `mender` 5.0.1
* Add recipe for `mender-binary-delta` 1.5.1
* Add recipe for `mender-monitor` 1.3.1
* Add recipe for `mender-monitor` 1.4.1


## meta-mender scarthgap-v2024.12

### Changelogs

#### meta-mender (scarthgap-v2024.12)

New changes in meta-mender since scarthgap-v2024.08:

##### Bug fixes

* finish fixing persistent machine id support

  Commit bca6bf7 attempted to fix the issue, but some references were
  overlooked. This commit addresses the rest.
* package artifact-verify-key.pem in mender-update
  ([MEN-7204](https://northerntech.atlassian.net/browse/MEN-7204))
* guard installation of systemd with mender-systemd feature
* Fixes parsing error with Mender disabled

##### Features

* add mender-prepopulate-inactive-partition feature

  Add mender-prepopulate-inactive-partition MENDER_FEATURE.
  Disabled by default for more efficient compression, it can be
  enabled to have the inactive partition populated with the same
  contents of the active one.

  This allows to check the bootloader integrations (A/B switching,
  A/B update, A/B rollback) directly on the generated images
  without additional modifications or processing.

##### Other

* Add recipe for `mender-flash` 1.0.1
* Add recipe for `mender-flash` 1.0.2
* Add recipe for `mender` 4.0.5
* Add recipe for `mender-artifact` 3.11.3
* Add recipe for `mender-gateway` 1.2.1
* Add recipe for `mender` 5.0.0. This recipe is set with
  `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it on
  your build.
* Add recipe for `mender-gateway` 2.0.0. This recipe is set
  with `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it
  on your build.
* Add recipe for `mender-connect` 2.3.0
* Add recipe for `mender-artifact` 4.0.0. This recipe is set
  with `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it
  on your build.
* Add recipe for `mender-monitor` 1.4.0
* Add recipe for `mender` 4.0.6


## meta-mender scarthgap-v2024.08

### Changelogs

#### meta-mender (scarthgap-v2024.08)

New changes in meta-mender since scarthgap-v2024.07:

##### Bug fixes

* persistent machine id support files renamed

##### Other

* Add Mender client 4.0.4 recipe.


## meta-mender scarthgap-v2024.07

_Released: 07.03.2024_

### Changelogs

#### meta-mender (scarthgap-v2024.07)

New changes in meta-mender since kirkstone-v2024.06:

##### Bug fixes

* remove splash IMAGE_FEATURE from demo layer
* move test specific settings from demo layer to tests
* use gitsm:// fetcher for mender-client_git
* core: add Upstream-Status to U-Boot patches
* Fix package error for `mender` 4.0.x series when building
  with usrmerge enabled
* meta-mender-demo: use /bin/sh as MENDER_CONNECT_SHELL
* meta-mender-ci: resolve usrmerge conflict

##### Features

* Add the `mender` recipe in
  `meta-mender-core/recipes/mender/mender-client/` while still keeping
  support for the old golang client builds. The new `mender` recipe
  creates two packages.  `mender-auth` and `mender-update` to provide
  the C++ implementations of the given functionality.

  The default is the C++ client.

  The given client
  implementation can be chosen using the Yocto `PREFERRED_PROVIDER` and
  `PREFERRED_RPROVIDER` variables, by using the 'mender' prefix for the
  C++ client, and 'mender-client' for the Golang client. For example
  like this:
  ```
  PREFERRED_PROVIDER_mender-native = "mender-client-native"
  PREFERRED_RPROVIDER_mender-auth = "mender-client"
  PREFERRED_RPROVIDER_mender-update = "mender-client"
  ```
  Remove `-client` to go from the Golang to the C++ implementation. Note
  that you should always set all of them.
* Add a MENDER_WATCHDOG_SEC variable to control the hardware watchdog
  timeout seconds in the mender-updated systemd service file.
* MENDER_ARTIFACT_PROVIDES(_GROUP), MENDER_ARTIFACT_DEPENDS(_GROUPS), and MENDER_ARTIFACT_NAME(_DEPENDS) variables have been supplemented with new "..._BOOTSTRAP" variables whose values will be added to the original variables to build the arguments passed to mender-artifact for the bootstrap artifact
* Add support to create mender artifact for UEFI capsule
* Enable UEFI capsule artifact generation
* Set layer compatibility to `scarthgap`

##### Other

* Remove recipes pre Mender 3.3.x, not supported anymore.
* Remove recipes from Mender 3.4.x, not supported anymore.
* Standardize on new names that follow the C++ client rewrite.

  The build component is now called `mender` instead of `mender-client`,
  because it contains the two independent `mender-auth` and
  `mender-update` runtime components. Other recipes should either use
  `DEPENDS = "mender"` for a build time dependency, or
  `RDEPENDS:${PN} = "mender-auth | mender-update"` for a runtime
  dependency.
* The `mender-install` and `mender-install-ubi`
  Mender features have been removed. Do not use them in
  `MENDER_FEATURES` variables, but instead one of the alternatives (see
  Features under Yocto section in the Mender documentation).
* Remove mender 3.99 alpha recipe.
* Remove recipes pre Mender 3.6.x, not supported anymore.
* meta-mender-core: remove unused u-boot patch
* raspberrypi: refresh u-boot patch
* core: remove unneeded u-boot patch
* refresh u-boot patches for 2023.01
* remove meta-mender-raspberrypi(-demo)
* Enabling systemd as init manager is no longer done
  automatically by the meta-mender layer. In order to re-enable it, put
  `INIT_MANAGER = "systemd"` in your `local.conf` file. Alternatively,
  use `MENDER_FEATURES_DISABLE = "mender-systemd"`, but be aware that
  this can break daemon mode.


## meta-mender kirkstone-v2026.04

### Changelogs

#### meta-mender (kirkstone-v2026.04)

New changes in meta-mender since kirkstone-v2025.11:

##### Bug Fixes

* Amend condition for "major upgrade warning"
  Correctly show the warning only when no preferred version is selected,
  regardless of the user setting with the explicit
  `PREFERRED_VERSION_mender` variable (recommended) or through an override.
  ([MEN-9094](https://northerntech.atlassian.net/browse/MEN-9094))
* Support new file output in do_check_config_efi_stub
* Extend list of mender variables
  ([MEN-5271](https://northerntech.atlassian.net/browse/MEN-5271))
* Increase ssh server limits on connections for the testing QEMU image
  ([QA-472](https://northerntech.atlassian.net/browse/QA-472))
* Fix a SDK build issue.
* Add python3-docker-compose and python3-distutils to RDEPENDS
  ([MEN-9603](https://northerntech.atlassian.net/browse/MEN-9603))
* Add mender-container-modules patch to fix an issue
  where docker-compose v1 can't find manifest files for a composition
  because we don't cd into the manifest directory.
  ([MEN-9641](https://northerntech.atlassian.net/browse/MEN-9641))

##### Features

* Add support for specifying MENDER_DEVICE_TIER in the mender conf.
  ([MEN-8650](https://northerntech.atlassian.net/browse/MEN-8650))
* Add `mender-client-version-inventory-script` recipe.
  ([MEN-9018](https://northerntech.atlassian.net/browse/MEN-9018))
* Add package configuration `version-inventory-script`
  This new configuration is enabled by default from `mender-update` 5.1
  on, where the report of the `mender_client_version` inventory attribute
  is provided through a script.
  ([MEN-9018](https://northerntech.atlassian.net/browse/MEN-9018))
* Allow disabling strict dependency checks for
  mender-client-version-inventory-script. This makes it easier
  to cherry-pick the recipe to maintenance branches that have
  conflicting subcomponent versions. When disabled, the
  build will log a warning instead of failing if a conflict
  occurs, and the script will not be installed.
  ([MEN-9502](https://northerntech.atlassian.net/browse/MEN-9502))
* Add new `meta-mender-extended` layer to group Mender
  components that have requirements beyond Poky's core layer.
  ([MEN-8739](https://northerntech.atlassian.net/browse/MEN-8739))
* Add `mender-container-modules` to provide
  `mender-docker-comopse` package. To add the package to the build
  `meta-virtualization` layer is required and a bigger rootfs is
  recommended. Sample configuration:
  ```
  IMAGE_INSTALL:append = " mender-docker-compose"
  DISTRO_FEATURES:append = " virtualization"
  MENDER_STORAGE_TOTAL_SIZE_MB_DEFAULT = "2048"
  ```
  ([MEN-8739](https://northerntech.atlassian.net/browse/MEN-8739))
* Add image recipe for meta-mender-extended
  ([MEN-8871](https://northerntech.atlassian.net/browse/MEN-8871))
* Add virtualization DISTRO_FEATURE in meta-mender-extended conf
* Add a variable `MENDER_DOCKER_DATA_ROOT` that allows
  specifying Docker's `data-root`, i.e. the storage directory the Docker
  daemon will use.
  ([MEN-9089](https://northerntech.atlassian.net/browse/MEN-9089))

##### Other

* Add mender-binary-delta_git.bb recipe
  ([QA-1178](https://northerntech.atlassian.net/browse/QA-1178))
* Add recipe for `mender` 5.0.4
* Add recipe for `mender-connect` 2.3.2
* Add recipe for `mender-configure` 1.1.4
* Add recipe for `mender-binary-delta` 1.5.3
* Add recipe for `mender-monitor` 1.4.4
* Add recipes for Mender Client 6.0.0
  * `mender-client-version-inventory-script` 6.0.0
  * `mender` 5.1.0
  * `mender-connect` 3.0.0
  * `mender-flash` 1.1.0
  * `mender-monitor` 1.5.0
  ([QA-1538](https://northerntech.atlassian.net/browse/QA-1538))


## meta-mender kirkstone-v2025.11

### Changelogs

#### meta-mender (kirkstone-v2025.11)

New changes in meta-mender since kirkstone-v2025.09:

##### Bug Fixes

* Clear warning on `mender-client-migrate-configuration`
* Fix image name for custom WIC imager
* Fix a circular dependency in uboot recipe
* Fix an invalid condition check when generating
  fw_env.config.default.
* Add missing `curl` dependency to `mender-monitor` recipes
  ([MEN-8986](https://northerntech.atlassian.net/browse/MEN-8986))

##### Other

* Add recipe `mender` 5.0.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-binary-delta` 1.5.2
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-configure` 1.1.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* Add recipe `mender-monitor` 1.4.3
  ([MEN-8870](https://northerntech.atlassian.net/browse/MEN-8870))
* **Warning**: Forced upgrade to `mender` v5 when selecting
  `mender` recipe for the client provider but keeping default versions.
  There was an oversight at the time of releasing `mender` 5.0.2 in
  `kirkstone` which, in effect, sets the default `mender` recipe for
  builds using `mender` provider to the v5 series, forcing a major upgrade
  on users that did select `mender` for the client provider and did not
  pin `mender` to an specific version or series. This change adds a
  warning. A revert was considered but deemed more risky, as forcing a
  downgrade is a known path for breakage
  ([MEN-8977](https://northerntech.atlassian.net/browse/MEN-8977))


## meta-mender kirkstone-v2025.09

### Changelogs

#### meta-mender (kirkstone-v2025.09)

New changes in meta-mender since kirkstone-v2025.07:

##### Bug Fixes

* mender-part-images handling of inactive partition


## meta-mender kirkstone-v2025.07

### Changelogs

#### meta-mender (kirkstone-v2025.07)

New changes in meta-mender since kirkstone-v2025.04:

* Add recipe for `mender` 5.0.2
* Add recipe for `mender-connect` 2.3.1
* Add recipe for `mender-monitor` 1.4.2


#### meta-mender (kirkstone-v2025.04)

New changes in meta-mender since kirkstone-v2024.12:

##### Bug fixes

* Fixes an issue with Mender GRUB integration when using rootfs
  partitions definitions with leading `0` (ie partition `02`) and the GRUB
  integration was not correctly doing integers comparisons.
  ([ME-458](https://northerntech.atlassian.net/browse/ME-458))

##### Features

* add mender-prepopulate-inactive-partition feature

  Add mender-prepopulate-inactive-partition MENDER_FEATURE.
  Disabled by default for more efficient compression, it can be
  enabled to have the inactive partition populated with the same
  contents of the active one.

  This allows to check the bootloader integrations (A/B switching,
  A/B update, A/B rollback) directly on the generated images
  without additional modifications or processing.

##### Other

* Prevent secondary rootfs from being mounted by udev-extraconf.
* Add recipe for `mender` 4.0.7
* Add recipe for `mender` 5.0.1
* Add recipe for `mender-binary-delta` 1.5.1
* Add recipe for `mender-monitor` 1.3.1
* Add recipe for `mender-monitor` 1.4.1


## meta-mender kirkstone-v2024.12

### Changelogs

#### meta-mender (kirkstone-v2024.12)

New changes in meta-mender since kirkstone-v2024.08:

##### Bug fixes

* package artifact-verify-key.pem in mender-update
  ([MEN-7204](https://northerntech.atlassian.net/browse/MEN-7204))
* guard installation of systemd with mender-systemd feature
* Fixes parsing error with Mender disabled

##### Other

* Add recipe for `mender-flash` 1.0.1
* Add recipe for `mender-flash` 1.0.2
* Add recipe for `mender` 4.0.5
* Add recipe for `mender-artifact` 3.11.3
* Add recipe for `mender-gateway` 1.2.1
* Add recipe for `mender` 5.0.0. This recipe is set with
  `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it on
  your build.
* Add recipe for `mender-gateway` 2.0.0. This recipe is set
  with `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it
  on your build.
* Add recipe for `mender-connect` 2.3.0
* Add recipe for `mender-artifact` 4.0.0. This recipe is set
  with `DEFAULT_PREFERENCE = "-1"`. Use `PREFERRED_VERSION` to select it
  on your build.
* Add recipe for `mender-monitor` 1.4.0
* Add recipe for `mender` 4.0.6


## meta-mender kirkstone-v2024.08

### Changelogs

#### meta-mender (kirkstone-v2024.08)

New changes in meta-mender since kirkstone-v2024.06:

##### Features

* MENDER_ARTIFACT_PROVIDES(_GROUP), MENDER_ARTIFACT_DEPENDS(_GROUPS), and MENDER_ARTIFACT_NAME(_DEPENDS) variables have been supplemented with new "..._BOOTSTRAP" variables whose values will be added to the original variables to build the arguments passed to mender-artifact for the bootstrap artifact

##### Other

* Add Mender client 4.0.4 recipe.


## meta-mender kirkstone-v2024.06

_Released: 06.17.2024_

### Changelogs

#### meta-mender (kirkstone-v2024.06)

New changes in meta-mender since kirkstone-v2024.04:

##### Bug fixes

* Fix typo in fstab options for extra partitions.
* Set correct systemd installation dir.

  This is important when usrmerge is enabled, which changes the systemd
  install location.
* add coreutils as a runtime dependency for Mender monitor
* Fix autogeneration of `mender-binary-delta.conf` so
  that the user value for `MENDER_FLASH` is respected, instead of the
  previously wrongly hard-coded value of `mender-flash`. Without this
  fix it is impossible to omit `mender-flash` from UBI systems, even
  when `ubiupdatevol` would have been sufficient.

##### Features

* Add MENDER_EXTRA_PARTS_MOUNT_LOCATIONS variable

##### Other

* Remove `mender-app-update-module` git recipe. Due to the
  dependencies on `virtualization` this module has not been fully
  integrated in `meta-mender-core` layer. Use the one from
  [`meta-mender-community`
  instead](https://github.com/mendersoftware/meta-mender-community/blob/master/meta-mender-update-modules/dynamic-layers/virtualization/recipes-mender/mender-update-modules/mender-app-update_git.bb).
* Add Mender client 3.5.3 recipe.
* Add mender-connect 2.1.2 recipe.
* Add Mender client 4.0.3 recipe.


## meta-mender kirkstone-v2024.04

_Released: 04.26.2024_

### Changelogs

#### meta-mender (kirkstone-v2024.04)

New changes in meta-mender since kirkstone-v2023.12:

##### Bug fixes

* Fix the install path for the D-Bus interface files shipped in
  `mender-client-dev` package. It was `$(datadir)/dbus-1/interface` but it
  should be `interfaces` instead.
* Fix mender-client version 3.5.2 for Kirkstone
* pass prefix and systemd_unitdir to mender-configure installation
* Fix broken Git builds for mender-client < 4.0.
* remove "mender.bmap" IMAGE_FSTYPE
* Remove `has_journal` flag from mkfs.ext4 when
  `read-only-rootfs` flag is enabled, which causes issues in certain
  configurations. Specifically it solves these problems:
  * Checksum is not stable which can cause issues with binary delta
    updates. This is an in-memory effect only, the physical checksum on
    disk is unaffected.
  * Mender-snapshot can generate corrupted rootfs dumps, for the same
    reason as the previous point.
* Fix rare mounting errors like these:
  ```
  kernel: EXT4-fs error (device mmcblk0p6): ext4_mb_generate_buddy:1141: group 35, block bitmap and bg descriptor inconsistent: 32766 vs 32768 free clusters
  ```
  ([MEN-6027](https://northerntech.atlassian.net/browse/MEN-6027))
* Fix path to mender-client-systemd-machine-id service/scripts

##### Features

* add recipe for Application Updates Module
  ([MEN-6084](https://northerntech.atlassian.net/browse/MEN-6084))
* Add the `mender` recipe in
  `meta-mender-core/recipes/mender/mender-client/` while still keeping
  support for the old golang client builds. The new `mender` recipe
  creates two packages, `mender-auth` and `mender-update`, to provide
  the C++ implementations of the given functionality. The given client
  implementation can be chosen using the Yocto `PREFERRED_PROVIDER` and
  `PREFERRED_RPROVIDER` variables, by using the 'mender' prefix for the
  C++ client, and 'mender-client' for the Golang client. For example
  like this:
  ```
  PREFERRED_PROVIDER_mender-native = "mender-client-native"
  PREFERRED_RPROVIDER_mender-auth = "mender-client"
  PREFERRED_RPROVIDER_mender-update = "mender-client"
  ```
  Remove `-client` to go from the Golang to the C++ implementation. Note
  that you should always set all of them. The default on this branch is
  the Golang client.
* Add `mender-flash` git recipe
* `mender-update` recommends `mender-flash`, which is
  the standalone tool used for rootfs updates.
* Add recipe for mender-flash-1.0.0.

  This tool will be used by Mender client 4.0.0 and later to do
  rootfs-image updates.
  ([MEN-6279](https://northerntech.atlassian.net/browse/MEN-6279))
* Add `MENDER_FLASH_TOOL` variable to mender-binary-delta.

  This has no effect for mender-binary-delta versions older than 1.5.
  ([MEN-6774](https://northerntech.atlassian.net/browse/MEN-6774))

##### Other

* Automatically define `mender-auth-install` and
  `mender-update-install` when `mender-client-install` is set. The
  two former features have been added to accomodate the new Mender
  client written in C++, where the auth and update functionality has
  been split into separate daemons which can be installed individually.
* The mender update client 4.0 and later comes with a
  `rootfs-image` Update Module, instead of having this functionality
  built in.
* Standardize on new names that follow the C++ client rewrite.
  The build component is now called `mender` instead of `mender-client`,
  because it contains the two independent `mender-auth` and
  `mender-update` runtime components. Other recipes should either use
  `DEPENDS = "mender"` for a build time dependency, or
  `RDEPENDS:${PN} = "mender-auth | mender-update"` for a runtime
  dependency.
* mender-client: Move DBus xml files to dev package.

  They do not influence production, and thus they belong in the dev
  package.
* In `meta-mender-demo` layer, `mender-update` recommends
  `mender-snapshot`, which an standalone tool to make snapshots of a live
  rootfs image. Prior to v4.0, this functionality used to be part of the
  core `mender` binary.
* Add recipe for `mender` 4.0.0
* Add recipe for `mender-artifact` 3.11.1
* Add recipe for `mender-configure` 1.1.2
* Add recipe for `mender-snapshot` 1.0.0
* Add recipe for `mender` 4.0.1
* Add recipe for `mender-artifact` 3.11.2
* Add recipe for `mender-connect` 2.2.1
* Add recipe for `mender-binary-delta` 1.5.0
* Add recipe for `mender` 4.0.2


## meta-mender kirkstone-v2023.12

_Released: _01.01.2024_

### Changelogs

#### meta-mender (kirkstone-v2023.12)

New changes in meta-mender since kirkstone-v2023.10:

##### Features

* add recipes for the client components in Mender 3.7.0


## meta-mender kirkstone-v2023.10

_Released: 10.01.2023_

### Changelogs

#### meta-mender (kirkstone-v2023.10)

New changes in meta-mender since kirkstone-v2023.08:

##### Bug fixes

* mv image files instead of install, to avoid corrupting the image.

##### Features

* add recipe for Application Updates Module
  ([MEN-6084](https://northerntech.atlassian.net/browse/MEN-6084))

##### Other

* Add recipe for mender-connect 2.1.1
* Add recipe for mender-artifact 3.10.2


## meta-mender kirkstone-v2023.08

_Released: 09.05.2023_

### Changelogs

#### meta-mender (kirkstone-v2023.08)

New changes in meta-mender since kirkstone-v2023.03:

##### Bug fixes

* boot-partition-devicetree use proper SPDX License GPL-2.0-only
* wic-tools does not need grub when using uboot
* Replace gpt partition type 8300 with full UUID
* mender-configure: Don't break if libdir is set to `lib64`.

##### Features

* Make the build succeed if gateway examples aren't present

##### Other

* Add recipe for mender-client 3.5.1
* Add recipe for mender-artifact 3.10.1
* Add recipe for mender-configure 1.1.0
* Add recipe for mender-monitor 1.3.0


## meta-mender kirkstone-v2023.03

_Released: 03.10.2023_

### Statistics

A total of 3 lines added, 3 removed (delta 0)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 3 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### meta-mender (kirkstone-v2023.03)

New changes in mender-client since kirkstone-v2023.02:

##### Bug fixes

* Add mender-client 3.3.2 recipe.


## meta-mender kirkstone-v2023.02

_Released: 02.24.2023_

### Statistics

A total of 686 lines added, 376 removed (delta 310)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 15 (34.1%) |
| Lluis Campos | 12 (27.3%) |
| Ole Petter Orhagen | 6 (13.6%) |
| Marek Belisko | 6 (13.6%) |
| Clément Péron | 2 (4.5%) |
| Justin Verble | 1 (2.3%) |
| Fabio Tranchitella | 1 (2.3%) |
| Drew Moseley | 1 (2.3%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 351 (48.7%) |
| Kristian Amlie | 250 (34.7%) |
| Marek Belisko | 47 (6.5%) |
| Clément Péron | 40 (5.5%) |
| Ole Petter Orhagen | 25 (3.5%) |
| Drew Moseley | 4 (0.6%) |
| Justin Verble | 3 (0.4%) |
| Fabio Tranchitella | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Clément Péron | 24 (6.4%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Ole Petter Orhagen | 1 (50.0%) |
| Lluis Campos | 1 (50.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 34 (77.3%) |
| open-nandra | 6 (13.6%) |
| peron.clem@gmail.com | 2 (4.5%) |
| Election Systems & Software | 1 (2.3%) |
| drew@moseleynet.net | 1 (2.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 627 (87.0%) |
| open-nandra | 47 (6.5%) |
| peron.clem@gmail.com | 40 (5.5%) |
| drew@moseleynet.net | 4 (0.6%) |
| Election Systems & Software | 3 (0.4%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 8) | |
|---|---|
| Northern.tech | 4 (50.0%) |
| open-nandra | 1 (12.5%) |
| peron.clem@gmail.com | 1 (12.5%) |
| drew@moseleynet.net | 1 (12.5%) |
| Election Systems & Software | 1 (12.5%) |

### Changelogs

#### meta-mender (kirkstone-v2023.02)

New changes in meta-mender since kirkstone-v2022.10:

##### Bug fixes

* Add missing licenses checksums, set right preference, and
  correct dependencies syntax for mender-client 3.3.1 recipe
* Add missing licenses checksums, set right preference, and
  add missing license for mender-artifact 3.8.1 recipe
* Fix issues found during testing when mender-partuuid is not set
* udev: Rename blacklist to ignorelist.
* grub-mender-grubenv: Add lock file to prevent data races
  when accessing boot environment concurrently.
* grub-mender-grubenv: Fail execution if both environments
  are corrupt.
* grub-mender-grubenv: Recompute checksum after restoring
  environment (new versions of grub-editenv add extra data).
* mender-qemu: Don't leave temp files around after quitting.
* Remove grub.efi resource files using pseudo.

##### Features

* Update UUID for all extra partitions
* Update fstab swap entry with UUID when feature is enabled
* Added variables for extra and swap parts UUID
* Mender Artifacts include now information about the installed
  Update Modules in the image. Specifically, the Artifacts `provide` two
  pair of keys for each module:
  `rootfs-image.update-module.<UPDATE_MODULE>.version` and
  `rootfs-image.update-module.<UPDATE_MODULE>.mender_update_module`. This
  also applies to the bootstrap Artifact which gets installed on first
  boot. ([MEN-5845](https://tracker.mender.io/browse/MEN-5845))

##### Other

* Add recipe for mender-client 3.5.0
* Add recipe for mender-artifact 3.10.0
* Add recipe for mender-gateway 1.1.0


## meta-mender kirkstone-v2022.10

_Released: 10.27.2022_

### Statistics

A total of 432 lines added, 113 removed (delta 319)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 5 (45.5%) |
| Ole Petter Orhagen | 4 (36.4%) |
| Lluis Campos | 2 (18.2%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 313 (68.3%) |
| Kristian Amlie | 93 (20.3%) |
| Lluis Campos | 52 (11.4%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 7 (6.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 11 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 458 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### meta-mender (kirkstone-v2022.10)

New changes in meta-mender since kirkstone-v2022.09:

##### Bug fixes

* Upgrade grub-mender-grubenv to include the XFS module in the default installation.
* Pre-3.5 mender-client recipes needs dependency on mender-artifact-info.
* Fix build error when building image using mender-artifact
  older than 3.10.0.
* Add recipe for mender-binary-delta 1.4.1
* Add recipe for mender-monitor 1.2.1
* Add recipe for mender-gateway 1.0.1
* Add mender-client_3.3.1 and mender-artifact_3.8.1 recipes.

##### Features

* Add a bootstrap Artifact to the generated images in
  /var/lib/mender/bootstrap.mender, so that the client can bootstrap it's database
  without having to first run an update.
  ([MEN-2585](https://northerntech.atlassian.net/browse/MEN-2585))
* Add recipe for mender-client 3.4.0
* Add recipe for mender-artifact 3.9.0
* Add recipe for mender-connect 2.1.0


## meta-mender kirkstone-v2022.09

_Released: 09.12.2022_

### Statistics

A total of 12574 lines added, 14375 removed (delta -1801)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 172 (35.1%) |
| Lluis Campos | 126 (25.7%) |
| Ole Petter Orhagen | 55 (11.2%) |
| Drew Moseley | 28 (5.7%) |
| Fabio Tranchitella | 24 (4.9%) |
| Josef Holzmayr | 18 (3.7%) |
| Peter Grzybowski | 14 (2.9%) |
| Clément Péron | 9 (1.8%) |
| Manuel Zedel | 5 (1.0%) |
| Leon Anavi | 5 (1.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 13064 (56.5%) |
| Lluis Campos | 3857 (16.7%) |
| Ole Petter Orhagen | 3030 (13.1%) |
| Drew Reed | 653 (2.8%) |
| Drew Moseley | 561 (2.4%) |
| Fabio Tranchitella | 527 (2.3%) |
| Liam White McShane | 401 (1.7%) |
| Josef Holzmayr | 336 (1.5%) |
| Peter Grzybowski | 275 (1.2%) |
| Marek Belisko | 141 (0.6%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 1655 (11.5%) |
| Kristian Amlie | 1260 (8.8%) |
| Drew Moseley | 178 (1.2%) |
| Marek Belisko | 54 (0.4%) |
| Drew Reed | 4 (0.0%) |
| Maciej Tomczuk | 1 (0.0%) |

| Developers with the most signoffs (total 21) | |
|---|---|
| Lluis Campos | 8 (38.1%) |
| Kristian Amlie | 2 (9.5%) |
| Mirza Krak | 2 (9.5%) |
| Maciej Borzecki | 2 (9.5%) |
| Vikas Katariya | 2 (9.5%) |
| Zachary T Welch | 2 (9.5%) |
| Ole Petter Orhagen | 1 (4.8%) |
| Drew Moseley | 1 (4.8%) |
| Drew Reed | 1 (4.8%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 447 (91.2%) |
| peron.clem@gmail.com | 9 (1.8%) |
| Konsulko Group | 5 (1.0%) |
| open-nandra | 5 (1.0%) |
| Timesys Corporation | 4 (0.8%) |
| Arm | 4 (0.8%) |
| Chora | 3 (0.6%) |
| ENLYZE GMBH | 3 (0.6%) |
| contact@coreycothrum.com | 2 (0.4%) |
| kekiefer@gmail.com | 2 (0.4%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 21714 (94.0%) |
| Arm | 685 (3.0%) |
| Timesys Corporation | 431 (1.9%) |
| open-nandra | 141 (0.6%) |
| peron.clem@gmail.com | 59 (0.3%) |
| Konsulko Group | 28 (0.1%) |
| ENLYZE GMBH | 22 (0.1%) |
| Chora | 7 (0.0%) |
| kekiefer@gmail.com | 4 (0.0%) |
| contact@coreycothrum.com | 3 (0.0%) |

| Employers with the most signoffs (total 21) | |
|---|---|
| Northern.tech | 12 (57.1%) |
| Arm | 3 (14.3%) |
| Timesys Corporation | 2 (9.5%) |
| RnDity | 2 (9.5%) |
| mirza.krak@gmail.com | 2 (9.5%) |

| Employers with the most hackers (total 30) | |
|---|---|
| Northern.tech | 13 (43.3%) |
| Arm | 2 (6.7%) |
| Timesys Corporation | 2 (6.7%) |
| open-nandra | 1 (3.3%) |
| peron.clem@gmail.com | 1 (3.3%) |
| Konsulko Group | 1 (3.3%) |
| ENLYZE GMBH | 1 (3.3%) |
| Chora | 1 (3.3%) |
| kekiefer@gmail.com | 1 (3.3%) |
| contact@coreycothrum.com | 1 (3.3%) |

### Changelogs

#### meta-mender (kirkstone-v2022.09)

New changes in meta-mender since dunfell-v2022.09:

##### Bug fixes

* bootfiles renamed to rpi-bootfiles in upstream
  ([MEN-5689](https://northerntech.atlassian.net/browse/MEN-5689))
* Remove mender-client versions before 3.3
  ([MEN-5698](https://northerntech.atlassian.net/browse/MEN-5698))
* select buildable OpenSSL binding for mender-client
  ([MEN-5700](https://northerntech.atlassian.net/browse/MEN-5700))
* Remove lmdb recipe, which meta-openembedded/kirkstone already has.
  ([MEN-4937](https://northerntech.atlassian.net/browse/MEN-4937))
* Generate correct licenses in `$BUILDDIR/tmp/deploy/licenses`.
  ([MEN-3604](https://northerntech.atlassian.net/browse/MEN-3604))
* Make `read-only-rootfs` tweaks dependent on `mender-image` feature flag.
* Fix occasional pseudo abort issue when building certain
  images, especially in parallel. The symptom was this message:
  ```
  abort()ing pseudo client by server request.
  See https://wiki.yoctoproject.org/wiki/Pseudo_Abort for more details on this
  ```
  ([MEN-5857](https://northerntech.atlassian.net/browse/MEN-5857))
* initramfs-module-install-efi: Ensure variable changes are reflected on rebuild
* bootimg: Respect MENDER_BOOT_PART_FSTYPE.
* Auto patching: Fix error `Unable to add definition
  MTDIDS_DEFAULT`, which happens on U-Boot v2020.10 and later.
* meta-mender-ci: Custom logging level for daemons with MENDER_CI_LOGLEVEL
* use mender-efi-boot feature in EFI-related overlays
* mender-core: refresh patch to be compatible with e2fsprogs 1.46.x
* core: only patch systemd-boot when mender-systemd-boot is enabled
* Adapt to new kernel which puts QEMU storage at sda, not hda.
* Fix many dangerous uses of regexes in Python.
* meta-mender-raspberrypi: update-firmware-state-script: Make
  copies of firmware binaries safer. On VFAT file-systems `mv` is not
  atomic, but still using it narrows the time window in which the files
  could be corrupted.
* rpi-bootfiles: rename to match upstream

##### Features

* Introduce `MENDER_EFI_LOADER`. This can be used to specify
  which bootloader is used to load other EFI apps, such as the grub-efi
  bootloader. This is normally provided by firmware on x86, and is
  therefore empty, but on ARM it is often set to u-boot or edk2.
* set LAYERCOMPAT to kirkstone only
  ([MEN-5681](https://northerntech.atlassian.net/browse/MEN-5681))
* mender-monitor conditionally available depending on meta-oe
* The `mender-binary-delta` recipe now takes a tarball as
  input instead of a folder containing unpacked files. Remove the line
  starting with `FILESEXTRAPATHS`, and instead insert this line:
  ```
  SRC_URI:pn-mender-binary-delta = "file://${HOME}/mender-binary-delta-1.4.0.tar.xz"
  ```
  where the path points to the downloaded tarball.
  ([MEN-4980](https://northerntech.atlassian.net/browse/MEN-4980))
* Install standard Mender Update Modules by default. These
  are:
  * deb
  * directory
  * docker
  * rpm
  * script
  * single-file
  To disable the automatic installation of these Update Modules, add
  `PACKAGECONFIG_remove = "modules"` to your `mender_%.bbappend` file,
  or set `PACKAGECONFIG` explicitly.
* Make DBus support optional in Mender client with `PACKAGECONFIG`.

  It defaults to on, but can be turned off with:

  ```
  PACKAGECONFIG_remove = "dbus"
  ```
  ([MEN-4014](https://northerntech.atlassian.net/browse/MEN-4014))
* Features that are added or removed using
  `MENDER_FEATURES_ENABLE` or `MENDER_FEATURES_DISABLE` now end up in
  the `MENDER_FEATURES` variable instead of the `DISTRO_FEATURES`
  variable. Code of the kind:
  ```
  ${@bb.utils.contains('DISTRO_FEATURES', 'mender-uboot', 'true', 'false', d)}
  ```
  needs to change to look in `MENDER_FEATURES` instead.
* New recipe `mender-server-certificate` to install a
  self-signed Mender server certificate to be trusted by all services
  running in the device. To use it create a `.bbappend` recipe in your
  layer fetching the certificate into `file://server.crt`
  ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* meta-mender-demo: install demo server certificate with
  `mender-server-certificate` recipe to be used by `mender-client`,
  `mender-shell`, and further services that could be added.
  ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* Variable `MENDER_CERT_LOCATION` deprecated. See note about
  `mender-server-certificate` for more details
  ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* mender-server-certificate: Split concatenated certificates.

  Multiple certificates in one file are necessary to split in
  order for `update-ca-certificates` to produce a hashed symlink to
  them, which is required by some programs, such as curl.
  ([MEN-4580](https://northerntech.atlassian.net/browse/MEN-4580))
* mender-client: New native package mender-modules-gen to
  install the Mender demo Update Module Artifact generators.
  ([MEN-4671](https://northerntech.atlassian.net/browse/MEN-4671))
* grub-mender-grubenv: User space tools, "fw_printenv" and
  "fw_setenv" have been renamed to "grub-mender-grubenv-print" and
  "grub-mender-grubenv-set", respectively. This has been done in order
  to avoid conflict with U-Boot's user space tools, which have the same
  names.
* Add support for using systemd-boot with meta-mender
* Fix error message `ERROR: It's not possible to create empty
  squashfs partition 'None'` when using "squashfs" filesystem type.
  ([MEN-5285](https://northerntech.atlassian.net/browse/MEN-5285))
* use data/boot label variable
* Add feature to detect boot and data partition based on their label.
* The grub-mender-grubenv default environment location has
  moved from `/boot/efi/EFI/BOOT/mender_grubenv*` to
  `/boot/efi/grub-mender-grubenv/mender_grubenv*`. This change is
  backwards compatible; existing devices will keep the environment in
  the original location and the `grub-mender-grubenv-*` tools will
  handle either location, by
  auto-detection. `/etc/mender_grubenv.config` is no longer installed by
  default, but it is still supported if installed manually.

##### Other

* deleted the mender-binary-delta_1.1.1 recipe
* deleted the mender-binary-delta_1.1.2 recipe
* deleted the mender-monitor_1.0.0 recipe
* deleted the mender-monitor_1.0.1 recipe
* deleted the mender-monitor_1.1.0 recipe
* deleted the mender-artifact_3.5.0 recipe
* deleted the mender-artifact_3.5.1 recipe
* deleted the mender-artifact_3.5.2 recipe
* deleted the mender-artifact_3.7.0 recipe
* deleted the mender-artifact_3.7.1 recipe
* deleted the mender-client_3.1.0 recipe
* deleted the mender-client_3.2.0 recipe
* deleted the mender-client_3.2.1 recipe
* deleted the mender-connect_1.0.0 recipe
* deleted the mender-connect_1.0.1 recipe
* deleted the mender-connect_1.0.2 recipe
* deleted the mender-connect_1.0.3 recipe
* deleted the mender-connect_1.1.0 recipe
* deleted the mender-connect_1.1.1 recipe
* Remove mender-client 2.2.1 recipe
* Remove mender-artifact 3.3.0 recipe
* Remove mender-artifact 3.3.1 recipe
* Remove mender-client recipes for 2.4.x series.
* Remove mender-artifact_3.4.* and mender-client_2.3.* recipes.
* Remove mender-client recipes pre 3.1.x series
  ([MEN-3978](https://northerntech.atlassian.net/browse/MEN-3978))
* linux-raspberrypi-rt: drop support

##### Dependabot bumps

* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.12.3 to 3.13.0.
  * Bumps [fabric](http://fabfile.org) from 2.5.0 to 2.6.0.
  * Bumps [pyyaml](https://github.com/yaml/pyyaml) from 5.3.1 to 5.4.1.
      - [Release notes](https://github.com/yaml/pyyaml/releases)
      - [Changelog](https://github.com/yaml/pyyaml/blob/master/CHANGES)
      - [Commits](https://github.com/yaml/pyyaml/compare/5.3.1...5.4.1)
  * Bumps alpine from 3.13.0 to 3.13.1.
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.1 to 6.2.2.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.1...6.2.2)
  * Bumps alpine from 3.13.1 to 3.13.2.
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.3.2 to 3.4.6.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/3.3.2...3.4.6)
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.6 to 3.4.7.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/3.4.6...3.4.7)
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.2 to 6.2.3.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.2...6.2.3)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [six](https://github.com/benjaminp/six) from 1.15.0 to 1.16.0.
      - [Release notes](https://github.com/benjaminp/six/releases)
      - [Changelog](https://github.com/benjaminp/six/blob/master/CHANGES)
      - [Commits](https://github.com/benjaminp/six/compare/1.15.0...1.16.0)
  * Bumps [attrs](https://github.com/python-attrs/attrs) from 20.3.0 to 21.2.0.
      - [Release notes](https://github.com/python-attrs/attrs/releases)
      - [Changelog](https://github.com/python-attrs/attrs/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/python-attrs/attrs/compare/20.3.0...21.2.0)
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.3 to 6.2.4.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.3...6.2.4)
  * Bumps [certifi](https://github.com/certifi/python-certifi) from 2020.12.5 to 2021.5.30.
      - [Release notes](https://github.com/certifi/python-certifi/releases)
      - [Commits](https://github.com/certifi/python-certifi/compare/2020.12.05...2021.05.30)
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.4 to 1.26.5.
      - [Release notes](https://github.com/urllib3/urllib3/releases)
      - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
      - [Commits](https://github.com/urllib3/urllib3/compare/1.26.4...1.26.5)
  * Bumps alpine from 3.13.5 to 3.14.0.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.5 to 1.26.6.
      - [Release notes](https://github.com/urllib3/urllib3/releases)
      - [Changelog](https://github.com/urllib3/urllib3/blob/1.26.6/CHANGES.rst)
      - [Commits](https://github.com/urllib3/urllib3/compare/1.26.5...1.26.6)

      ```
      updated-dependencies:
      - dependency-name: urllib3
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pathlib2](https://github.com/mcmtroffaes/pathlib2) from 2.3.5 to 2.3.6.
      - [Release notes](https://github.com/mcmtroffaes/pathlib2/releases)
      - [Changelog](https://github.com/mcmtroffaes/pathlib2/blob/develop/CHANGELOG.rst)
      - [Commits](https://github.com/mcmtroffaes/pathlib2/compare/2.3.5...2.3.6)

      ```
      updated-dependencies:
      - dependency-name: pathlib2
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [packaging](https://github.com/pypa/packaging) from 20.9 to 21.0.
      - [Release notes](https://github.com/pypa/packaging/releases)
      - [Changelog](https://github.com/pypa/packaging/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pypa/packaging/compare/20.9...21.0)

      ```
      updated-dependencies:
      - dependency-name: packaging
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [invoke](https://github.com/bitprophet/alabaster) from 1.5.0 to 1.6.0.
      - [Release notes](https://github.com/bitprophet/alabaster/releases)
      - [Changelog](https://github.com/bitprophet/alabaster/blob/master/docs/changelog.rst)
      - [Commits](https://github.com/bitprophet/alabaster/commits)

      ```
      updated-dependencies:
      - dependency-name: invoke
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [cffi](http://cffi.readthedocs.org) from 1.14.5 to 1.14.6.

      ```
      updated-dependencies:
      - dependency-name: cffi
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [requests](https://github.com/psf/requests) from 2.25.1 to 2.26.0.
      - [Release notes](https://github.com/psf/requests/releases)
      - [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
      - [Commits](https://github.com/psf/requests/compare/v2.25.1...v2.26.0)

      ```
      updated-dependencies:
      - dependency-name: requests
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps alpine from 3.14.0 to 3.14.1.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps alpine from 3.14.1 to 3.14.2.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pluggy](https://github.com/pytest-dev/pluggy) from 0.13.1 to 1.0.0.
      - [Release notes](https://github.com/pytest-dev/pluggy/releases)
      - [Changelog](https://github.com/pytest-dev/pluggy/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pluggy/compare/0.13.1...1.0.0)

      ```
      updated-dependencies:
      - dependency-name: pluggy
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.7 to 3.4.8.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/3.4.7...3.4.8)

      ```
      updated-dependencies:
      - dependency-name: cryptography
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.4 to 6.2.5.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.4...6.2.5)

      ```
      updated-dependencies:
      - dependency-name: pytest
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.0.12 to 3.1.0.
      - [Release notes](https://github.com/tox-dev/py-filelock/releases)
      - [Commits](https://github.com/tox-dev/py-filelock/compare/v3.0.12...3.1.0)

      ```
      updated-dependencies:
      - dependency-name: filelock
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.6 to 1.26.7.
      - [Release notes](https://github.com/urllib3/urllib3/releases)
      - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
      - [Commits](https://github.com/urllib3/urllib3/compare/1.26.6...1.26.7)

      ```
      updated-dependencies:
      - dependency-name: urllib3
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.1.0 to 3.3.0.
      - [Release notes](https://github.com/tox-dev/py-filelock/releases)
      - [Commits](https://github.com/tox-dev/py-filelock/compare/3.1.0...3.3.0)

      ```
      updated-dependencies:
      - dependency-name: filelock
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.8 to 35.0.0.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/3.4.8...35.0.0)

      ```
      updated-dependencies:
      - dependency-name: cryptography
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [certifi](https://github.com/certifi/python-certifi) from 2021.5.30 to 2021.10.8.
      - [Release notes](https://github.com/certifi/python-certifi/releases)
      - [Commits](https://github.com/certifi/python-certifi/compare/2021.05.30...2021.10.08)

      ```
      updated-dependencies:
      - dependency-name: certifi
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.7.2 to 2.8.0.
      - [Release notes](https://github.com/paramiko/paramiko/releases)
      - [Changelog](https://github.com/paramiko/paramiko/blob/main/NEWS)
      - [Commits](https://github.com/paramiko/paramiko/compare/2.7.2...2.8.0)

      ```
      updated-dependencies:
      - dependency-name: paramiko
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [cffi](http://cffi.readthedocs.org) from 1.14.6 to 1.15.0.

      ```
      updated-dependencies:
      - dependency-name: cffi
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [pyyaml](https://github.com/yaml/pyyaml) from 5.4.1 to 6.0.
      - [Release notes](https://github.com/yaml/pyyaml/releases)
      - [Changelog](https://github.com/yaml/pyyaml/blob/master/CHANGES)
      - [Commits](https://github.com/yaml/pyyaml/compare/5.4.1...6.0)

      ```
      updated-dependencies:
      - dependency-name: pyyaml
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.3.0 to 3.3.1.
      - [Release notes](https://github.com/tox-dev/py-filelock/releases)
      - [Changelog](https://github.com/tox-dev/py-filelock/blob/main/docs/changelog.rst)
      - [Commits](https://github.com/tox-dev/py-filelock/compare/3.3.0...3.3.1)

      ```
      updated-dependencies:
      - dependency-name: filelock
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [idna](https://github.com/kjd/idna) from 2.10 to 3.3.
      - [Release notes](https://github.com/kjd/idna/releases)
      - [Changelog](https://github.com/kjd/idna/blob/master/HISTORY.rst)
      - [Commits](https://github.com/kjd/idna/compare/v2.10...v3.3)

      ```
      updated-dependencies:
      - dependency-name: idna
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [pyparsing](https://github.com/pyparsing/pyparsing) from 2.4.7 to 3.0.1.
      - [Release notes](https://github.com/pyparsing/pyparsing/releases)
      - [Changelog](https://github.com/pyparsing/pyparsing/blob/master/CHANGES)
      - [Commits](https://github.com/pyparsing/pyparsing/compare/pyparsing_2.4.7...pyparsing_3.0.1)

      ```
      updated-dependencies:
      - dependency-name: pyparsing
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.3.1 to 3.3.2.
      - [Release notes](https://github.com/tox-dev/py-filelock/releases)
      - [Changelog](https://github.com/tox-dev/py-filelock/blob/main/docs/changelog.rst)
      - [Commits](https://github.com/tox-dev/py-filelock/compare/3.3.1...3.3.2)

      ```
      updated-dependencies:
      - dependency-name: filelock
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [py](https://github.com/pytest-dev/py) from 1.10.0 to 1.11.0.
      - [Release notes](https://github.com/pytest-dev/py/releases)
      - [Changelog](https://github.com/pytest-dev/py/blob/master/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/py/compare/1.10.0...1.11.0)

      ```
      updated-dependencies:
      - dependency-name: py
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [pycparser](https://github.com/eliben/pycparser) from 2.20 to 2.21.
      - [Release notes](https://github.com/eliben/pycparser/releases)
      - [Changelog](https://github.com/eliben/pycparser/blob/master/CHANGES)
      - [Commits](https://github.com/eliben/pycparser/compare/release_v2.20...release_v2.21)

      ```
      updated-dependencies:
      - dependency-name: pycparser
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps alpine from 3.14.2 to 3.14.3.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pyparsing](https://github.com/pyparsing/pyparsing) from 3.0.1 to 3.0.6.
      - [Release notes](https://github.com/pyparsing/pyparsing/releases)
      - [Changelog](https://github.com/pyparsing/pyparsing/blob/master/CHANGES)
      - [Commits](https://github.com/pyparsing/pyparsing/compare/pyparsing_3.0.1...pyparsing_3.0.6)

      ```
      updated-dependencies:
      - dependency-name: pyparsing
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [packaging](https://github.com/pypa/packaging) from 21.0 to 21.3.
      - [Release notes](https://github.com/pypa/packaging/releases)
      - [Changelog](https://github.com/pypa/packaging/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pypa/packaging/compare/21.0...21.3)

      ```
      updated-dependencies:
      - dependency-name: packaging
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.3.2 to 3.4.0.
      - [Release notes](https://github.com/tox-dev/py-filelock/releases)
      - [Changelog](https://github.com/tox-dev/py-filelock/blob/main/docs/changelog.rst)
      - [Commits](https://github.com/tox-dev/py-filelock/compare/3.3.2...3.4.0)

      ```
      updated-dependencies:
      - dependency-name: filelock
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 35.0.0 to 36.0.0.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/35.0.0...36.0.0)

      ```
      updated-dependencies:
      - dependency-name: cryptography
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps alpine from 3.14.3 to 3.15.0.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.8.0 to 2.8.1.
      - [Release notes](https://github.com/paramiko/paramiko/releases)
      - [Changelog](https://github.com/paramiko/paramiko/blob/main/NEWS)
      - [Commits](https://github.com/paramiko/paramiko/compare/2.8.0...2.8.1)

      ```
      updated-dependencies:
      - dependency-name: paramiko
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 36.0.0 to 36.0.1.
      - [Release notes](https://github.com/pyca/cryptography/releases)
      - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/cryptography/compare/36.0.0...36.0.1)

      ```
      updated-dependencies:
      - dependency-name: cryptography
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [python-lzo](https://github.com/jd-boyd/python-lzo) from 1.12 to 1.14.
      - [Release notes](https://github.com/jd-boyd/python-lzo/releases)
      - [Changelog](https://github.com/jd-boyd/python-lzo/blob/master/NEWS)
      - [Commits](https://github.com/jd-boyd/python-lzo/compare/v1.12...v1.14)

      ```
      updated-dependencies:
      - dependency-name: python-lzo
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.8.1 to 2.9.1.
      - [Release notes](https://github.com/paramiko/paramiko/releases)
      - [Changelog](https://github.com/paramiko/paramiko/blob/main/NEWS)
      - [Commits](https://github.com/paramiko/paramiko/compare/2.8.1...2.9.1)

      ```
      updated-dependencies:
      - dependency-name: paramiko
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [attrs](https://github.com/python-attrs/attrs) from 21.2.0 to 21.4.0.
      - [Release notes](https://github.com/python-attrs/attrs/releases)
      - [Changelog](https://github.com/python-attrs/attrs/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/python-attrs/attrs/compare/21.2.0...21.4.0)

      ```
      updated-dependencies:
      - dependency-name: attrs
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [psutil](https://github.com/giampaolo/psutil) from 5.8.0 to 5.9.0.
      - [Release notes](https://github.com/giampaolo/psutil/releases)
      - [Changelog](https://github.com/giampaolo/psutil/blob/master/HISTORY.rst)
      - [Commits](https://github.com/giampaolo/psutil/compare/release-5.8.0...release-5.9.0)

      ```
      updated-dependencies:
      - dependency-name: psutil
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [requests](https://github.com/psf/requests) from 2.26.0 to 2.27.0.
      - [Release notes](https://github.com/psf/requests/releases)
      - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
      - [Commits](https://github.com/psf/requests/compare/v2.26.0...v2.27.0)

      ```
      updated-dependencies:
      - dependency-name: requests
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [requests](https://github.com/psf/requests) from 2.27.0 to 2.27.1.
      - [Release notes](https://github.com/psf/requests/releases)
      - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
      - [Commits](https://github.com/psf/requests/compare/v2.27.0...v2.27.1)

      ```
      updated-dependencies:
      - dependency-name: requests
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pynacl](https://github.com/pyca/pynacl) from 1.4.0 to 1.5.0.
      - [Release notes](https://github.com/pyca/pynacl/releases)
      - [Changelog](https://github.com/pyca/pynacl/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pyca/pynacl/compare/1.4.0...1.5.0)

      ```
      updated-dependencies:
      - dependency-name: pynacl
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```
  * Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.9.1 to 2.9.2.
      - [Release notes](https://github.com/paramiko/paramiko/releases)
      - [Changelog](https://github.com/paramiko/paramiko/blob/main/NEWS)
      - [Commits](https://github.com/paramiko/paramiko/compare/2.9.1...2.9.2)

      ```
      updated-dependencies:
      - dependency-name: paramiko
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.7 to 1.26.8.
      - [Release notes](https://github.com/urllib3/urllib3/releases)
      - [Changelog](https://github.com/urllib3/urllib3/blob/1.26.8/CHANGES.rst)
      - [Commits](https://github.com/urllib3/urllib3/compare/1.26.7...1.26.8)

      ```
      updated-dependencies:
      - dependency-name: urllib3
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [ubi-reader](https://github.com/jrspruitt/ubi_reader) from 0.7.0 to 0.7.2.
      - [Release notes](https://github.com/jrspruitt/ubi_reader/releases)
      - [Commits](https://github.com/jrspruitt/ubi_reader/commits)

      ```
      updated-dependencies:
      - dependency-name: ubi-reader
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pyparsing](https://github.com/pyparsing/pyparsing) from 3.0.6 to 3.0.7.
      - [Release notes](https://github.com/pyparsing/pyparsing/releases)
      - [Changelog](https://github.com/pyparsing/pyparsing/blob/master/CHANGES)
      - [Commits](https://github.com/pyparsing/pyparsing/compare/pyparsing_3.0.6...pyparsing_3.0.7)

      ```
      updated-dependencies:
      - dependency-name: pyparsing
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.5 to 7.0.0.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.5...7.0.0)

      ```
      updated-dependencies:
      - dependency-name: pytest
        dependency-type: direct:production
        update-type: version-update:semver-major
      ```
  * Bumps [pathlib2](https://github.com/jazzband/pathlib2) from 2.3.6 to 2.3.7.post1.
      - [Release notes](https://github.com/jazzband/pathlib2/releases)
      - [Changelog](https://github.com/jazzband/pathlib2/blob/develop/CHANGELOG.rst)
      - [Commits](https://github.com/jazzband/pathlib2/compare/2.3.6...2.3.7-post1)

      ```
      updated-dependencies:
      - dependency-name: pathlib2
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 7.0.0 to 7.0.1.
      - [Release notes](https://github.com/pytest-dev/pytest/releases)
      - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
      - [Commits](https://github.com/pytest-dev/pytest/compare/7.0.0...7.0.1)

      ```
      updated-dependencies:
      - dependency-name: pytest
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.9.2 to 2.10.2.
      - [Release notes](https://github.com/paramiko/paramiko/releases)
      - [Changelog](https://github.com/paramiko/paramiko/blob/main/NEWS)
      - [Commits](https://github.com/paramiko/paramiko/compare/2.9.2...2.10.2)

      ```
      updated-dependencies:
      - dependency-name: paramiko
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```


## meta-mender dunfell-v2024.06

_Released: 06.14.2024_

### Changelogs

#### meta-mender (dunfell-v2024.06)

New changes in meta-mender since dunfell-v2023.03:

##### Bug fixes

* mender-configure: Don't break if libdir is set to `lib64`.
* pass prefix and systemd_unitdir to mender-configure installation
* add coreutils as a runtime dependency for Mender monitor
* boot-partition-devicetree use proper SPDX License GPL-2.0-only
* Replace gpt partition type 8300 with full UUID
* wic-tools does not need grub when using uboot
* mv image files instead of install, to avoid corrupting the image.
* Fix the install path for the D-Bus interface files shipped in
  `mender-client-dev` package. It was `$(datadir)/dbus-1/interface` but it
  should be `interfaces` instead.
* remove "mender.bmap" IMAGE_FSTYPE
* Remove `has_journal` flag from mkfs.ext4 when
  `read-only-rootfs` flag is enabled, which causes issues in certain
  configurations. Specifically it solves these problems:
  * Checksum is not stable which can cause issues with binary delta
    updates. This is an in-memory effect only, the physical checksum on
    disk is unaffected.
  * Mender-snapshot can generate corrupted rootfs dumps, for the same
    reason as the previous point.
* Fix typo in fstab options for extra partitions.
* Correctly handle `mender-partuuid` feature for `dunfell`
* Make the build succeed if gateway examples aren't present

##### Features

* Add `MENDER_FLASH_TOOL` variable to mender-binary-delta.
  This has no effect for mender-binary-delta versions older than 1.5.
  ([MEN-6774](https://northerntech.atlassian.net/browse/MEN-6774))

##### Other

* Add recipe for mender-client 3.5.1
* Add recipe for mender-artifact 3.10.1
* Add recipe for mender-configure 1.1.0
* Add recipe for mender-connect 2.1.1
* Add recipe for mender-artifact 3.10.2
* Add recipe for `mender-client` 3.5.2
* Add recipe for `mender-configure` 1.1.1
* Add recipe for `mender-configure` 1.1.2
* Add recipe for mender-monitor 1.3.0
* Add recipe for `mender-binary-delta` 1.5.0
* Remove git versions for the Mender recipes `mender-client`,
  `mender-connect`, `mender-configure`, `mender-artifact`,
  `mender-monitor` and `mender-gateway`. These won't build in `dunfell`
  and are not meant to be used from an LTS yocto release.
* Add Mender client 3.5.3 recipe.
* Add mender-connect 2.1.2 recipe.


## meta-mender dunfell-v2023.03

_Released: 03.13.2023_

### Statistics

A total of 23 lines added, 9 removed (delta 14)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 23 (100.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 23 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2023.03)

New changes in meta-mender since dunfell-v2023.02:

##### Bug fixes

* Add mender-client 3.3.2 recipe.


## meta-mender dunfell-v2023.02

_Released: 02.24.2023_

### Statistics

A total of 472 lines added, 61 removed (delta 411)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 6 (60.0%) |
| Ole Petter Orhagen | 2 (20.0%) |
| Justin Verble | 1 (10.0%) |
| Fabio Tranchitella | 1 (10.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 465 (98.5%) |
| Ole Petter Orhagen | 3 (0.6%) |
| Justin Verble | 3 (0.6%) |
| Fabio Tranchitella | 1 (0.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 9 (90.0%) |
| Election Systems & Software | 1 (10.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 469 (99.4%) |
| Election Systems & Software | 3 (0.6%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| Election Systems & Software | 1 (25.0%) |

### Changelogs

#### meta-mender (dunfell-v2023.02)

New changes in meta-mender since dunfell-v2022.12:

##### Bug fixes

* Patch `mender-artifact` _next_ recipe to be compatible with
  `dunfell` which builds with golang 1.14.
  ([MEN-6142](https://tracker.mender.io/browse/MEN-6142))
* Remove grub.efi resource files using pseudo.

##### Features

* Mender Artifacts include now information about the installed
  Update Modules in the image. Specifically, the Artifacts `provide` two
  pair of keys for each module:
  `rootfs-image.update-module.<UPDATE_MODULE>.version` and
  `rootfs-image.update-module.<UPDATE_MODULE>.mender_update_module`. This
  also applies to the bootstrap Artifact which gets installed on first
  boot. ([MEN-5845](https://tracker.mender.io/browse/MEN-5845))

##### Other

* Add recipe for mender-client 3.5.0
* Add recipe for mender-artifact 3.10.0
* Add recipe for mender-gateway 1.1.0


## meta-mender dunfell-v2022.12

_Released: 12.22.2022_

### Statistics

A total of 1 lines added, 1 removed (delta 0)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 1 (100.0%) |

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

#### meta-mender (dunfell-v2022.12)

New changes in meta-mender since dunfell-v2022.11:

##### Bug fixes

* Fix the regression in which Dunfell started providing the 3.3.x
  client as the default. This was an unintentional change, and this
  re-downprioritizes it, so that the `2.x` client is once again the default.
  ([MEN-6122](https://northerntech.atlassian.net/browse/MEN-6122))


## meta-mender dunfell-v2022.11

_Released: 11.22.2022_

### Statistics

A total of 157 lines added, 18 removed (delta 139)

| Developers with the most changesets | |
|---|---|
| Marek Belisko | 6 (75.0%) |
| Lluis Campos | 2 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 110 (70.1%) |
| Marek Belisko | 47 (29.9%) |

| Top changeset contributors by employer | |
|---|---|
| open-nandra | 6 (75.0%) |
| Northern.tech | 2 (25.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 110 (70.1%) |
| open-nandra | 47 (29.9%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 1 (50.0%) |
| open-nandra | 1 (50.0%) |

### Changelogs

#### meta-mender (dunfell-v2022.11)

New changes in meta-mender since dunfell-v2022.10:

##### Bug fixes

* Add missing licenses checksums and set right preference for
  mender-client 3.3.1 recipe
* Add missing licenses checksums, set right preference, and
  add missing license for mender-artifact 3.8.1 recipe
* Fix issues found during testing when mender-partuuid is not set

##### Features

* Update UUID for all extra partitions
* Update fstab swap entry with UUID when feature is enabled
* Added variables for extra and swap parts UUID


## meta-mender dunfell-v2022.10

_Released: 10.27.2022_

### Statistics

A total of 461 lines added, 62 removed (delta 399)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (70.0%) |
| Ole Petter Orhagen | 1 (10.0%) |
| Lluis Campos | 1 (10.0%) |
| Peter Grzybowski | 1 (10.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 284 (59.3%) |
| Kristian Amlie | 161 (33.6%) |
| Lluis Campos | 32 (6.7%) |
| Peter Grzybowski | 2 (0.4%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 18 (29.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 10 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 479 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2022.10)

New changes in meta-mender since dunfell-v2022.09:

##### Bug fixes

* Fix occasional pseudo abort issue when building certain
  images, especially in parallel. The symptom was this message:
  ```
  abort()ing pseudo client by server request.
  See https://wiki.yoctoproject.org/wiki/Pseudo_Abort for more details on this
  ```
  ([MEN-5857](https://northerntech.atlassian.net/browse/MEN-5857))
* Pre-3.5 mender-client recipes needs dependency on mender-artifact-info.
* Fix build error when building image using mender-artifact
  older than 3.10.0.
* Add recipe for mender-binary-delta 1.4.1
* Add recipe for mender-monitor 1.2.1
* Add recipe for mender-gateway 1.0.1
* Add mender-client_3.3.1 and mender-artifact_3.8.1 recipes.

##### Features

* Add a bootstrap Artifact to the generated images in
  /var/lib/mender/bootstrap.mender, so that the client can bootstrap it's database
  without having to first run an update.
  ([MEN-2585](https://northerntech.atlassian.net/browse/MEN-2585))
* Add recipe for mender-client 3.4.0
* Add recipe for mender-artifact 3.9.0
* Add recipe for mender-connect 2.1.0


## meta-mender dunfell-v2022.09

_Released: 09.07.2022_

### Statistics

A total of 799 lines added, 175 removed (delta 624)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 12 (30.8%) |
| Kristian Amlie | 11 (28.2%) |
| Peter Grzybowski | 5 (12.8%) |
| Colin Finck | 3 (7.7%) |
| Fabio Tranchitella | 2 (5.1%) |
| Josef Holzmayr | 2 (5.1%) |
| Leon Anavi | 2 (5.1%) |
| Lluis Campos | 1 (2.6%) |
| Sebastian Suesens | 1 (2.6%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 547 (64.6%) |
| Peter Grzybowski | 181 (21.4%) |
| Ole Petter Orhagen | 65 (7.7%) |
| Colin Finck | 23 (2.7%) |
| Josef Holzmayr | 12 (1.4%) |
| Leon Anavi | 10 (1.2%) |
| Fabio Tranchitella | 4 (0.5%) |
| Lluis Campos | 3 (0.4%) |
| Sebastian Suesens | 2 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Josef Holzmayr | 2 (1.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 33 (84.6%) |
| ENLYZE GMBH | 3 (7.7%) |
| Konsulko Group | 2 (5.1%) |
| Basler AG | 1 (2.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 812 (95.9%) |
| ENLYZE GMBH | 23 (2.7%) |
| Konsulko Group | 10 (1.2%) |
| Basler AG | 2 (0.2%) |

| Employers with the most hackers (total 9) | |
|---|---|
| Northern.tech | 6 (66.7%) |
| ENLYZE GMBH | 1 (11.1%) |
| Konsulko Group | 1 (11.1%) |
| Basler AG | 1 (11.1%) |

### Changelogs

#### meta-mender (dunfell-v2022.09)

New changes in meta-mender since dunfell-v2022.04:

##### Bug fixes

* Add mender-artifact 3.7.1 recipe.
* Force building in separate build directory, even with `externalsrc`.
* Automatically rebuild is tags have changed.
* Make mender-client-resize-data-part compatible with "partuuid" setups.
  ([MEN-3701](https://northerntech.atlassian.net/browse/MEN-3701))
* Race condition in mender-client-resize-data-part
  ([MEN-5717](https://northerntech.atlassian.net/browse/MEN-5717))
* Added mender-configure-module 1.0.4
* Better error message when Enterprise components can't be found.
* Add a systemd Before dependency on the `mender-client-data-dir`
  service file.
* repeated grub build with different MENDER_STORAGE_DEVICE

  If a variable in do_configure task changed do_configure task is triggered
  again but not do_compile.This patch clean the build folder and triggered
  do_compile task again to get a fresh grub.cfg file with the fresh generated
  data from do_configure task.

##### Features

* Add mender-artifact version 3.8.0.
* add the mender-client 3.3.0 recipe
* Add the mender-monitor 1.2.0 recipe
* Add the mender-gateway 1.0.0 recipe
* Add recipe for mender-binary-delta 1.4.0
* Implemented proper license tracking for commercial
  components. This was necessary for several reasons:
  * Licenses were not being correctly generated inside
    `$BUILDDIR/tmp/deploy/licenses`.
  * Because they were not generated correctly, it wasn't previously
    possible to bind a particular version of a commercial component to
    a specific license. Hence, if Northern.tech were to change the
    license, this online version would be the only available copy. It
    thus would become unclear exactly what terms the user had accepted.
    This has been fixed by including the license with the software.
  This requires all users to re-accept the license (the license text can
  be found in
  `meta-mender-commercial/files/licenses/Mender-Yocto-Layer-License.md`),
  by adding this to their `local.conf`:
  ```
  LICENSE_FLAGS_ACCEPTED:append = " commercial_mender-yocto-layer-license"
  ```
  Previous assignments of `LICENSE_FLAGS_ACCEPTED` mentioning "mender"
  software can be removed.
  ([MEN-5517](https://northerntech.atlassian.net/browse/MEN-5517))
* mender-artifact: Add OpenSSL dependency
  ([MEN-5759](https://northerntech.atlassian.net/browse/MEN-5759))

##### Other

* dataimg: Load Mender files on F2FS

  Bug fix to load Mender configuration files to the data partition
  when using F2FS through sload.f2fs.
* mender-part-images: f2fs-tools-native if using F2FS

  Add a dependency to f2fs-tools-native if using F2FS for the data
  partition.

## meta-mender dunfell-v2022.04

_Released: 04.11.2022_

### Statistics

A total of 27 lines added, 11 removed (delta 16)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 4 (80.0%) |
| Leon Anavi | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 27 (77.1%) |
| Leon Anavi | 8 (22.9%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (80.0%) |
| Konsulko Group | 1 (20.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 27 (77.1%) |
| Konsulko Group | 8 (22.9%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 1 (50.0%) |
| Konsulko Group | 1 (50.0%) |

### Changelogs

#### meta-mender (dunfell-v2022.04)

New changes in meta-mender since dunfell-v2022.03:

* Support F2FS for the data partition
* Merge pull request #1652 from lluiscampos/qemu-docker-update-alpine

  Bump alpine in /meta-mender-qemu/docker/qemux86-64
* meta-mender-demo: Add demo functionality for mender-gateway

  Requires the user to extend SRC_URI of mender-gateway with the location
  of the examples tarball:
  ```
  SRC_URI_pn-mender-gateway_append = " file:///<download-path>/mender-gateway-examples-1.0.0.tar"
  ```

  Download the tarball from https://docs.mender.io/downloads
  ([MEN-5475](https://northerntech.atlassian.net/browse/MEN-5475))
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.12.3 to 3.15.0.


## meta-mender zeus-v2022.03

_Released: 03.25.2022_

### Statistics

A total of 30 lines added, 4 removed (delta 26)

| Developers with the most changesets | |
|---|---|
| Josef Holzmayr | 4 (66.7%) |
| Leon Anavi | 1 (16.7%) |
| Corey Cothrum | 1 (16.7%) |

| Developers with the most changed lines | |
|---|---|
| Josef Holzmayr | 24 (80.0%) |
| Leon Anavi | 4 (13.3%) |
| Corey Cothrum | 2 (6.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (66.7%) |
| Konsulko Group | 1 (16.7%) |
| contact@coreycothrum.com | 1 (16.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 24 (80.0%) |
| Konsulko Group | 4 (13.3%) |
| contact@coreycothrum.com | 2 (6.7%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 1 (33.3%) |
| Konsulko Group | 1 (33.3%) |
| contact@coreycothrum.com | 1 (33.3%) |

### Changelogs

#### meta-mender (zeus-v2022.03)

New changes in meta-mender since zeus-v2022.02:

* prevent pseudo inode mismatch w/ efi-secure-boot
* Avoid lib64/*.a issues with lsb-ld on multilib systems

## meta-mender dunfell-v2022.03

_Released: 03.14.2022_

### Statistics

A total of 217 lines added, 121 removed (delta 96)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 6 (40.0%) |
| Josef Holzmayr | 4 (26.7%) |
| Kristian Amlie | 2 (13.3%) |
| Leon Anavi | 1 (6.7%) |
| Ole Petter Orhagen | 1 (6.7%) |
| Corey Cothrum | 1 (6.7%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 109 (50.2%) |
| Lluis Campos | 69 (31.8%) |
| Josef Holzmayr | 24 (11.1%) |
| Kristian Amlie | 9 (4.1%) |
| Leon Anavi | 4 (1.8%) |
| Corey Cothrum | 2 (0.9%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 13 (86.7%) |
| Konsulko Group | 1 (6.7%) |
| contact@coreycothrum.com | 1 (6.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 211 (97.2%) |
| Konsulko Group | 4 (1.8%) |
| contact@coreycothrum.com | 2 (0.9%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 4 (66.7%) |
| Konsulko Group | 1 (16.7%) |
| contact@coreycothrum.com | 1 (16.7%) |

### Changelogs

#### meta-mender (dunfell-v2022.03)

New changes in meta-mender since dunfell-v2022.02:

* prevent pseudo inode mismatch w/ efi-secure-boot
* Add recipe for mender-gateway_git
  ([MEN-5300](https://northerntech.atlassian.net/browse/MEN-5300))
* Add testing image mender-gateway-image-full-cmdline
  ([MEN-5300](https://northerntech.atlassian.net/browse/MEN-5300))
* Avoid lib64/*.a issues with lsb-ld on multilib systems

## meta-mender zeus-v2022.02

_Released 02.28.2022_

### Statistics

A total of 681 lines added, 137 removed (delta 544)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 12 (42.9%) |
| Ole Petter Orhagen | 8 (28.6%) |
| Kristian Amlie | 6 (21.4%) |
| Marek Belisko | 2 (7.1%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 628 (89.3%) |
| Ole Petter Orhagen | 34 (4.8%) |
| Kristian Amlie | 31 (4.4%) |
| Marek Belisko | 10 (1.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Ole Petter Orhagen | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 26 (92.9%) |
| open-nandra | 2 (7.1%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 693 (98.6%) |
| open-nandra | 10 (1.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| open-nandra | 1 (25.0%) |

### Changelogs

#### meta-mender (zeus-v2022.02)

New changes in meta-mender since zeus-v2021.12:

* mender-setup-image: Add swap partition to fstab
* Enable demo functionality for the monitor-client
  ([MEN-5137](https://northerntech.atlassian.net/browse/MEN-5137))
* release-3.2.0: add mender-artifact 3.7.0
* release-3.2.0: add mender-client 3.2.0
* release-3.2.0: add mender-connect 2.0.0
* release-3.2.0: add mender-monitor 1.1.0
* release-3.2.0: add mender-configure 1.0.3 recipe
* Add the mender-connect 2.0.1 recipe
* Add the mender-client 3.2.1 recipe
* Add recipe for mender-client 3.1.1
* Add recipe for mender-connect 1.2.1
* Add recipe for mender-monitor 1.0.1
* Add recipe for mender-client 3.0.2
* Add recipe for mender-client 2.5.4
* Add recipe for mender-connect 1.0.3


## meta-mender dunfell-v2022.02

_Released 02.16.2022_

### Statistics

A total of 674 lines added, 133 removed (delta 541)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 10 (37.0%) |
| Ole Petter Orhagen | 9 (33.3%) |
| Kristian Amlie | 6 (22.2%) |
| Marek Belisko | 2 (7.4%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 611 (87.8%) |
| Ole Petter Orhagen | 44 (6.3%) |
| Kristian Amlie | 31 (4.5%) |
| Marek Belisko | 10 (1.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Ole Petter Orhagen | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 25 (92.6%) |
| open-nandra | 2 (7.4%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 686 (98.6%) |
| open-nandra | 10 (1.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| open-nandra | 1 (25.0%) |

### Changelogs

#### meta-mender (dunfell-v2022.02)

New changes in meta-mender since dunfell-v2021.12:

* mender-setup-image: Add swap partition to fstab
* Enable demo functionality for the monitor-client
  ([MEN-5137](https://northerntech.atlassian.net/browse/MEN-5137))
* release-3.2.0: add mender-artifact 3.7.0
* release-3.2.0: add mender-client 3.2.0
* release-3.2.0: add mender-connect 2.0.0
* release-3.2.0: add mender-monitor 1.1.0
* release-3.2.0: add mender-configure 1.0.3 recipe
* Add the mender-connect 2.0.1 recipe
* Add the mender-client 3.2.1 recipe
* Add recipe for mender-client 3.1.1
* Add recipe for mender-connect 1.2.1
* Add recipe for mender-monitor 1.0.1
* Add recipe for mender-client 3.0.2
* Add recipe for mender-client 2.5.4
* Add recipe for mender-connect 1.0.3


## meta-mender zeus-v2021.12

_Released 12.20.2021_

### Statistics

A total of 25 lines added, 7 removed (delta 18)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 2 (50.0%) |
| Clément Péron | 1 (25.0%) |
| Lluis Campos | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 13 (52.0%) |
| Clément Péron | 9 (36.0%) |
| Kristian Amlie | 3 (12.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (75.0%) |
| peron.clem@gmail.com | 1 (25.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 16 (64.0%) |
| peron.clem@gmail.com | 9 (36.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| peron.clem@gmail.com | 1 (33.3%) |

### Changelogs

#### meta-mender (zeus-v2021.12)

New changes in meta-mender since zeus-v2021.11:

* Switch git:// links to https:// links since Github disabled them.
* Avoid populating rootfs partition B to save space when compressing.
* mender-connect master: depend on mender 3.2
  ([MEN-5203](https://northerntech.atlassian.net/browse/MEN-5203))
* Fix installation when cross-compiling mender-artifact


## meta-mender dunfell-v2021.12

_Released 12.03.2021_

### Statistics

A total of 27 lines added, 8 removed (delta 19)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 2 (40.0%) |
| Clément Péron | 1 (20.0%) |
| Lluis Campos | 1 (20.0%) |
| Peter Hatina | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 13 (48.1%) |
| Clément Péron | 9 (33.3%) |
| Kristian Amlie | 3 (11.1%) |
| Peter Hatina | 2 (7.4%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (60.0%) |
| peron.clem@gmail.com | 1 (20.0%) |
| peter@hatina.eu | 1 (20.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 16 (59.3%) |
| peron.clem@gmail.com | 9 (33.3%) |
| peter@hatina.eu | 2 (7.4%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 2 (50.0%) |
| peron.clem@gmail.com | 1 (25.0%) |
| peter@hatina.eu | 1 (25.0%) |

### Changelogs

#### meta-mender (dunfell-v2021.12)

New changes in meta-mender since dunfell-v2021.11:

* Fix FTBFS due to host contamination with secure boot enabled
* Switch git:// links to https:// links since Github disabled them.
* Avoid populating rootfs partition B to save space when compressing.
* mender-connect master: depend on mender 3.2
  ([MEN-5203](https://northerntech.atlassian.net/browse/MEN-5203))
* Fix installation when cross-compiling mender-artifact

## meta-mender zeus-v2021.11

_Released 11.19.2021_

### Statistics

A total of 5 lines added, 4 removed (delta 1)

| Developers with the most changesets | |
|---|---|
| Peter Hatina | 1 (33.3%) |
| Kristian Amlie | 1 (33.3%) |
| Clément Péron | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Peter Hatina | 2 (40.0%) |
| Clément Péron | 2 (40.0%) |
| Kristian Amlie | 1 (20.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (33.3%) |
| peter@hatina.eu | 1 (33.3%) |
| peron.clem@gmail.com | 1 (33.3%) |

| Top lines changed by employer | |
|---|---|
| peter@hatina.eu | 2 (40.0%) |
| peron.clem@gmail.com | 2 (40.0%) |
| Northern.tech | 1 (20.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 1 (33.3%) |
| peter@hatina.eu | 1 (33.3%) |
| peron.clem@gmail.com | 1 (33.3%) |

### Changelogs

#### meta-mender (zeus-v2021.11)

New changes in meta-mender since zeus-v2021.10:

* Add support for VirtIO disk drives
* u-boot: Fix save_mender_auto_configured_patch when recipe
  version contains a `+`.
* Fix FTBFS due to host contamination with secure boot enabled


## meta-mender dunfell-v2021.11

_Released 11.02.2021_

### Statistics

A total of 19 lines added, 17 removed (delta 2)

| Developers with the most changesets | |
|---|---|
| Clément Péron | 1 (33.3%) |
| Ole Petter Orhagen | 1 (33.3%) |
| Kristian Amlie | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 17 (89.5%) |
| Clément Péron | 1 (5.3%) |
| Kristian Amlie | 1 (5.3%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (66.7%) |
| peron.clem@gmail.com | 1 (33.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 18 (94.7%) |
| peron.clem@gmail.com | 1 (5.3%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| peron.clem@gmail.com | 1 (33.3%) |

### Changelogs

#### meta-mender (dunfell-v2021.11)

New changes in meta-mender since dunfell-v2021.10:

* u-boot: Fix save_mender_auto_configured_patch when recipe
  version contains a `+`.
* Add support for VirtIO disk drives


## meta-mender zeus-v2021.10

_Released 10.05.2021_

### Statistics

A total of 331 lines added, 61 removed (delta 270)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 7 (36.8%) |
| Ole Petter Orhagen | 4 (21.1%) |
| Peter Grzybowski | 4 (21.1%) |
| Kristian Amlie | 3 (15.8%) |
| Alf-Rune Siqveland | 1 (5.3%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 207 (62.5%) |
| Ole Petter Orhagen | 71 (21.5%) |
| Peter Grzybowski | 31 (9.4%) |
| Alf-Rune Siqveland | 15 (4.5%) |
| Kristian Amlie | 7 (2.1%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 19 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 331 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

### Changelogs

#### meta-mender (zeus-v2021.10)

New changes in meta-mender since zeus-v2021.07:

* Fix: mender-client-dev package contains D-Bus interface files
  only when "dbus" is enabled in PACKAGECONFIG.
  ([MEN-4811](https://northerntech.atlassian.net/browse/MEN-4811))
* meta-mender-commercial: Add mender-monitor git recipe
  ([MEN-4712](https://northerntech.atlassian.net/browse/MEN-4712))
* Add new image mender-monitor-image-full-cmdline for internal testing
  ([MEN-4712](https://northerntech.atlassian.net/browse/MEN-4712))
* Monitoring wrapper alignment
  ([MEN-4737](https://northerntech.atlassian.net/browse/MEN-4737))
* Use ${localstatedir} in mender-configure
* Monitoring: ln -s /data/mender-monitor /var/lib/mender-monitor
  ([MEN-4710](https://northerntech.atlassian.net/browse/MEN-4710))
* Include mender-monitorctl in mender-monitor recipe.
  ([MEN-4893](https://northerntech.atlassian.net/browse/MEN-4893))
* Add lmdb as a runtime depency to the mender-monitor recipe
* Add recipe for mender-client 3.1.0
* Add recipe for mender-artifact 3.6.1
* Add recipe for mender-monitor 1.0.0
* Add recipe for mender-binary-delta 1.3.0
* Add recipe for mender-configure 1.0.2
* Add recipe for mender-client 2.5.3
* Add recipe for mender-artifact 3.5.3
* Add recipe for mender-client 3.0.1


## meta-mender dunfell-v2021.10

_Released 10.04.2021_

### Statistics

A total of 231 lines added, 33 removed (delta 198)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 4 (26.7%) |
| Lluis Campos | 4 (26.7%) |
| Kristian Amlie | 3 (20.0%) |
| Peter Grzybowski | 3 (20.0%) |
| Alf-Rune Siqveland | 1 (6.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 123 (53.2%) |
| Ole Petter Orhagen | 71 (30.7%) |
| Peter Grzybowski | 15 (6.5%) |
| Alf-Rune Siqveland | 15 (6.5%) |
| Kristian Amlie | 7 (3.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 15 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 231 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2021.10)

New changes in meta-mender since dunfell-v2021.08:

* Use ${localstatedir} in mender-configure
* Monitoring: ln -s /data/mender-monitor /var/lib/mender-monitor
  ([MEN-4710](https://northerntech.atlassian.net/browse/MEN-4710))
* Include mender-monitorctl in mender-monitor recipe.
  ([MEN-4893](https://northerntech.atlassian.net/browse/MEN-4893))
* Add lmdb as a runtime depency to the mender-monitor recipe
* Add recipe for mender-client 3.1.0
* Add recipe for mender-artifact 3.6.1
* Add recipe for mender-monitor 1.0.0
* Add recipe for mender-binary-delta 1.3.0
* Add recipe for mender-configure 1.0.2
* Add recipe for mender-client 2.5.3
* Add recipe for mender-artifact 3.5.3
* Add recipe for mender-client 3.0.1


## meta-mender dunfell-v2021.08

_Released 08.05.2021_

### Statistics

A total of 179 lines added, 99 removed (delta 80)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 7 (77.8%) |
| Peter Grzybowski | 1 (11.1%) |
| Kristian Amlie | 1 (11.1%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 109 (60.6%) |
| Kristian Amlie | 55 (30.6%) |
| Peter Grzybowski | 16 (8.9%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 9 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 180 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |


### Changelogs

#### meta-mender (dunfell-v2021.08)

New changes in meta-mender since dunfell-v2021.07.02:

* Fix: mender-client-dev package contains D-Bus interface files
  only when "dbus" is enabled in PACKAGECONFIG.
  ([MEN-4811](https://northerntech.atlassian.net/browse/MEN-4811))
* meta-mender-commercial: Add mender-monitor git recipe
  ([MEN-4712](https://northerntech.atlassian.net/browse/MEN-4712))
* Add new image mender-monitor-image-full-cmdline for internal testing
  ([MEN-4712](https://northerntech.atlassian.net/browse/MEN-4712))
* Monitoring wrapper alignment
  ([MEN-4737](https://northerntech.atlassian.net/browse/MEN-4737))

## meta-mender zeus-v2021.07

_Released 07.23.2021_

### Statistics

A total of 1314 lines added, 298 removed (delta 1016)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 12 (40.0%) |
| Lluis Campos | 11 (36.7%) |
| Ole Petter Orhagen | 2 (6.7%) |
| Fabio Tranchitella | 2 (6.7%) |
| Pierre-Jean Texier | 1 (3.3%) |
| Corey Cothrum | 1 (3.3%) |
| Alan Martinovic | 1 (3.3%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 1009 (76.6%) |
| Lluis Campos | 238 (18.1%) |
| Fabio Tranchitella | 55 (4.2%) |
| Ole Petter Orhagen | 12 (0.9%) |
| Pierre-Jean Texier | 1 (0.1%) |
| Corey Cothrum | 1 (0.1%) |
| Alan Martinovic | 1 (0.1%) |

| Developers with the most signoffs (total 6) | |
|---|---|
| Lluis Campos | 6 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 28 (93.3%) |
| texier.pj2@gmail.com | 1 (3.3%) |
| contact@coreycothrum.com | 1 (3.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1315 (99.8%) |
| texier.pj2@gmail.com | 1 (0.1%) |
| contact@coreycothrum.com | 1 (0.1%) |

| Employers with the most signoffs (total 6) | |
|---|---|
| Northern.tech | 6 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 5 (71.4%) |
| texier.pj2@gmail.com | 1 (14.3%) |
| contact@coreycothrum.com | 1 (14.3%) |

### Changelogs

#### meta-mender (zeus-v2021.07)

New changes in meta-mender since zeus-v2021.04:

* Add meta-oe as dependency to mender-demo
* mender-client-dev package to distribute D-Bus API specs
  ([MEN-4106](https://northerntech.atlassian.net/browse/MEN-4106))
* fix grub chownboot task ordering
* Add io.mender.UpdateManager to D-Bus policy files.
* Fix build error when trying to build mender-configure
  without systemd:
  ```
  mender-configure-1.0.0-r0 do_package: SYSTEMD_SERVICE_mender-configure value mender-configure-apply-device-config.service does not exist.
  ```
* u-boot-mender: Ignore case when checking variables in mender_Kconfig_fragment
* Add mender-client-3.0.0 recipe. Note that it has to be
  enabled specifically, since it is not perfectly compatible with the
  2.x series:
  ```
  PREFERRED_VERSION_mender-client = "3.%"
  ```
  In particular, the single dash flags have been removed and replaced
  with commands. It is no longer possible to use `mender -install`, it
  must be replaced with `mender install`, and likewise for similar
  commands.
* Add mender-artifact-3.6.0 recipe.
* Add mender-connect-1.2.0 recipe.
* Add mender-configure-1.0.1 recipe.
* Add mender-artifact-3.5.2 recipe.
* Add mender-client-2.5.2 recipe.
* Add mender-client-2.6.1 recipe.
* Add mender-connect-1.0.2 recipe.
* Add mender-connect-1.1.1 recipe.
* Increase Update Control Map timeout values in demo to avoid
  Update Control malfunctioning on slow boards.

## meta-mender dunfell-v2021.07.02

_Released 07.15.2021_

### Statistics

A total of 10 lines added, 1 removed (delta 9)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 10 (100.0%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Lluis Campos | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 10 (100.0%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2021.07.02)

New changes in meta-mender since dunfell-v2021.07:

* Increase Update Control Map timeout values in demo to avoid
  Update Control malfunctioning on slow boards.

## meta-mender dunfell-v2021.07

_Released 07.15.2021_

### Statistics

A total of 1172 lines added, 227 removed (delta 945)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 11 (50.0%) |
| Lluis Campos | 7 (31.8%) |
| Ole Petter Orhagen | 1 (4.5%) |
| Pierre-Jean Texier | 1 (4.5%) |
| Corey Cothrum | 1 (4.5%) |
| Alan Martinovic | 1 (4.5%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 956 (81.4%) |
| Lluis Campos | 213 (18.1%) |
| Ole Petter Orhagen | 2 (0.2%) |
| Pierre-Jean Texier | 1 (0.1%) |
| Corey Cothrum | 1 (0.1%) |
| Alan Martinovic | 1 (0.1%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 20 (90.9%) |
| texier.pj2@gmail.com | 1 (4.5%) |
| contact@coreycothrum.com | 1 (4.5%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1172 (99.8%) |
| texier.pj2@gmail.com | 1 (0.1%) |
| contact@coreycothrum.com | 1 (0.1%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 4 (66.7%) |
| texier.pj2@gmail.com | 1 (16.7%) |
| contact@coreycothrum.com | 1 (16.7%) |

### Changelogs

#### meta-mender (dunfell-v2021.07)

New changes in meta-mender since dunfell-v2021.06:

* Add meta-oe as dependency to mender-demo
* fix grub chownboot task ordering
* Add io.mender.UpdateManager to D-Bus policy files.
* Fix build error when trying to build mender-configure
  without systemd:
  ```
  mender-configure-1.0.0-r0 do_package: SYSTEMD_SERVICE_mender-configure value mender-configure-apply-device-config.service does not exist.
  ```
* u-boot-mender: Ignore case when checking variables in mender_Kconfig_fragment
* Add mender-client-3.0.0 recipe. Note that it has to be
  enabled specifically, since it is not perfectly compatible with the
  2.x series:
  ```
  PREFERRED_VERSION_mender-client = "3.%"
  ```
  In particular, the single dash flags have been removed and replaced
  with commands. It is no longer possible to use `mender -install`, it
  must be replaced with `mender install`, and likewise for similar
  commands.
* Add mender-artifact-3.6.0 recipe.
* Add mender-connect-1.2.0 recipe.
* Add mender-configure-1.0.1 recipe.
* Add mender-artifact-3.5.2 recipe.
* Add mender-client-2.5.2 recipe.
* Add mender-client-2.6.1 recipe.
* Add mender-connect-1.0.2 recipe.
* Add mender-connect-1.1.1 recipe.

## meta-mender dunfell-v2021.06

_Released 05.28.2021_

### Statistics

A total of 55 lines added, 1 removed (delta 54)

| Developers with the most changesets | |
|---|---|
| Fabio Tranchitella | 2 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Fabio Tranchitella | 55 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 55 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2021.06)

New changes in meta-mender since dunfell-v2021.04:

* mender-client-dev package to distribute D-Bus API specs
  ([MEN-4106](https://northerntech.atlassian.net/browse/MEN-4106))


## meta-mender zeus-v2021.04

_Released 04.23.2021_

### Statistics

A total of 264 lines added, 92 removed (delta 172)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 9 (34.6%) |
| Lluis Campos | 8 (30.8%) |
| Ole Petter Orhagen | 7 (26.9%) |
| Peter Grzybowski | 1 (3.8%) |
| Leon Anavi | 1 (3.8%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 125 (46.5%) |
| Lluis Campos | 99 (36.8%) |
| Ole Petter Orhagen | 37 (13.8%) |
| Leon Anavi | 6 (2.2%) |
| Peter Grzybowski | 2 (0.7%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 25 (96.2%) |
| Konsulko Group | 1 (3.8%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 263 (97.8%) |
| Konsulko Group | 6 (2.2%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| Konsulko Group | 1 (20.0%) |

### Changelogs

#### meta-mender (zeus-v2021.04)

New changes in meta-mender since zeus-v2021.02:

* Fix Mender installation from a USB stick for BIOS
* Fixes build warnings: "MENDER_CONNECT_..." is not a
  recognized MENDER_ variable
* mender-connect.conf: Remove unnecessary field ServerURL
* Include a recipe for building dosfstools 4.2
  This is due to an error in older versions, which can leave the Vfat boot
  partitions bricked.
  See for more information.
  ([MEN-4497](https://northerntech.atlassian.net/browse/MEN-4497))
* Add mender-configure git recipe
  ([MEN-4420](https://northerntech.atlassian.net/browse/MEN-4420))
* Add mender-configure-scripts package, which provides
  timezone configuration out of the box.
* Add mender-configure-demo package, which provides led
  manipulation on Raspberry Pi devices, for demo purposes.
* If the `mender-systemd` class is set (the default),
  mender-configure now provides a service file for systemd which will
  automatically apply the stored configuration on startup.
* Prepopulate the device config in mender-configure-demo.
  ([MEN-4594](https://northerntech.atlassian.net/browse/MEN-4594))
* mender-client: Split concatenated certificates in ca-certificates.
  Multiple certificates in one file are necessary to split in
  order for `update-ca-certificates` to produce a hashed symlink to
  them, which is required by some programs, such as curl.
  ([MEN-4580](https://northerntech.atlassian.net/browse/MEN-4580))
* Add mender-client 2.6.0.
* Add mender-connect 1.1.0.
* Add mender-artifact 3.5.1.
* Add mender-configure 1.0.0.
* Add mender-client 2.5.1
* Add mender-connect 1.0.1
* Add mender-binary-delta 1.1.2
* Add mender-binary-delta-1.2.1 recipe.
* Add mender-client 2.3.3
* Add mender-artifact 3.4.2
* chmod 600 on mender.conf
  ([MEN-3762](https://northerntech.atlassian.net/browse/MEN-3762))

## meta-mender warrior-v2021.04

_Released 04.23.2021_

### Statistics

A total of 271 lines added, 94 removed (delta 177)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 9 (33.3%) |
| Kristian Amlie | 9 (33.3%) |
| Ole Petter Orhagen | 7 (25.9%) |
| Peter Grzybowski | 1 (3.7%) |
| Leon Anavi | 1 (3.7%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 124 (44.9%) |
| Lluis Campos | 107 (38.8%) |
| Ole Petter Orhagen | 37 (13.4%) |
| Leon Anavi | 6 (2.2%) |
| Peter Grzybowski | 2 (0.7%) |

| Developers with the most signoffs (total 6) | |
|---|---|
| Lluis Campos | 6 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 26 (96.3%) |
| Konsulko Group | 1 (3.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 270 (97.8%) |
| Konsulko Group | 6 (2.2%) |

| Employers with the most signoffs (total 6) | |
|---|---|
| Northern.tech | 6 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| Konsulko Group | 1 (20.0%) |

### Changelogs

#### meta-mender (warrior-v2021.04)

New changes in meta-mender since warrior-v2021.02:

* Fix Mender installation from a USB stick for BIOS
* Fixes build warnings: "MENDER_CONNECT_..." is not a
  recognized MENDER_ variable
* mender-connect.conf: Remove unnecessary field ServerURL
* Include a recipe for building dosfstools 4.2
  This is due to an error in older versions, which can leave the Vfat boot
  partitions bricked.
  See for more information.
  ([MEN-4497](https://northerntech.atlassian.net/browse/MEN-4497))
* Add mender-configure git recipe
  ([MEN-4420](https://northerntech.atlassian.net/browse/MEN-4420))
* Add mender-configure-scripts package, which provides
  timezone configuration out of the box.
* Add mender-configure-demo package, which provides led
  manipulation on Raspberry Pi devices, for demo purposes.
* If the `mender-systemd` class is set (the default),
  mender-configure now provides a service file for systemd which will
  automatically apply the stored configuration on startup.
* Prepopulate the device config in mender-configure-demo.
  ([MEN-4594](https://northerntech.atlassian.net/browse/MEN-4594))
* mender-client: Split concatenated certificates in ca-certificates.
  Multiple certificates in one file are necessary to split in
  order for `update-ca-certificates` to produce a hashed symlink to
  them, which is required by some programs, such as curl.
  ([MEN-4580](https://northerntech.atlassian.net/browse/MEN-4580))
* Add mender 2.6.0.
* Add mender-connect 1.1.0.
* Add mender-artifact 3.5.1.
* Add mender-configure 1.0.0.
* Add mender 2.5.1
* Add mender-connect 1.0.1
* Add mender-binary-delta 1.1.2
* Add mender-binary-delta-1.2.1 recipe.
* Add mender 2.3.3
* Add mender-artifact 3.4.2
* chmod 600 on mender.conf
  ([MEN-3762](https://northerntech.atlassian.net/browse/MEN-3762))

## meta-mender dunfell-v2021.04

_Released 04.16.2021_

### Statistics

A total of 271 lines added, 85 removed (delta 186)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 12 (50.0%) |
| Ole Petter Orhagen | 7 (29.2%) |
| Lluis Campos | 5 (20.8%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 143 (52.6%) |
| Lluis Campos | 92 (33.8%) |
| Ole Petter Orhagen | 37 (13.6%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 24 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 272 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2021.04)

New changes in meta-mender since dunfell-v2021.03:

* Add mender-configure git recipe
([MEN-4420](https://northerntech.atlassian.net/browse/MEN-4420))
* Include a recipe for building dosfstools 4.2
This is due to an error in older versions, which can leave the Vfat boot
partitions bricked.
See for more information.
([MEN-4497](https://northerntech.atlassian.net/browse/MEN-4497))
* Add mender-configure-scripts package, which provides
timezone configuration out of the box.
* Add mender-configure-demo package, which provides led
manipulation on Raspberry Pi devices, for demo purposes.
* If the `mender-systemd` class is set (the default),
mender-configure now provides a service file for systemd which will
automatically apply the stored configuration on startup.
* Fix `EFI_PROVIDER` being set incorrectly when using certain layers.
* Prepopulate the device config in mender-configure-demo.
([MEN-4594](https://northerntech.atlassian.net/browse/MEN-4594))
* mender-client: Split concatenated certificates in ca-certificates.
Multiple certificates in one file are necessary to split in
order for `update-ca-certificates` to produce a hashed symlink to
them, which is required by some programs, such as curl.
([MEN-4580](https://northerntech.atlassian.net/browse/MEN-4580))
* Add mender-client 2.6.0.
* Add mender-connect 1.1.0.
* Add mender-artifact 3.5.1.
* Add mender-configure 1.0.0.
* Add mender-client 2.5.1
* Add mender-connect 1.0.1
* Add mender-binary-delta 1.1.2
* Add mender-binary-delta-1.2.1 recipe.
* Add mender-client 2.3.3
* Add mender-artifact 3.4.2
## meta-mender dunfell-v2021.03

_Released 03.05.2021_

### Statistics

A total of 29 lines added, 23 removed (delta 6)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 5 (62.5%) |
| Kristian Amlie | 2 (25.0%) |
| Leon Anavi | 1 (12.5%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 16 (47.1%) |
| Lluis Campos | 12 (35.3%) |
| Leon Anavi | 6 (17.6%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 2 (8.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 7 (87.5%) |
| Konsulko Group | 1 (12.5%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 28 (82.4%) |
| Konsulko Group | 6 (17.6%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| Konsulko Group | 1 (33.3%) |


### Changelogs

#### meta-mender (dunfell-v2021.03)

New changes in meta-mender since dunfell-v2021.01:

* Fix Mender installation from a USB stick for BIOS
* Fixes build warnings: "MENDER_CONNECT_..." is not a
recognized MENDER_ variable
* mender-connect: Correct ShellCommand key in config file
* mender-connect.conf: Remove unnecessary field ServerURL

## meta-mender zeus-v2021.02

_Released 02.22.2021_

### Statistics

A total of 887 lines added, 368 removed (delta 519)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 22 (40.0%) |
| Kristian Amlie | 18 (32.7%) |
| Fabio Tranchitella | 14 (25.5%) |
| Ole Petter Orhagen | 1 (1.8%) |

| Developers with the most changed lines | |
|---|---|
| Fabio Tranchitella | 407 (42.0%) |
| Lluis Campos | 379 (39.2%) |
| Kristian Amlie | 162 (16.7%) |
| Ole Petter Orhagen | 20 (2.1%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 20 (5.4%) |

| Developers with the most signoffs (total 7) | |
|---|---|
| Lluis Campos | 7 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 55 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 968 (100.0%) |

| Employers with the most signoffs (total 7) | |
|---|---|
| Northern.tech | 7 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### meta-mender (zeus-v2021.02)

New changes in meta-mender since zeus-v2020.12:

* Make DBus support optional in Mender client with `PACKAGECONFIG`.
It defaults to on, but can be turned off with:
```
PACKAGECONFIG_remove = "dbus"
```
Backported to dunfell, modifying the PACKAGECONFIG defaults and amending
the test. ([MEN-4014](https://northerntech.atlassian.net/browse/MEN-4014))
* mender-client: Add DBus busconfig files.
([MEN-4030](https://northerntech.atlassian.net/browse/MEN-4030))
* mender-client: The self-signed Mender server certificate, if
present, is copied to ca-certificates in addition to
`MENDER_CERT_LOCATION` to be trusted by other services running in the
device. ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* mender-client: fix QA Issue: invalid PACKAGECONFIG: inventory-network-scripts
* Rename mender-shell to mender-connect
([MEN-4292](https://northerntech.atlassian.net/browse/MEN-4292))
* Add mender-binary-delta 1.1.1 and 1.2.0.
* Add the MENDER_CONNECT_SHELL to meta-mender-core, defaults to /bin/sh
* Add recipe mender-connect 1.0.0
* Add recipe mender-client 2.5.0
* Add recipe mender-artifact 3.5.0
* Add mender-artifact 3.4.1 recipe.
* Add mender-client 2.3.2 and 2.4.2 recipes.
* Fix broken demo certificate in production recipes.
* mender-connect: Correct ShellCommand key in config file

## meta-mender warrior-v2021.02

_Released 02.22.2021_

### Statistics

A total of 272 lines added, 180 removed (delta 92)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 13 (43.3%) |
| Lluis Campos | 12 (40.0%) |
| Fabio Tranchitella | 5 (16.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 202 (64.3%) |
| Kristian Amlie | 77 (24.5%) |
| Fabio Tranchitella | 35 (11.1%) |

| Developers with the most signoffs (total 8) | |
|---|---|
| Lluis Campos | 8 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 30 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 314 (100.0%) |

| Employers with the most signoffs (total 8) | |
|---|---|
| Northern.tech | 8 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### meta-mender (warrior-v2021.02)

New changes in meta-mender since warrior-v2020.12:

* Make DBus support optional in Mender client with `PACKAGECONFIG`.
It defaults to on, but can be turned off with:
```
PACKAGECONFIG_remove = "dbus"
```
Backported to dunfell, modifying the PACKAGECONFIG defaults and amending
the test.
Backported to warrior, removing the test.
([MEN-4014](https://northerntech.atlassian.net/browse/MEN-4014))
* mender-client: Add DBus busconfig files.
([MEN-4030](https://northerntech.atlassian.net/browse/MEN-4030))
* mender-client: The self-signed Mender server certificate, if
present, is copied to ca-certificates in addition to
`MENDER_CERT_LOCATION` to be trusted by other services running in the
device. ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* mender-client: fix QA Issue: invalid PACKAGECONFIG: inventory-network-scripts
* Rename mender-shell to mender-connect
([MEN-4292](https://northerntech.atlassian.net/browse/MEN-4292))
* Add mender-binary-delta 1.1.1 and 1.2.0.
* Add the MENDER_CONNECT_SHELL to meta-mender-core, defaults to /bin/sh
* Add recipe mender-connect 1.0.0
* Add recipe mender 2.5.0
* Add recipe mender-artifact 3.5.0
* Add mender-artifact 3.4.1 recipe.
* Add mender 2.3.2 and 2.4.2 recipes.
* Fix broken demo certificate in production recipes.
* mender-connect: Correct ShellCommand key in config file

## meta-mender dunfell-v2021.01

_Released 01.26.2021_

### Statistics

A total of 959 lines added, 405 removed (delta 554)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 28 (43.1%) |
| Kristian Amlie | 21 (32.3%) |
| Fabio Tranchitella | 14 (21.5%) |
| Drew Moseley | 1 (1.5%) |
| Ole Petter Orhagen | 1 (1.5%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 439 (41.6%) |
| Fabio Tranchitella | 408 (38.6%) |
| Kristian Amlie | 186 (17.6%) |
| Ole Petter Orhagen | 20 (1.9%) |
| Drew Moseley | 3 (0.3%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 20 (4.9%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Lluis Campos | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 65 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1056 (100.0%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |


### Changelogs

#### meta-mender (dunfell-v2021.01)

New changes in meta-mender since dunfell-v2020.12:

* Make DBus support optional in Mender client with `PACKAGECONFIG`.
It defaults to on, but can be turned off with:
```
PACKAGECONFIG_remove = "dbus"
```
Backported to dunfell, modifying the PACKAGECONFIG defaults and amending
the test. ([MEN-4014](https://northerntech.atlassian.net/browse/MEN-4014))
* mender-client: Add DBus busconfig files.
([MEN-4030](https://northerntech.atlassian.net/browse/MEN-4030))
* mender-client: The self-signed Mender server certificate, if
present, is copied to ca-certificates in addition to
`MENDER_CERT_LOCATION` to be trusted by other services running in the
device. ([MEN-4273](https://northerntech.atlassian.net/browse/MEN-4273))
* meta-mender-demo: install mender-shell
([MEN-4187](https://northerntech.atlassian.net/browse/MEN-4187))
* Revert "mender: Reestablish labels on the root filesystems."
* mender-client: fix QA Issue: invalid PACKAGECONFIG: inventory-network-scripts
* mender-shell: generate and install mender-shell.conf with
required fields. `ServerURL` can be configured setting yocto variable
`MENDER_SERVER_URL`, same as used by mender-client recipe. If a
`mender-shell.conf` file is found in the `SRC_URI` the contents will be
merged. ([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))
* mender-shell: Add `User` to generated mender-shell.conf. The
value of it is configured using `MENDER_SHELL_USER` variable, which
defaults to `nobody` for meta-mender-core and `root` for
meta-mender-demo.
([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))
* Rename mender-shell to mender-connect
([MEN-4292](https://northerntech.atlassian.net/browse/MEN-4292))
* mender-raspberrypi: Make kernel settings conditional
* Remove mender-binary-delta 1.0.0, 1.0.1, and 1.1.0.
All three of these have turned out to be incompatible with
libubootenv, which is used on dunfell and later Yocto branches.
* Add mender-binary-delta 1.1.1 and 1.2.0.
* Add the MENDER_CONNECT_SHELL to meta-mender-core, defaults to /bin/sh
* Add recipe mender-connect 1.0.0
* Add recipe mender-client 2.5.0
* Add recipe mender-artifact 3.5.0
* Add mender-artifact 3.4.1 recipe.
* Add mender-client 2.3.2 and 2.4.2 recipes.
* Fix broken demo certificate in production recipes.
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.7 to 3.12.0.
* Bumps [ubi-reader](https://github.com/jrspruitt/ubi_reader) from 0.6.5 to 0.7.0.
- [Release notes](https://github.com/jrspruitt/ubi_reader/releases)
- [Commits](https://github.com/jrspruitt/ubi_reader/commits)
* Bumps [requests](https://github.com/psf/requests) from 2.22.0 to 2.24.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.22.0...v2.24.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.0.1 to 2.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.0.1...v2.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.3.2 to 6.1.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.3.2...6.1.1)
* Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.7.1 to 2.7.2.
- [Release notes](https://github.com/paramiko/paramiko/releases)
- [Changelog](https://github.com/paramiko/paramiko/blob/master/NEWS)
- [Commits](https://github.com/paramiko/paramiko/compare/2.7.1...2.7.2)
* Bumps alpine from 3.12.0 to 3.12.1.
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.1 to 6.1.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.1...6.1.2)
* Bumps [requests](https://github.com/psf/requests) from 2.24.0 to 2.25.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.24.0...v2.25.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.1.1 to 3.0.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.1.1...v3.0.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.0.0 to 3.1.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.0.0...v3.1.0)
* Bumps alpine from 3.12.1 to 3.12.2.
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.1.0 to 3.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.1.0...v3.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.2 to 6.2.0.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.2...6.2.0)
* Bumps alpine from 3.12.2 to 3.12.3.
* Bumps [psutil](https://github.com/giampaolo/psutil) from 5.7.2 to 5.8.0.
- [Release notes](https://github.com/giampaolo/psutil/releases)
- [Changelog](https://github.com/giampaolo/psutil/blob/master/HISTORY.rst)
- [Commits](https://github.com/giampaolo/psutil/compare/release-5.7.2...release-5.8.0)
* Bumps [requests](https://github.com/psf/requests) from 2.25.0 to 2.25.1.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.25.0...v2.25.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.0 to 6.2.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.2.0...6.2.1)

## meta-mender zeus-v2020.12

_Released 12.16.2020_

### Statistics

A total of 676 lines added, 2800 removed (delta -2124)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 12 (34.3%) |
| Kristian Amlie | 9 (25.7%) |
| Ole Petter Orhagen | 6 (17.1%) |
| Drew Moseley | 3 (8.6%) |
| Kasper Føns | 2 (5.7%) |
| Fabio Tranchitella | 2 (5.7%) |
| Peter Grzybowski | 1 (2.9%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 1826 (56.0%) |
| Lluis Campos | 1329 (40.7%) |
| Kristian Amlie | 84 (2.6%) |
| Fabio Tranchitella | 12 (0.4%) |
| Drew Moseley | 6 (0.2%) |
| Kasper Føns | 5 (0.2%) |
| Peter Grzybowski | 1 (0.0%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 1274 (45.5%) |
| Lluis Campos | 838 (29.9%) |
| Kristian Amlie | 22 (0.8%) |
| Drew Moseley | 2 (0.1%) |

| Developers with the most signoffs (total 5) | |
|---|---|
| Lluis Campos | 3 (60.0%) |
| Kristian Amlie | 2 (40.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 33 (94.3%) |
| Chora | 2 (5.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 3258 (99.8%) |
| Chora | 5 (0.2%) |

| Employers with the most signoffs (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 6 (85.7%) |
| Chora | 1 (14.3%) |

### Changelogs

#### meta-mender (zeus-v2020.12)

New changes in meta-mender since zeus-v2020.10:

* Disable filesystem journal on read-only-rootfs, which
sometimes causes unstable rootfs checksum together with fsck.
([MEN-3912](https://northerntech.atlassian.net/browse/MEN-3912))
* mender: Fix broken patch for mender-systemd-machine-id.
* Remove recipe mender-client 2.3.0
* Add recipe mender-client 2.3.1
* Remove recipe mender-client 2.4.0
* Add recipe mender-client 2.4.1
* New Mender-client configuration option: 'inventory-network-scripts'.
This option, if enabled, installs the inventory-network-scripts in the client.
This is enabled as an option, because the inventory-geo script relies on a
third-party network service to figure out the geographic location of the device,
which may not be something that everyone wants installed on their devices. The
feature is enabled in the standard 'PACKAGECONFIG' for the Mender-client, and is
included unless overridded. To remove it, add
'PACKAGECONFIG_remove_pn-mender-client = "inventory-network-scripts"' to your
local.conf file.
* mender-client: Do not keep resizing if a little space is left unused
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Ensure growfs works on GPT filesystems
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Update LICENSE to include OpenSSL
* Add a recipe for building 'mender-connect', remote shell support.
([MEN-4083](https://northerntech.atlassian.net/browse/MEN-4083))
* meta-mender-demo: install mender-connect
([MEN-4187](https://northerntech.atlassian.net/browse/MEN-4187))
* mender-connect: generate and install mender-connect.conf with
required fields. `ServerURL` can be configured setting yocto variable
`MENDER_SERVER_URL`, same as used by mender-client recipe. If a
`mender-connect.conf` file is found in the `SRC_URI` the contents will be
merged. ([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))
* mender-connect: Add `User` to generated mender-connect.conf. The
value of it is configured using `MENDER_CONNECT_USER` variable, which
defaults to `nobody` for meta-mender-core and `root` for
meta-mender-demo.
([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))

## meta-mender warrior-v2020.12

_Released 12.16.2020_

### Statistics

A total of 750 lines added, 94 removed (delta 656)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 8 (33.3%) |
| Kristian Amlie | 7 (29.2%) |
| Ole Petter Orhagen | 5 (20.8%) |
| Kasper Føns | 2 (8.3%) |
| Drew Moseley | 1 (4.2%) |
| Peter Grzybowski | 1 (4.2%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 534 (68.0%) |
| Ole Petter Orhagen | 166 (21.1%) |
| Kristian Amlie | 76 (9.7%) |
| Kasper Føns | 5 (0.6%) |
| Drew Moseley | 3 (0.4%) |
| Peter Grzybowski | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 13 (13.8%) |
| Drew Moseley | 2 (2.1%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Lluis Campos | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 22 (91.7%) |
| Chora | 2 (8.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 780 (99.4%) |
| Chora | 5 (0.6%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 5 (83.3%) |
| Chora | 1 (16.7%) |

### Changelogs

#### meta-mender (warrior-v2020.12)

New changes in meta-mender since warrior-v2020.10:

* Disable `64bit` ext4 filesystem feature.
([MEN-3513](https://northerntech.atlassian.net/browse/MEN-3513))
* Disable filesystem journal on read-only-rootfs, which
sometimes causes unstable rootfs checksum together with fsck.
([MEN-3912](https://northerntech.atlassian.net/browse/MEN-3912))
* mender: Fix broken patch for mender-systemd-machine-id.
* Remove recipe mender-client 2.3.0
* Add recipe mender-client 2.3.1
* Remove recipe mender-client 2.4.0
* Add recipe mender-client 2.4.1
* New Mender-client configuration option: 'inventory-network-scripts'.
This option, if enabled, installs the inventory-network-scripts in the client.
This is enabled as an option, because the inventory-geo script relies on a
third-party network service to figure out the geographic location of the device,
which may not be something that everyone wants installed on their devices. The
feature is enabled in the standard 'PACKAGECONFIG' for the Mender-client, and is
included unless overridded. To remove it, add
'PACKAGECONFIG_remove_pn-mender-client = "inventory-network-scripts"' to your
local.conf file.
* mender-client: Do not keep resizing if a little space is left unused
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Ensure growfs works on GPT filesystems
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Update LICENSE to include OpenSSL
* Add a recipe for building 'mender-connect', remote shell support.
([MEN-4083](https://northerntech.atlassian.net/browse/MEN-4083))
* meta-mender-demo: install mender-connect
([MEN-4187](https://northerntech.atlassian.net/browse/MEN-4187))
* mender-connect: generate and install mender-connect.conf with
required fields. `ServerURL` can be configured setting yocto variable
`MENDER_SERVER_URL`, same as used by mender-client recipe. If a
`mender-connect.conf` file is found in the `SRC_URI` the contents will be
merged. ([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))
* mender-connect: Add `User` to generated mender-connect.conf. The
value of it is configured using `MENDER_CONNECT_USER` variable, which
defaults to `nobody` for meta-mender-core and `root` for
meta-mender-demo.
([MEN-4242](https://northerntech.atlassian.net/browse/MEN-4242))

## meta-mender dunfell-v2020.12

_Released 12.08.2020_

### Statistics

A total of 547 lines added, 1726 removed (delta -1179)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (38.9%) |
| Ole Petter Orhagen | 5 (27.8%) |
| Lluis Campos | 3 (16.7%) |
| Kasper Føns | 2 (11.1%) |
| Drew Moseley | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 1823 (87.5%) |
| Kristian Amlie | 143 (6.9%) |
| Lluis Campos | 111 (5.3%) |
| Kasper Føns | 5 (0.2%) |
| Drew Moseley | 2 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 1275 (73.9%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Kristian Amlie | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 16 (88.9%) |
| Chora | 2 (11.1%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 2079 (99.8%) |
| Chora | 5 (0.2%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| Chora | 1 (20.0%) |

### Changelogs

#### meta-mender (dunfell-v2020.12)

New changes in meta-mender since dunfell-v2020.11:

* mender: Reestablish labels on the root filesystems.
* New Mender-client configuration option: 'inventory-network-scripts'.
This option, if enabled, installs the inventory-network-scripts in the client.
This is enabled as an option, because the inventory-geo script relies on a
third-party network service to figure out the geographic location of the device,
which may not be something that everyone wants installed on their devices. The
feature is enabled in the standard 'PACKAGECONFIG' for the Mender-client, and is
included unless overridded. To remove it, add
'PACKAGECONFIG_remove_pn-mender-client = "inventory-network-scripts"' to your
local.conf file.
* mender-client: Do not keep resizing if a little space is left unused
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Ensure growfs works on GPT filesystems
([MEN-4176](https://northerntech.atlassian.net/browse/MEN-4176))
* mender-client: Update LICENSE to include OpenSSL
* mender-client: Include OpenSSL license from 2.4.x onwards.
* Add a recipe for building 'mender-connect', remote shell support.
([MEN-4083](https://northerntech.atlassian.net/browse/MEN-4083))
* Fix a parsing issue where `inherit` could not be used with
variables that had been defined with overrides that depended on
`MENDER_FEATURES_ENABLE`. One example would be:
```
MYVAR_mender-grub = "grub-efi"
inherit ${MYVAR}
```

## meta-mender dunfell-v2020.11

_Released 11.16.2020_

### Statistics

A total of 6 lines added, 1067 removed (delta -1061)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 3 (50.0%) |
| Lluis Campos | 2 (33.3%) |
| Drew Moseley | 1 (16.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 922 (86.4%) |
| Ole Petter Orhagen | 142 (13.3%) |
| Drew Moseley | 3 (0.3%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 921 (86.3%) |
| Ole Petter Orhagen | 138 (12.9%) |
| Drew Moseley | 2 (0.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 6 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1067 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2020.11)

New changes in meta-mender since dunfell-v2020.10:

* mender: Fix broken patch for mender-systemd-machine-id.
* Remove recipe mender-client 2.3.0
* Add recipe mender-client 2.3.1
* Remove recipe mender-client 2.4.0
* Add recipe mender-client 2.4.1
* Aggregated Dependabot Changelogs:
* Bumps [tests/acceptance/image-tests](https://github.com/mendersoftware/mender-image-tests) from `457ea99` to `713c563`.
- [Release notes](https://github.com/mendersoftware/mender-image-tests/releases)
- [Commits](https://github.com/mendersoftware/mender-image-tests/compare/457ea99937642ec29da53a9a2d30a51067cf8dc0...713c56364b79a18ad86e6731b1a602f0f3d9d233)
* Bump tests/acceptance/image-tests from `457ea99` to `713c563`

## meta-mender dunfell-v2020.10

_Released 10.13.2020_

### Statistics

A total of 334 lines added, 431 removed (delta -97)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 17 (53.1%) |
| Kristian Amlie | 8 (25.0%) |
| Lluis Campos | 2 (6.2%) |
| Ole Petter Orhagen | 2 (6.2%) |
| Fabio Tranchitella | 2 (6.2%) |
| Peter Grzybowski | 1 (3.1%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 315 (65.9%) |
| Kristian Amlie | 129 (27.0%) |
| Ole Petter Orhagen | 15 (3.1%) |
| Fabio Tranchitella | 12 (2.5%) |
| Lluis Campos | 6 (1.3%) |
| Peter Grzybowski | 1 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Drew Moseley | 114 (26.5%) |

| Developers with the most signoffs (total 5) | |
|---|---|
| Lluis Campos | 5 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 32 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 478 (100.0%) |

| Employers with the most signoffs (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 6 (100.0%) |

### Changelogs

#### meta-mender (dunfell-v2020.10)

New changes in meta-mender since dunfell-v2020.09:

* Disable filesystem journal on read-only-rootfs, which
sometimes causes unstable rootfs checksum together with fsck.
([MEN-3912](https://northerntech.atlassian.net/browse/MEN-3912))
* mender: Make Mender settings conditional.
* meta-mender-demo: Make Mender settings conditional.
* meta-mender-raspberrypi-demo: Make Mender settings conditional.
* meta-mender-qemu: Make Mender settings conditional.
* tests/mender: Make Mender settings conditional.
* mender-grub: Rework to use conditional includes.
* mender-uboot: Conditionally include settings.
* mender: Only include full mender-setup if features are enabled.
* mender-binary-delta: Only add SRC_URI entries for existing binaries.
* grub-mender-grubenv: Cleanup PROVIDES and RPROVIDES.
* mender: Switch from include to require.
* Fix PACKAGECONFIG not propagating RDEPENDS properly.

## meta-mender zeus-v2020.10

_Released 10.05.2020_

### Statistics

A total of 86545 lines added, 31 removed (delta 86514)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 5 (27.8%) |
| Lluis Campos | 4 (22.2%) |
| Peter Grzybowski | 2 (11.1%) |
| Daniel Selvan D | 1 (5.6%) |
| Kristian Amlie | 1 (5.6%) |
| Mirza Krak | 1 (5.6%) |
| Kasper Føns | 1 (5.6%) |
| Kurt Kiefer | 1 (5.6%) |
| Marek Belisko | 1 (5.6%) |
| Ossian Riday | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 86467 (99.9%) |
| Marek Belisko | 47 (0.1%) |
| Peter Grzybowski | 10 (0.0%) |
| Drew Moseley | 9 (0.0%) |
| Kurt Kiefer | 7 (0.0%) |
| Kristian Amlie | 4 (0.0%) |
| Ossian Riday | 3 (0.0%) |
| Kasper Føns | 2 (0.0%) |
| Daniel Selvan D | 1 (0.0%) |
| Mirza Krak | 1 (0.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 13 (72.2%) |
| kekiefer@gmail.com | 1 (5.6%) |
| danilselvan@gmail.com | 1 (5.6%) |
| ossian.riday@gmail.com | 1 (5.6%) |
| Chora | 1 (5.6%) |
| open-nandra | 1 (5.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 86491 (99.9%) |
| open-nandra | 47 (0.1%) |
| kekiefer@gmail.com | 7 (0.0%) |
| ossian.riday@gmail.com | 3 (0.0%) |
| Chora | 2 (0.0%) |
| danilselvan@gmail.com | 1 (0.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 10) | |
|---|---|
| Northern.tech | 5 (50.0%) |
| open-nandra | 1 (10.0%) |
| kekiefer@gmail.com | 1 (10.0%) |
| ossian.riday@gmail.com | 1 (10.0%) |
| Chora | 1 (10.0%) |
| danilselvan@gmail.com | 1 (10.0%) |

### Changelogs

#### meta-mender (zeus-v2020.10)

New changes in meta-mender since zeus-v2020.07:

* []MBR systems don't have a backup header, so always return true
([MEN-3761](https://northerntech.atlassian.net/browse/MEN-3761))
* u-boot: Fix raspberrypi-cm3 u-boot hang
* mender-client: fix install of systemd-machine-id.service
* initramfs-module-install-efi: Ensure variable changes are reflected on rebuild
* mender-commercial: Cleanup BBFILES.
* Warn when detecting U-Boot version without script '=' support.
([MEN-3851](https://northerntech.atlassian.net/browse/MEN-3851))
* Add mender-client 2.4.0 recipe.
* OpenSSL: qemu: set SECLEVEL=2 in /etc/ssl/openssl.cnf
([MEN-3730](https://northerntech.atlassian.net/browse/MEN-3730))
* Fixed key extraction by skipping new lines in defconfig.
The `add_kconfig_option_with_depends.py` file throws `Not sure how to
handle Kconfig option that doesn't start with 'CONFIG_'` when the
provided defconfig file contains blank lines. It has been fixed by
checking for empty lines before processing for keys.
* Add recipe go 1.14 from dunfell
* Use golang 1.14 in meta-mender-core layer to support Ed25519
public keys for signing and transport in the Mender client.

## meta-mender warrior-v2020.10

_Released 10.05.2020_

### Statistics

A total of 86487 lines added, 100 removed (delta 86387)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 7 (46.7%) |
| Lluis Campos | 3 (20.0%) |
| Peter Grzybowski | 1 (6.7%) |
| Mirza Krak | 1 (6.7%) |
| Kristian Amlie | 1 (6.7%) |
| Michael Davis | 1 (6.7%) |
| Kasper Føns | 1 (6.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 86463 (99.9%) |
| Drew Moseley | 92 (0.1%) |
| Peter Grzybowski | 9 (0.0%) |
| Kristian Amlie | 4 (0.0%) |
| Kasper Føns | 2 (0.0%) |
| Mirza Krak | 1 (0.0%) |
| Michael Davis | 1 (0.0%) |

| Developers with the most lines removed | |
|---|---|
| Drew Moseley | 73 (73.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 13 (86.7%) |
| Election Systems & Software | 1 (6.7%) |
| Chora | 1 (6.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 86569 (100.0%) |
| Chora | 2 (0.0%) |
| Election Systems & Software | 1 (0.0%) |

| Employers with the most signoffs (total 0) | |
|---|---|

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 5 (71.4%) |
| Chora | 1 (14.3%) |
| Election Systems & Software | 1 (14.3%) |

### Changelogs

#### meta-mender (warrior-v2020.10)

New changes in meta-mender since warrior-v2020.07:

* initramfs-module-install-efi: Ensure variable changes are reflected on rebuild
* mender-grub: Dynamically determine mender_grub_storage_device.
* mender-grub: Add regexp module.
* Deprecate MENDER_GRUB_STORAGE_DEVICE variable.
* mender: Add sanity check to ensure partuuid with X86.
* vexpress: Remove nonexistent kernel config options that issue warnings.
* mender-commercial: Cleanup BBFILES.
* mender: Add additonal x86 arch to partuuid sanity check
* Warn when detecting U-Boot version without script '=' support.
([MEN-3851](https://northerntech.atlassian.net/browse/MEN-3851))
* Add mender-client 2.4.0 recipe.
* OpenSSL: qemu: set SECLEVEL=2 in /etc/ssl/openssl.cnf
([MEN-3730](https://northerntech.atlassian.net/browse/MEN-3730))
* Add recipe go 1.14 from dunfell
* Use golang 1.14 in meta-mender-core layer to support Ed25519
public keys for signing and transport in the Mender client.

## meta-mender thud-v2020.10

_Released 10.05.2020_

### Statistics

A total of 82 lines added, 38 removed (delta 44)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 7 (43.8%) |
| Lluis Campos | 3 (18.8%) |
| Gaurav Kalra | 2 (12.5%) |
| Matthew Beckler | 2 (12.5%) |
| Joerg Hofrichter | 1 (6.2%) |
| Kristian Amlie | 1 (6.2%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 55 (63.2%) |
| Lluis Campos | 16 (18.4%) |
| Kristian Amlie | 10 (11.5%) |
| Gaurav Kalra | 2 (2.3%) |
| Matthew Beckler | 2 (2.3%) |
| Joerg Hofrichter | 2 (2.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 11 (68.8%) |
| Packet Power LLC | 2 (12.5%) |
| National Instruments | 1 (6.2%) |
| gvkalra@gmail.com | 1 (6.2%) |
| SM Instruments Inc. | 1 (6.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 81 (93.1%) |
| Packet Power LLC | 2 (2.3%) |
| National Instruments | 2 (2.3%) |
| gvkalra@gmail.com | 1 (1.1%) |
| SM Instruments Inc. | 1 (1.1%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 3 (42.9%) |
| Packet Power LLC | 1 (14.3%) |
| National Instruments | 1 (14.3%) |
| gvkalra@gmail.com | 1 (14.3%) |
| SM Instruments Inc. | 1 (14.3%) |

### Changelogs

#### meta-mender (thud-v2020.10)

New changes in meta-mender since thud-v2019.12:

* grub-mender-grubenv: Fix broken debug-log PACKAGECONFIG.
* grub-efi: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* mender-grub: Set EFI_PROVIDER to grub-efi.
* remove stray '-' in IMAGE_NAME
* systemd-boot: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* Add mender 2.2.0b1 recipe
* Add mender-artifact 3.3.0b1 recipe
* In demo mode, put demo certificate in same directory as Debian package.
([MEN-3048](https://northerntech.atlassian.net/browse/MEN-3048))
* mender-helpers: Error out if copying different files to boot part.
* Improve warning when multiple DTB files are in KERNEL_DEVICETREE
* Add MENDER_DTB_NAME_FORCE to mender-vars.json to avoid unrecognized variable warning
* rpi: fix rootfs cmdline trailing space
* Add mender 2.2.1 recipe
* Add mender-artifact 3.3.1 recipe
* Remove mender 2.2.0b1 recipe
* Remove mender-artifact 3.3.0b1 recipe

## meta-mender sumo-v2020.10

_Released 10.05.2020_

### Statistics

A total of 52 lines added, 60 removed (delta -8)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 5 (45.5%) |
| Lluis Campos | 2 (18.2%) |
| Matthew Beckler | 2 (18.2%) |
| Gaurav Kalra | 1 (9.1%) |
| Kristian Amlie | 1 (9.1%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 49 (55.1%) |
| Drew Moseley | 27 (30.3%) |
| Kristian Amlie | 10 (11.2%) |
| Matthew Beckler | 2 (2.2%) |
| Gaurav Kalra | 1 (1.1%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 35 (58.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 8 (72.7%) |
| Packet Power LLC | 2 (18.2%) |
| SM Instruments Inc. | 1 (9.1%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 86 (96.6%) |
| Packet Power LLC | 2 (2.2%) |
| SM Instruments Inc. | 1 (1.1%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 3 (60.0%) |
| Packet Power LLC | 1 (20.0%) |
| SM Instruments Inc. | 1 (20.0%) |

### Changelogs

#### meta-mender (sumo-v2020.10)

New changes in meta-mender since sumo-v2019.12:

* grub-mender-grubenv: Fix broken debug-log PACKAGECONFIG.
* grub-efi: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* mender-grub: Set EFI_PROVIDER to grub-efi.
* systemd-boot: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* Add mender 2.2.0b1 recipe
* Add mender-artifact 3.3.0b1 recipe
* In demo mode, put demo certificate in same directory as Debian package.
([MEN-3048](https://northerntech.atlassian.net/browse/MEN-3048))
* Improve warning when multiple DTB files are in KERNEL_DEVICETREE
* Add MENDER_DTB_NAME_FORCE to mender-vars.json to avoid unrecognized variable warning
* rpi: fix rootfs cmdline trailing space
* Add mender 2.2.1 recipe
* Add mender-artifact 3.3.1 recipe
* Remove mender 2.2.0b1 recipe
* Remove mender-artifact 3.3.0b1 recipe

## meta-mender rocko-v2020.10

_Released 10.05.2020_

### Statistics

A total of 201 lines added, 147 removed (delta 54)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 6 (46.2%) |
| Kristian Amlie | 6 (46.2%) |
| Ole Petter Orhagen | 1 (7.7%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 157 (55.5%) |
| Ole Petter Orhagen | 113 (39.9%) |
| Lluis Campos | 13 (4.6%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 82 (55.8%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 13 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 283 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### meta-mender (rocko-v2020.10)

New changes in meta-mender since rocko-v2019.08:

* Add meta-mender-commercial layer.
This will host our mender-binary-delta Update Module.
* Update recipe for mender-binary-delta pre-release v0.1.1
* `FILESEXTRAPATHS_prepend_pn-mender-binary-delta` now needs
to point to the folder containing `arm`, `aarch64` and `x86_64`, not the folder
containing the binary.
* Update recipe for mender-binary-delta beta release v1.0.0b1
* Update recipe for mender-binary-delta final release v1.0.0
* Add mender 2.2.1 recipe
* Add mender-artifact 3.3.1 recipe
* Remove mender 2.1.0b1 recipe
* Remove mender-artifact 3.1.0b1 recipe
* Removes the tests covering Mender-Artifact version 1.
([MEN-2156](https://northerntech.atlassian.net/browse/MEN-2156))

## meta-mender dunfell-v2020.09

_Released 09.17.2020_

### Statistics

A total of 70 lines added, 136 removed (delta -66)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 5 (26.3%) |
| Peter Grzybowski | 3 (15.8%) |
| Lluis Campos | 2 (10.5%) |
| Kurt Kiefer | 2 (10.5%) |
| Daniel Selvan D | 1 (5.3%) |
| Kristian Amlie | 1 (5.3%) |
| Ole Petter Orhagen | 1 (5.3%) |
| Marek Belisko | 1 (5.3%) |
| Mirza Krak | 1 (5.3%) |
| Kasper Føns | 1 (5.3%) |

| Developers with the most changed lines | |
|---|---|
| Marek Belisko | 64 (36.2%) |
| Drew Moseley | 45 (25.4%) |
| Peter Grzybowski | 35 (19.8%) |
| Lluis Campos | 12 (6.8%) |
| Kurt Kiefer | 9 (5.1%) |
| Kristian Amlie | 4 (2.3%) |
| Ossian Riday | 3 (1.7%) |
| Kasper Føns | 2 (1.1%) |
| Daniel Selvan D | 1 (0.6%) |
| Ole Petter Orhagen | 1 (0.6%) |

| Developers with the most lines removed | |
|---|---|
| Marek Belisko | 64 (47.1%) |
| Drew Moseley | 34 (25.0%) |
| Lluis Campos | 6 (4.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 13 (68.4%) |
| kekiefer@gmail.com | 2 (10.5%) |
| danilselvan@gmail.com | 1 (5.3%) |
| ossian.riday@gmail.com | 1 (5.3%) |
| Chora | 1 (5.3%) |
| open-nandra | 1 (5.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 98 (55.4%) |
| open-nandra | 64 (36.2%) |
| kekiefer@gmail.com | 9 (5.1%) |
| ossian.riday@gmail.com | 3 (1.7%) |
| Chora | 2 (1.1%) |
| danilselvan@gmail.com | 1 (0.6%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 11) | |
|---|---|
| Northern.tech | 6 (54.5%) |
| open-nandra | 1 (9.1%) |
| kekiefer@gmail.com | 1 (9.1%) |
| ossian.riday@gmail.com | 1 (9.1%) |
| Chora | 1 (9.1%) |
| danilselvan@gmail.com | 1 (9.1%) |

### Changelogs

#### meta-mender (dunfell-v2020.09)

New changes in meta-mender since dunfell-v2020.07:

* []MBR systems don't have a backup header, so always return true
([MEN-3761](https://northerntech.atlassian.net/browse/MEN-3761))
* Fix error that no recipe provides bcm2835-bootfiles.
* mender-client: fix install of systemd-machine-id.service
* initramfs-module-install-efi: Ensure variable changes are reflected on rebuild
* vexpress: Remove nonexistent kernel config options that issue warnings.
* mender-commercial: Cleanup BBFILES.
* libubootenv: Drop bbappend file
* libubootenv: add RPROVIDES for u-boot-default-env
* Add mender-client 2.4.0 recipe.
* OpenSSL: qemu: set SECLEVEL=2 in /etc/ssl/openssl.cnf
([MEN-3730](https://northerntech.atlassian.net/browse/MEN-3730))
* Fixed key extraction by skipping new lines in defconfig.
The `add_kconfig_option_with_depends.py` file throws `Not sure how to
handle Kconfig option that doesn't start with 'CONFIG_'` when the
provided defconfig file contains blank lines. It has been fixed by
checking for empty lines before processing for keys.
* Add mender-client 2.4.0 recipe.

## meta-mender warrior-v2020.07

_Released 07.29.2020_

### Statistics

A total of 171 lines added, 54 removed (delta 117)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 4 (50.0%) |
| Lluis Campos | 1 (12.5%) |
| Ossian Riday | 1 (12.5%) |
| Trevor Woerner | 1 (12.5%) |
| Garrett Brown | 1 (12.5%) |

| Developers with the most changed lines | |
|---|---|
| Garrett Brown | 147 (71.7%) |
| Kristian Amlie | 51 (24.9%) |
| Ossian Riday | 3 (1.5%) |
| Lluis Campos | 2 (1.0%) |
| Trevor Woerner | 2 (1.0%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 33 (61.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 5 (62.5%) |
| twoerner@gmail.com | 1 (12.5%) |
| Aclima Inc. | 1 (12.5%) |
| ossian.riday@gmail.com | 1 (12.5%) |

| Top lines changed by employer | |
|---|---|
| Aclima Inc. | 147 (71.7%) |
| Northern.tech | 53 (25.9%) |
| ossian.riday@gmail.com | 3 (1.5%) |
| twoerner@gmail.com | 2 (1.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 2 (40.0%) |
| Aclima Inc. | 1 (20.0%) |
| ossian.riday@gmail.com | 1 (20.0%) |
| twoerner@gmail.com | 1 (20.0%) |

### Changelogs

#### meta-mender (warrior-v2020.07)

New changes in meta-mender since warrior-v2020.06:

* Fix boot failure on ARM UEFI devices because of missing
`regexp` module. A typical error log looks like this:
```
Welcome to GRUB!
```
* Fix EFI boot partition corruption with mtools 4.0.19
* uboot_auto_configure: build U-Boot the same way Yocto does
* Add mender_2.3.0 and mender-artifact_3.4.0 recipes.
* Add mender-2.2.1 and mender-artifact-3.3.1 recipes.
* Add mender-binary-delta-1.1.0 release.
* MBR systems don't have a backup header, so always return true
([MEN-3761](https://northerntech.atlassian.net/browse/MEN-3761))

## meta-mender dunfell-v2020.07

_Released 07.28.2020_

### Statistics

A total of 895 lines added, 2274 removed (delta -1379)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 26 (83.9%) |
| Peter Grzybowski | 1 (3.2%) |
| Lluis Campos | 1 (3.2%) |
| Corey Cothrum | 1 (3.2%) |
| Ole Petter Orhagen | 1 (3.2%) |
| Trevor Woerner | 1 (3.2%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 2435 (96.4%) |
| Corey Cothrum | 72 (2.8%) |
| Ole Petter Orhagen | 14 (0.6%) |
| Peter Grzybowski | 2 (0.1%) |
| Lluis Campos | 2 (0.1%) |
| Trevor Woerner | 2 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 1459 (64.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 29 (93.5%) |
| twoerner@gmail.com | 1 (3.2%) |
| contact@coreycothrum.com | 1 (3.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 2453 (97.1%) |
| contact@coreycothrum.com | 72 (2.8%) |
| twoerner@gmail.com | 2 (0.1%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 4 (66.7%) |
| contact@coreycothrum.com | 1 (16.7%) |
| twoerner@gmail.com | 1 (16.7%) |

### Changelogs

#### meta-mender (dunfell-v2020.07)

New changes in meta-mender since zeus-v2020.06:

* uboot_auto_configure: build U-Boot the same way Yocto does
* Fix error message about `CONFIG_ENV_OFFSET` being wrong,
such as:
```
ERROR: u-boot-fw-utils-mender-auto-provided-1.0-r0 do_configure: U-Boot configuration rpi_4_config has setting:
CONFIG_ENV_OFFSET=0x400000
CONFIG_ENV_OFFSET_REDUND=0x800000
but Mender expects:
CONFIG_ENV_OFFSET=0x800000
Please fix U-Boot’s configuration file.
```
* add support for separate A/B kernel partitions
* Add MENDER_EXTRA_PARTS_SIZES_MB variable
* U-Boot auto-configuration: Better algorithm for removing
options from defconfig files. This increases board compatibility.
* Start using libubootenv for U-Boot environment manipulation.
This deprecates the u-boot-fw-utils tools, which have been removed
from upstream. The functionality and command line API is the same.
* `libubootenv` is now used instead of `u-boot-fw-utils`. If
you have a "fw-utils" type recipe in your layer, you probably need to
remove it, particularly if it references `u-boot-mender-common.inc`.
* Patch broken UBI support in libubootenv_0.2.
* chmod 600 on mender.conf
([MEN-3762](https://northerntech.atlassian.net/browse/MEN-3762))
* Add mender-2.2.1 and mender-artifact-3.3.1 recipes.
* Add mender-2.3.0 and mender-artifact-3.4.0 recipes.
* Add mender-binary-delta-1.1.0 release.
* Remove mender-client recipes that are incompatible with dunfell.
([MEN-3764](https://northerntech.atlassian.net/browse/MEN-3764))
* Fix incorrect BOOTENV_SIZE value being used in libubootenv
recipe. The symptom of this was a non-working set of `fw_printenv` and
`fw_setenv` tools:
```
root@raspberrypi4:~# fw_printenv
Cannot read environment, using default
Cannot read default environment from file
```
([MEN-3834](https://northerntech.atlassian.net/browse/MEN-3834))
* Fix fsck running on every boot in dunfell.
## meta-mender zeus-v2020.07

_Released 07.16.2020_

### Statistics

A total of 203 lines added, 1050 removed (delta -847)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 15 (83.3%) |
| Trevor Woerner | 1 (5.6%) |
| Ole Petter Orhagen | 1 (5.6%) |
| Lluis Campos | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 1145 (98.5%) |
| Ole Petter Orhagen | 14 (1.2%) |
| Trevor Woerner | 2 (0.2%) |
| Lluis Campos | 2 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 862 (82.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 17 (94.4%) |
| twoerner@gmail.com | 1 (5.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1161 (99.8%) |
| twoerner@gmail.com | 2 (0.2%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| twoerner@gmail.com | 1 (25.0%) |

### Changelogs

#### meta-mender (zeus-v2020.07)

New changes in meta-mender since zeus-v2020.06:

* Fix error message about `CONFIG_ENV_OFFSET` being wrong,
such as:
```
ERROR: u-boot-fw-utils-mender-auto-provided-1.0-r0 do_configure: U-Boot configuration rpi_4_config has setting:
CONFIG_ENV_OFFSET=0x400000
CONFIG_ENV_OFFSET_REDUND=0x800000
but Mender expects:
CONFIG_ENV_OFFSET=0x800000
Please fix U-Boot’s configuration file.
```
* add support for separate A/B kernel partitions
* U-Boot auto-configuration: Better algorithm for removing
options from defconfig files. This increases board compatibility.
* uboot_auto_configure: build U-Boot the same way Yocto does
* Add mender-2.2.1 and mender-artifact-3.3.1 recipes.
* Add mender-2.3.0 and mender-artifact-3.4.0 recipes.
* Add mender-binary-delta-1.1.0 release.

## meta-mender zeus-v2020.06

_Released 06.12.2020_

### Statistics

A total of 7169 lines added, 4936 removed (delta 2233)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 79 (41.4%) |
| Ole Petter Orhagen | 33 (17.3%) |
| Lluis Campos | 22 (11.5%) |
| Drew Moseley | 19 (9.9%) |
| Marcin Pasinski | 10 (5.2%) |
| Mirza Krak | 9 (4.7%) |
| Alf-Rune Siqveland | 4 (2.1%) |
| Joerg Hofrichter | 3 (1.6%) |
| Marek Belisko | 2 (1.0%) |
| Gaurav Kalra | 2 (1.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 3006 (33.1%) |
| Ole Petter Orhagen | 2699 (29.7%) |
| Joerg Hofrichter | 1522 (16.8%) |
| Marcin Pasinski | 1016 (11.2%) |
| Drew Moseley | 275 (3.0%) |
| Mirza Krak | 244 (2.7%) |
| Marek Belisko | 163 (1.8%) |
| Lluis Campos | 101 (1.1%) |
| Alf-Rune Siqveland | 19 (0.2%) |
| Joris Offouga | 16 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 839 (17.0%) |
| Joris Offouga | 16 (0.3%) |

| Developers with the most signoffs (total 4) | |
|---|---|
| Maciej Borzecki | 2 (50.0%) |
| Kristian Amlie | 1 (25.0%) |
| Drew Moseley | 1 (25.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 176 (92.1%) |
| National Instruments | 3 (1.6%) |
| walkbase | 2 (1.0%) |
| Packet Power LLC | 2 (1.0%) |
| open-nandra | 2 (1.0%) |
| BayLibre | 1 (0.5%) |
| alex.misch901@gmail.com | 1 (0.5%) |
| guillaume.kh.alt@gmail.com | 1 (0.5%) |
| SM Instruments Inc. | 1 (0.5%) |
| offougajoris@gmail.com | 1 (0.5%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 7360 (81.1%) |
| National Instruments | 1522 (16.8%) |
| open-nandra | 163 (1.8%) |
| offougajoris@gmail.com | 16 (0.2%) |
| walkbase | 8 (0.1%) |
| Packet Power LLC | 2 (0.0%) |
| BayLibre | 1 (0.0%) |
| alex.misch901@gmail.com | 1 (0.0%) |
| guillaume.kh.alt@gmail.com | 1 (0.0%) |
| SM Instruments Inc. | 1 (0.0%) |

| Employers with the most signoffs (total 4) | |
|---|---|
| Northern.tech | 2 (50.0%) |
| RnDity | 2 (50.0%) |

| Employers with the most hackers (total 17) | |
|---|---|
| Northern.tech | 7 (41.2%) |
| National Instruments | 1 (5.9%) |
| open-nandra | 1 (5.9%) |
| offougajoris@gmail.com | 1 (5.9%) |
| walkbase | 1 (5.9%) |
| Packet Power LLC | 1 (5.9%) |
| BayLibre | 1 (5.9%) |
| alex.misch901@gmail.com | 1 (5.9%) |
| guillaume.kh.alt@gmail.com | 1 (5.9%) |
| SM Instruments Inc. | 1 (5.9%) |


### Changelogs

#### meta-mender (zeus-v2020.06)

New changes in meta-mender since warrior-v2020.06:

* Removes the tests covering Mender-Artifact version 1.
([MEN-2156](https://northerntech.atlassian.net/browse/MEN-2156))
* Add mender 2.1.1 and mender-artifact 3.2.0b1 recipes.
* Update recipe for mender-binary-delta beta release v1.0.0b1
* Remove mender-2.0.x and older, and mender-artifact 3.0.x
and older.
* mender-setup: do not add systemd options to fstab without mender-systemd
* Enable Artifact Depends and Provides for Yocto builds
Enables the ability to set:
* Artifact Depends
* Artifact Provides
* Artifact Name Depends
* Artifact Provides Group
* Artifact Depends Groups
In the Mender Artifact from the Yocto build,
through the build variables:
MENDER_ARTIFACT_NAME_DEPENDS -- List of names
MENDER_ARTIFACT_PROVIDES -- Key:Value
MENDER_ARTIFACT_DEPENDS -- Key:Value
MENDER_ARTIFACT_PROVIDES_GROUP -- Name
MENDER_ARTIFACT_DEPENDS_GROUPS -- List of names
([MEN-1670](https://northerntech.atlassian.net/browse/MEN-1670))
* Add mender-artifact 3.2.0 and remove beta.
* Upgrade client acceptance tests to Python3
* Update recipe for mender-binary-delta final release v1.0.0
* mender-setup: allow setting fstab options for the boot partition
* mender-image: Add DEPENDS to include WKS_FILE_DEPENDS.
* Update uboot_auto_patch script to be compatible with U-Boot 2019.10
* Add mender 2.1.2 recipe
* Add mender-artifact 3.1.1 recipe
* Add mender-artifact 3.2.1 recipe
* Add mender-binar-delta 1.0.1 recipe
* Add 'datatar' as an image type.
* Upgrade to new grub-mender-grubenv.
* Remove outdated grub-mender-grubenv_1.3.0 recipe.
* systemd-boot: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* grub-efi: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* mender-grub: Set EFI_PROVIDER to grub-efi.
* mender-helpers: Error out if copying different files to boot part.
* demo: Support systemd Predictable Network Names.
* grub-mender-grubenv: Fix broken debug-log PACKAGECONFIG.
* mender-part-images: Added handling for extra partitions
* mender-artifact: make it available in SDK
* remove stray '-' in IMAGE_NAME
* Fix failure in boot log when `MENDER_EXTRA_PARTS` is used.
`mender-growfs-data` and `MENDER_EXTRA_PARTS` are mutually exclusive,
so set the default of `mender-growfs-data` to off if
`MENDER_EXTRA_PARTS` is being used.
* Improve warning when multiple DTB files are in KERNEL_DEVICETREE
* In demo mode, put demo certificate in same directory as Debian package.
([MEN-3048](https://northerntech.atlassian.net/browse/MEN-3048))
* Add mender 2.2.0b1 recipe
* Add mender-artifact 3.3.0b1 recipe
* mender: Add signature/secure-boot support.
* Remove mender-artifact 3.1 recipes (EOL).
* Add MENDER_DTB_NAME_FORCE to mender-vars.json to avoid unrecognized variable warning
* rpi: fix rootfs cmdline trailing space
* mender-helper: Added handling for MENDER_EXTRA_PARTS_FSTAB
* Improve dependency logic to not require U-Boot unconditionally on ARM.
This will help when not using `mender-grub`, and instead using
Barebox, for example.
* Make sure partitions are marked for fsck'ing by default.
* Follow e2fsprogs version bump from 1.44 to 1.45.
* Follow systemd feature rename from time-epoch to set-time-epoch.
* systemd-conf: Fix missing FILES section which is mandatory on zeus.
* Work around missing LSB support in zeus.
This is a very intrusive change, which creates the `/lib64` symlink on
the root filesystem for 64-bit systems. This symlink is normally
missing when building with Yocto, but was provided by the LSB package
previously. The directory is necessary to remain compatible with
software built outside of Yocto. The Mender demo artifact, as well as
the binary delta update module are examples of such components.
If the link turns out to conflict with another package, it should be
possible to work around the problem by adding this to the other
package, either in the original `.bb` file or a `.bbappend` file:
```
RPROVIDES_${PN} += "lsb-ld"
```
* Enable CONFIG_EFI_STUB on kernels when booting with UEFI on ARM.
* Add mender 2.2.0 recipe and remove beta
* Add mender-artifact 3.3.0 recipe and remove beta
* Add mender 2.1.3 recipe
* raspberrypi4: update U-Boot patches to apply to 2019.07 version
([MEN-3262](https://northerntech.atlassian.net/browse/MEN-3262))
* Renamed mender -> mender-client
This renaming was done to conform with the new naming introduced. This helps
seperate Mender (the product), from Mender-client, which is a part of the
aforementioned product.
The renaming is due in parts:
* The 'mender.service' systemd recipe is now named 'mender-client.service'
* The bitbake recipes are now renamed from 'mender%.bb' to 'mender-client%.bb'
* The Mender feature 'mender-install' is now 'mender-client-install'
* The mender directory holding the mender-client recipe is also renamed 'mender-client'
* Upgrade to U-Boot 2020.01 and GRUB 2.04 to fix Beaglebone support.
* Updated the LIC_FILES_CHECKSUM after removing dependencies
([MEN-3251](https://northerntech.atlassian.net/browse/MEN-3251))
* mender-grub: Dynamically determine mender_grub_storage_device.
* mender-grub: Add regexp module.
* Deprecate MENDER_GRUB_STORAGE_DEVICE variable.
* raspberrypi: add state script to update boot firmware
Raspberry Pi boards have a set of boot firmware files that are
located on the vfat boot part, and these files are not updated
when you perform an update of the root filesystem.
Occasionally there will be changes to the Raspberry Pi software stack
that requires that these files are update. Typically there is something
in the Linux kernel that requires something that is in the boot
firmware. This means that to update the Linux kernel you must also
update the boot firmware files.
Above is really sub-optimal design of the Raspberry Pi boards but a
limitation that we must live with.
Note that the DTB files are also part of "boot firmware" and included in
the state script update.
The provided state-script can be enabled by adding the following to e.g
local.conf:
INHERIT += "rpi-update-firmware"
The ArtifactInstall_Leave_50 script can be overriden to customize what
files to update, e.g only DTB files. By default all files on the boot
part will be updated including config.txt and cmdline.txt.
NOTE! Updating the boot firmware files can not be done atomically and the
files are not roll-backed even though an rootfs rollback is performed. Conclusion,
this is an risky operating which could brick your device.
* Fix infinite loop which would eat all available memory
on the build host, when using U-Boot v2020.01 or later together with
the auto-patcher.
([MEN-3265](https://northerntech.atlassian.net/browse/MEN-3265))
* Updated the LIC_FILES_CHECKSUM after removing dependencies
([MEN-3251](https://northerntech.atlassian.net/browse/MEN-3251))
* mender: Add sanity check for partuuid and uboot.
* grubenv: Handle debug command prompt when running as EFI
app.
* write GPT partition table before resize of data part
([MEN-3366](https://northerntech.atlassian.net/browse/MEN-3366))
* raspberrypi: busybox compatibility for boot firmware state script
* grub: Move dynamic storage handling into grub-mender-grubenv repository.
* U-Boot versions from v2020.01 onwards have moved several C
code defines into Kconfig, which may require changes in board specific
patches. Specifically, `CONFIG_ENV_SIZE`, `CONFIG_ENV_OFFSET` and
`CONFIG_ENV_OFFSET_REDUND` now need to be defined in the board's
`defconfig` file. In addition, the redundant environment now need to
be specifically enabled, using the new switch,
`CONFIG_SYS_REDUNAND_ENVIRONMENT`. If you are using
`MENDER_UBOOT_AUTO_CONFIGURE=1`, then this is handled automatically,
but if not you will need to add this to your board's `defconfig` file:
```
CONFIG_SYS_REDUNAND_ENVIRONMENT=y
CONFIG_ENV_SIZE=0x20000
CONFIG_ENV_OFFSET=0x800000
CONFIG_ENV_OFFSET_REDUND=0x1000000
```
Note that the values may differ from the values you actually need,
these are just the defaults from the meta-mender Yocto
layer. `CONFIG_ENV_SIZE` need to match the `MENDER_ENV_SIZE` Bitbake
variable, and `CONFIG_ENV_OFFSET` and `CONFIG_ENV_OFFSET_REDUND`
should (usually) be 1x and 2x the `MENDER_PARTITION_ALIGNMENT`
variable. If the values are not as expected, then you will get an
error during the compile stage.
* Fix OOM issue on the build host if certain configuration
options are missing from the defconfig file.
([MEN-3476](https://northerntech.atlassian.net/browse/MEN-3476))
* grub-mender-grubenv: Remove kernel_devicetree.
The only way to use GRUB 2.04 on ARM is via UEFI, and the
kernel_devicetree information is not used when loading via UEFI,
instead it is queried directly from the UEFI provider.
* Make sure that mender-grow-data.service only runs once.
* Boot no longer blocks while the data part is resized, and
instead this is a background process.
* Add OpenSSL as dependency for Git versions of the Mender client.
* Fix U-Boot auto-patcher sometimes adding two conflicting
options to the defconfig file.
([MEN-3514](https://northerntech.atlassian.net/browse/MEN-3514))
* Add mender-client_2.3.0b1 and mender-artifact_3.4.0b1 recipes.
To use the Beta recipes, add this to `local.conf`:
```
PREFERRED_VERSION_pn-mender-client = "2.3.0b1"
PREFERRED_VERSION_pn-mender-artifact = "3.4.0b1"
PREFERRED_VERSION_pn-mender-artifact-native = "3.4.0b1"
```
* Add mender-binary-delta_1.1.0b1 recipe.
To use the beta, add this to `local.conf`:
```
PREFERRED_VERSION_pn-mender-binary-delta = "1.1.0b1"
```
* Disable `64bit` ext4 filesystem feature.
([MEN-3513](https://northerntech.atlassian.net/browse/MEN-3513))
* Remove mender-client < 2.2, and mender-artifact < 3.3 recipes.

## meta-mender warrior-v2020.06

_Released 06.08.2020_

### Statistics

A total of 166 lines added, 163 removed (delta 3)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 6 (35.3%) |
| Ole Petter Orhagen | 5 (29.4%) |
| Mirza Krak | 4 (23.5%) |
| Drew Moseley | 2 (11.8%) |

| Developers with the most changed lines | |
|---|---|
| Mirza Krak | 123 (48.2%) |
| Kristian Amlie | 121 (47.5%) |
| Drew Moseley | 6 (2.4%) |
| Ole Petter Orhagen | 5 (2.0%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 83 (50.9%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 17 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 255 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### meta-mender (warrior-v2020.06)

New changes in meta-mender since warrior-v2020.05:

* Make sure that mender-grow-data.service only runs once.
* Boot no longer blocks while the data part is resized, and
instead this is a background process.
* Add OpenSSL as dependency for Git versions of the Mender client.
* Add mender_2.3.0b1 and mender-artifact_3.4.0b1 recipes.
To use the Beta recipes, add this to `local.conf`:
```
PREFERRED_VERSION_pn-mender = "2.3.0b1"
PREFERRED_VERSION_pn-mender-artifact = "3.4.0b1"
PREFERRED_VERSION_pn-mender-artifact-native = "3.4.0b1"
```
* Add mender-binary-delta_1.1.0b1 recipe.
To use the beta, add this to `local.conf`:
```
PREFERRED_VERSION_pn-mender-binary-delta = "1.1.0b1"
```

## meta-mender warrior-v2020.05

_Released 05.05.2020_

### Statistics

A total of 7 lines added, 7 removed (delta 0)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 3 (42.9%) |
| Ole Petter Orhagen | 2 (28.6%) |
| Mirza Krak | 1 (14.3%) |
| Guillaume Khayat | 1 (14.3%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 4 (50.0%) |
| Ole Petter Orhagen | 2 (25.0%) |
| Mirza Krak | 1 (12.5%) |
| Guillaume Khayat | 1 (12.5%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 1 (14.3%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Kristian Amlie | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 6 (85.7%) |
| guillaume.kh.alt@gmail.com | 1 (14.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 7 (87.5%) |
| guillaume.kh.alt@gmail.com | 1 (12.5%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| guillaume.kh.alt@gmail.com | 1 (25.0%) |

### Changelogs

#### meta-mender (warrior-v2020.05)

New changes in meta-mender since warrior-v2020.04:

* grubenv: Handle debug command prompt when running as EFI
app.
* raspberrypi: busybox compatibility for boot firmware state script
* grub: Move dynamic storage handling into grub-mender-grubenv repository.
* write GPT partition table before resize of data part
([MEN-3366](https://northerntech.atlassian.net/browse/MEN-3366))

## meta-mender warrior-v2020.04

_Released 04.08.2020_

### Statistics

A total of 206 lines added, 47 removed (delta 159)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 2 (28.6%) |
| Mirza Krak | 1 (14.3%) |
| Lluis Campos | 1 (14.3%) |
| Ole Petter Orhagen | 1 (14.3%) |
| Alf-Rune Siqveland | 1 (14.3%) |
| Drew Moseley | 1 (14.3%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 115 (47.7%) |
| Mirza Krak | 70 (29.0%) |
| Drew Moseley | 42 (17.4%) |
| Lluis Campos | 7 (2.9%) |
| Alf-Rune Siqveland | 6 (2.5%) |
| Ole Petter Orhagen | 1 (0.4%) |

| Developers with the most lines removed | |
|---|---|
| Drew Moseley | 35 (74.5%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 7 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 241 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 6 (100.0%) |

### Changelogs

#### meta-mender (warrior-v2020.04)

New changes in meta-mender since warrior-v2020.03:

* mender-grub: Dynamically determine mender_grub_storage_device.
* mender-grub: Add regexp module.
* Deprecate MENDER_GRUB_STORAGE_DEVICE variable.
* Updated the LIC_FILES_CHECKSUM after removing dependencies
([MEN-3251](https://northerntech.atlassian.net/browse/MEN-3251))
* raspberrypi: add state script to update boot firmware
Raspberry Pi boards have a set of boot firmware files that are
located on the vfat boot part, and these files are not updated
when you perform an update of the root filesystem.
Occasionally there will be changes to the Raspberry Pi software stack
that requires that these files are update. Typically there is something
in the Linux kernel that requires something that is in the boot
firmware. This means that to update the Linux kernel you must also
update the boot firmware files.
Above is really sub-optimal design of the Raspberry Pi boards but a
limitation that we must live with.
Note that the DTB files are also part of "boot firmware" and included in
the state script update.
The provided state-script can be enabled by adding the following to e.g
local.conf:
INHERIT += "rpi-update-firmware"
The ArtifactInstall_Leave_50 script can be overriden to customize what
files to update, e.g only DTB files. By default all files on the boot
part will be updated including config.txt and cmdline.txt.
NOTE! Updating the boot firmware files can not be done atomically and the
files are not roll-backed even though an rootfs rollback is performed. Conclusion,
this is an risky operating which could brick your device.

## meta-mender warrior-v2020.03

_Released 03.09.2020_

### Statistics

A total of 182 lines added, 157 removed (delta 25)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 5 (38.5%) |
| Kristian Amlie | 4 (30.8%) |
| Lluis Campos | 3 (23.1%) |
| Joris Offouga | 1 (7.7%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 244 (75.5%) |
| Lluis Campos | 43 (13.3%) |
| Kristian Amlie | 20 (6.2%) |
| Joris Offouga | 16 (5.0%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 23 (14.6%) |
| Joris Offouga | 16 (10.2%) |
| Kristian Amlie | 4 (2.5%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (92.3%) |
| offougajoris@gmail.com | 1 (7.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 307 (95.0%) |
| offougajoris@gmail.com | 16 (5.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| offougajoris@gmail.com | 1 (25.0%) |

### Changelogs

#### meta-mender (warrior-v2020.03)

New changes in meta-mender since warrior-v2020.02.2:

* systemd: move network configurations to systemd-conf
* Add 'datatar' as an image type.
* Remove outdated grub-mender-grubenv_1.3.0 recipe.
* Upgrade to new grub-mender-grubenv.
* mender: Add signature/secure-boot support.
* Add mender 2.2.0 recipe and remove beta
* Add mender-artifact 3.3.0 recipe and remove beta
* Add mender 2.1.3 recipe
* Improve dependency logic to not require U-Boot unconditionally on ARM.
This will help when not using `mender-grub`, and instead using
Barebox, for example.

## meta-mender warrior-v2020.02.2

_Released 02.18.2020_

### Statistics

A total of 26 lines added, 7 removed (delta 19)

| Developers with the most changesets | |
|---|---|
| Matthew Beckler | 2 (40.0%) |
| Gaurav Kalra | 1 (20.0%) |
| Joerg Hofrichter | 1 (20.0%) |
| Drew Moseley | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 21 (80.8%) |
| Matthew Beckler | 2 (7.7%) |
| Joerg Hofrichter | 2 (7.7%) |
| Gaurav Kalra | 1 (3.8%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Packet Power LLC | 2 (40.0%) |
| National Instruments | 1 (20.0%) |
| SM Instruments Inc. | 1 (20.0%) |
| Northern.tech | 1 (20.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 21 (80.8%) |
| Packet Power LLC | 2 (7.7%) |
| National Instruments | 2 (7.7%) |
| SM Instruments Inc. | 1 (3.8%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 1 (25.0%) |
| Packet Power LLC | 1 (25.0%) |
| National Instruments | 1 (25.0%) |
| SM Instruments Inc. | 1 (25.0%) |

### Changelogs

#### meta-mender (warrior-v2020.02.2)

New changes in meta-mender since warrior-v2020.02:

* mender-helpers: Error out if copying different files to boot part.
* Improve warning when multiple DTB files are in KERNEL_DEVICETREE
* Add MENDER_DTB_NAME_FORCE to mender-vars.json to avoid unrecognized variable warning
* rpi: fix rootfs cmdline trailing space

## meta-mender warrior-v2020.02

_Released 02.12.2020_

### Statistics

A total of 69 lines added, 42 removed (delta 27)

| Developers with the most changesets | |
|---|---|
| Drew Moseley | 7 (43.8%) |
| Kristian Amlie | 6 (37.5%) |
| Lluis Campos | 1 (6.2%) |
| Gaurav Kalra | 1 (6.2%) |
| Benjamin Byholm | 1 (6.2%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 36 (45.6%) |
| Kristian Amlie | 25 (31.6%) |
| Lluis Campos | 10 (12.7%) |
| Benjamin Byholm | 7 (8.9%) |
| Gaurav Kalra | 1 (1.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 14 (87.5%) |
| walkbase | 1 (6.2%) |
| gvkalra@gmail.com | 1 (6.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 71 (89.9%) |
| walkbase | 7 (8.9%) |
| gvkalra@gmail.com | 1 (1.3%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 3 (60.0%) |
| walkbase | 1 (20.0%) |
| gvkalra@gmail.com | 1 (20.0%) |

### Changelogs

#### meta-mender (warrior-v2020.02)

New changes in meta-mender since warrior-v2019.12:

* mender-setup: allow setting fstab options for the boot partition
* grub-mender-grubenv: Fix broken debug-log PACKAGECONFIG.
* grub-efi: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* mender-grub: Set EFI_PROVIDER to grub-efi.
* remove stray '-' in IMAGE_NAME
* systemd-boot: Respect MENDER_BOOT_PART_MOUNT_LOCATION
* Add mender 2.2.0b1 recipe
* Add mender-artifact 3.3.0b1 recipe
* In demo mode, put demo certificate in same directory as Debian package.
([MEN-3048](https://northerntech.atlassian.net/browse/MEN-3048))

## meta-mender thud-v2019.12

_Released 12.17.2019_

### Statistics

A total of 597 lines added, 366 removed (delta 231)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 17 (39.5%) |
| Lluis Campos | 10 (23.3%) |
| Drew Moseley | 9 (20.9%) |
| Mirza Krak | 4 (9.3%) |
| Ole Petter Orhagen | 1 (2.3%) |
| Joerg Hofrichter | 1 (2.3%) |
| Pierre-Jean Texier | 1 (2.3%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 370 (48.2%) |
| Drew Moseley | 140 (18.3%) |
| Ole Petter Orhagen | 113 (14.7%) |
| Lluis Campos | 83 (10.8%) |
| Mirza Krak | 58 (7.6%) |
| Pierre-Jean Texier | 2 (0.3%) |
| Joerg Hofrichter | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 82 (22.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 41 (95.3%) |
| KONCEPTO | 1 (2.3%) |
| National Instruments | 1 (2.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 764 (99.6%) |
| KONCEPTO | 2 (0.3%) |
| National Instruments | 1 (0.1%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 5 (71.4%) |
| KONCEPTO | 1 (14.3%) |
| National Instruments | 1 (14.3%) |

### Changelogs

#### meta-mender (thud-v2019.12)

New changes in meta-mender since thud-v2019.08:

* Add meta-mender-commercial layer.
This will host our mender-binary-delta Update Module.
* Update recipe for mender-binary-delta pre-release v0.1.1
* u-boot-fw-utils: set PACKAGE_ARCH as MACHINE_ARCH
* Add mender-2.1.0 and mender-artifact-3.1.0.
* Fix "set_image_size" errors when large files are installed
in /data directory (staging area for data partition filesystem image)
* mender-systemd: Maintain persistent machine-id across updates.
* Start using Git SHA based grub-mender-grubenv versions.
* Add grub-mender-grubenv 1.3.0 recipe.
* Add support for initramfs when booting using GRUB.
* grub-mender-grubenv: Setup debug option to drop to grub prompt.
* Fix initramfs builds when using meta-mender layer
* mender: Scan for devices with the live installer
* `FILESEXTRAPATHS_prepend_pn-mender-binary-delta` now needs
to point to the folder containing `arm`, `aarch64` and `x86_64`, not the folder
containing the binary.
* Update recipe for mender-binary-delta beta release v1.0.0b1
* Update recipe for mender-binary-delta final release v1.0.0
* Fix incorrect boot partition type for EFI boot partitions.
* Fix issue where U-boot is not able to find a valid DTB on Raspberry Pi boards
* Add mender 2.1.1 and mender-artifact 3.2.0b1 recipes.
* Add mender-artifact 3.2.0 and remove beta.
* mender-image: Add DEPENDS to include WKS_FILE_DEPENDS.
* Add mender 2.1.2 recipe
* Add mender-artifact 3.1.1 recipe
* Add mender-artifact 3.2.1 recipe
* Add mender-binar-delta 1.0.1 recipe
* Removes the tests covering Mender-Artifact version 1.
([MEN-2156](https://northerntech.atlassian.net/browse/MEN-2156))

## meta-mender sumo-v2019.12

_Released 12.17.2019_

### Statistics

A total of 353 lines added, 241 removed (delta 112)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 10 (34.5%) |
| Lluis Campos | 9 (31.0%) |
| Drew Moseley | 6 (20.7%) |
| Ole Petter Orhagen | 1 (3.4%) |
| Joerg Hofrichter | 1 (3.4%) |
| Mirza Krak | 1 (3.4%) |
| Ajith P V | 1 (3.4%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 168 (34.4%) |
| Drew Moseley | 130 (26.6%) |
| Ole Petter Orhagen | 113 (23.1%) |
| Lluis Campos | 41 (8.4%) |
| Mirza Krak | 35 (7.2%) |
| Joerg Hofrichter | 1 (0.2%) |
| Ajith P V | 1 (0.2%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 82 (34.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 27 (93.1%) |
| National Instruments | 1 (3.4%) |
| ajithpv@outlook.com | 1 (3.4%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 487 (99.6%) |
| National Instruments | 1 (0.2%) |
| ajithpv@outlook.com | 1 (0.2%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 5 (71.4%) |
| National Instruments | 1 (14.3%) |
| ajithpv@outlook.com | 1 (14.3%) |

### Changelogs

#### meta-mender (sumo-v2019.12)

New changes in meta-mender since sumo-v2019.08:

* Add meta-mender-commercial layer.
This will host our mender-binary-delta Update Module.
* Update recipe for mender-binary-delta pre-release v0.1.1
* `FILESEXTRAPATHS_prepend_pn-mender-binary-delta` now needs
to point to the folder containing `arm`, `aarch64` and `x86_64`, not the folder
containing the binary.
* Update recipe for mender-binary-delta beta release v1.0.0b1
* Update recipe for mender-binary-delta final release v1.0.0
* mender-image: Add DEPENDS to include WKS_FILE_DEPENDS.
* mender: Use += rather than _append for IMAGE_FSTYPES.
* mender-systemd: Maintain persistent machine-id across updates.
* Add 'datatar' as an image type.
* Fix issue where U-boot is not able to find a valid DTB on Raspberry Pi boards
* Add mender-2.1.0 and mender-artifact-3.1.0.
* Add mender 2.1.1 and mender-artifact 3.2.0b1 recipes.
* Add mender-artifact 3.2.0 and remove beta.
* Add mender 2.1.2 recipe
* Add mender-artifact 3.1.1 recipe
* Add mender-artifact 3.2.1 recipe
* Add mender-binar-delta 1.0.1 recipe
* Removes the tests covering Mender-Artifact version 1.
([MEN-2156](https://northerntech.atlassian.net/browse/MEN-2156))

## meta-mender warrior-v2019.12

_Released 12.10.2019_

### Statistics

A total of 13 lines added, 8 removed (delta 5)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 3 (50.0%) |
| Drew Moseley | 2 (33.3%) |
| Joerg Hofrichter | 1 (16.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 6 (46.2%) |
| Drew Moseley | 6 (46.2%) |
| Joerg Hofrichter | 1 (7.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 5 (83.3%) |
| National Instruments | 1 (16.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 12 (92.3%) |
| National Instruments | 1 (7.7%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| National Instruments | 1 (33.3%) |

### Changelogs

#### meta-mender (warrior-v2019.12)

New changes in meta-mender since warrior-v2019.11:

* Update recipe for mender-binary-delta final release v1.0.0
* mender-image: Add DEPENDS to include WKS_FILE_DEPENDS.
* Add mender 2.1.2 recipe
* Add mender-artifact 3.1.1 recipe
* Add mender-artifact 3.2.1 recipe
* Add mender-binary-delta 1.0.1 recipe

## meta-mender warrior-v2019.11

_Released 10.30.2019_

### Statistics

A total of 11 lines added, 4 removed (delta 7)

| Developers with the most changesets | |
|---|---|
| Benjamin Byholm | 1 (33.3%) |
| Lluis Campos | 1 (33.3%) |
| Alf-Rune Siqveland | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 6 (54.5%) |
| Alf-Rune Siqveland | 4 (36.4%) |
| Benjamin Byholm | 1 (9.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (66.7%) |
| walkbase | 1 (33.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 10 (90.9%) |
| walkbase | 1 (9.1%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| walkbase | 1 (33.3%) |

### Changelogs

#### meta-mender (warrior-v2019.11)

New changes in meta-mender since warrior-v2019.10.2:

* mender-setup: do not add systemd options to fstab without mender-systemd

## meta-mender warrior-v2019.10.2

_Released 10.23.2019_

### Changelogs

#### meta-mender (warrior-v2019.10.2)

New changes in mender-artifact since warrior-v2019.10:

* Add mender-artifact 3.2.0 and remove beta.

## meta-mender warrior-v2019.10

_Released 10.10.2019_

### Statistics

A total of 2540 lines added, 1428 removed (delta 1112)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 74 (46.8%) |
| Lluis Campos | 27 (17.1%) |
| Drew Moseley | 18 (11.4%) |
| Mirza Krak | 15 (9.5%) |
| Ole Petter Orhagen | 7 (4.4%) |
| Pierre-Jean Texier | 5 (3.2%) |
| Paul Barker | 3 (1.9%) |
| Dell Green | 2 (1.3%) |
| Dan Walkes | 1 (0.6%) |
| Bryan Matthews | 1 (0.6%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 1898 (58.0%) |
| Drew Moseley | 333 (10.2%) |
| Mirza Krak | 317 (9.7%) |
| Ole Petter Orhagen | 282 (8.6%) |
| Lluis Campos | 273 (8.3%) |
| Tim Froehlich | 46 (1.4%) |
| Dell Green | 43 (1.3%) |
| Dan Walkes | 40 (1.2%) |
| Pierre-Jean Texier | 14 (0.4%) |
| Bryan Matthews | 9 (0.3%) |

| Developers with the most signoffs (total 6) | |
|---|---|
| Kristian Amlie | 3 (50.0%) |
| Drew Moseley | 2 (33.3%) |
| Mirza Krak | 1 (16.7%) |

| Developers with the most report credits (total 2) | |
|---|---|
| Drew Moseley | 1 (50.0%) |
| Denis Mosolov | 1 (50.0%) |

| Developers who gave the most report credits (total 2) | |
|---|---|
| Kristian Amlie | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 141 (89.2%) |
| KONCEPTO | 5 (3.2%) |
| Beta Five Ltd | 3 (1.9%) |
| Ideaworks Ltd | 2 (1.3%) |
| Konsulko Group | 1 (0.6%) |
| GreenEggs AB | 1 (0.6%) |
| manuel@linux-home.at | 1 (0.6%) |
| Arch Systems Inc. | 1 (0.6%) |
| Trellis-Logic | 1 (0.6%) |
| Reach Technologies Inc | 1 (0.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 3103 (94.8%) |
| Arch Systems Inc. | 46 (1.4%) |
| Ideaworks Ltd | 43 (1.3%) |
| Trellis-Logic | 40 (1.2%) |
| KONCEPTO | 14 (0.4%) |
| Reach Technologies Inc | 9 (0.3%) |
| Beta Five Ltd | 8 (0.2%) |
| Konsulko Group | 8 (0.2%) |
| GreenEggs AB | 1 (0.0%) |
| manuel@linux-home.at | 1 (0.0%) |

| Employers with the most signoffs (total 6) | |
|---|---|
| Northern.tech | 6 (100.0%) |

| Employers with the most hackers (total 15) | |
|---|---|
| Northern.tech | 5 (33.3%) |
| Arch Systems Inc. | 1 (6.7%) |
| Ideaworks Ltd | 1 (6.7%) |
| Trellis-Logic | 1 (6.7%) |
| KONCEPTO | 1 (6.7%) |
| Reach Technologies Inc | 1 (6.7%) |
| Beta Five Ltd | 1 (6.7%) |
| Konsulko Group | 1 (6.7%) |
| GreenEggs AB | 1 (6.7%) |
| manuel@linux-home.at | 1 (6.7%) |

### Changelogs

#### meta-mender (warrior-v2019.10)

New changes in meta-mender since thud-v2019.09:

* part-images: add missing u-boot:deploy dependency for ARM
* Add mender 1.6.1 and 1.7.0 recipes.
* Add mender-artifact 2.3.1 and 2.4.0 recipes.
* Remove unsupported mender 1.5.x series.
* Fix data directory not being empty on rootfs.
([MEN-2290](https://northerntech.atlassian.net/browse/MEN-2290))
* Add grub-mender-grubenv 1.2.1 recipe.
* Fix grub-editenv invocation on platforms where it is called
grub2-editenv.
* Add grub-mender-grubenv 1.3.0 recipe.
* Add support for initramfs when booting using GRUB.
* mender-helpers.bbclass: Add NVMe support
* Set inventory poll interval default to 8h
([MEN-2214](https://northerntech.atlassian.net/browse/MEN-2214))
* mender artifact bbclass image name override variable added.
([MEN-2333](https://northerntech.atlassian.net/browse/MEN-2333))
* grub: ensure "test" module is builtin
* Added bitbake variable to add optional swap partition
([MEN-2361](https://northerntech.atlassian.net/browse/MEN-2361))
* Start using Git SHA based grub-mender-grubenv versions.
* Adapt to new flags in mender-artifact-3.0.0.
* Some core update modules can now be installed by adding
`modules` to the `PACKAGECONFIG` variable of `mender`. They are
included by default when using the meta-mender-demo layer.
([MEN-2383](https://northerntech.atlassian.net/browse/MEN-2383))
* Install `mender-data-dir.service` to create `/data/mender` directory.
* Extended MENDER_DATA_PART_FSTYPE to allow it to be used to
specify the filesystem to be generated. Added support to build the data
partition as btrfs, and for setting mkfs and fstab options
* Change variable to access ubi dataimg, points now to the symlink to prevent yocto rebuild error when timestamp/name of ubimg have changed
* linux-raspberrypi-rt: Add mender settings for the PREEMPT_RT kernel.
* Add mender-2.0.0b1 and mender-artifact-3.0.0b1.
* Add new liblzma dependency for the client.
* Add missing build dep on "xz" in Mender Artifact recipes for
3.0.x versions
* Fix error message `Incorrect Usage: flag provided but not defined: -f`
* Fix mender 2.0.x and mender-artifact 3.0.x recipes to use the
correct branches when fetching the source.
* mender: Do not exclude missing directories.
* Upgrade default state script version to version 3.
* Add recipe for mender-2.0.0 and mender-artifact-3.0.0.
* Enable mender v2 and mender-artifact v3 by default.
* Add recipes for mender-1.7.1 and mender-artifact-2.4.1.
* Fix build failing in do_image_ubimg task
* Demo images now include Yocto LSB package.
([MEN-2421](https://northerntech.atlassian.net/browse/MEN-2421))
* grub-mender-grubenv: Fix broken 'debug-pause' `PACKAGECONFIG`.
* QEMU: Add inventory script for Docker IP and open port 80.
([MEN-2574](https://northerntech.atlassian.net/browse/MEN-2574))
* u-boot-mender: Add define for MENDER_STORAGE_DEVICE
* mender: Add support for a bootimg FSTYPE.
* This new define is to allow builds when no dtb is produced or the dtb is
* Remap port 85 on host to 85 in qemu
* Ensure that artifact and partition images' checksums are equal.
([MEN-2597](https://northerntech.atlassian.net/browse/MEN-2597))
* Add recipes for mender 2.0.1 and mender-artifact 3.0.1
* mender: Setup Live installer with HDDIMG
* rpi: Fix several assignment bugs regarding `MENDER_BOOTLOADER_DEFAULT`.
* mender-systemd: Maintain persistent machine-id across updates.
* Add MENDER_UBOOT_CONFIG_SYS_MMC_ENV_PART variable which can
be used to specify MMC partitions other than the user partition like
mmcblk0boot0 and mmcblk0boot1 for u-boot environment storage.
* grub-mender-grubenv: Setup debug option to drop to grub prompt.
* mender: Scan for devices with the live installer
* Add mender 2.1.0b1 and mender-artifact 3.1.0b1 recipes.
Part of Mender 2.1.0 Beta release.
* Remove outdated mender-1.6.x and mender-artifact-2.3.x recipes.
* layer.conf: set high layer priority
Set a high layer prio to ensure that meta-mender-demo addons (e.g psplash)
are always prioritized above the depended layers (e.g meta-boundary).
* Add meta-mender-commercial layer.
This will host our mender-binary-delta Update Module.
* Update recipe for mender-binary-delta pre-release v0.1.1
* u-boot-fw-utils: set PACKAGE_ARCH as MACHINE_ARCH
* example-state-scripts: use show-artifact instead of parsing file
* Fix incorrect boot partition type for EFI boot partitions.
* Fix initramfs builds when using meta-mender layer
* Fix "set_image_size" errors when large files are installed
in /data directory (staging area for data partition filesystem image)
* Add mender-2.1.0 and mender-artifact-3.1.0.
* Enable dynamic resizing of the data partition
Enable dynamic resize of the data partition on first boot. Meaning that it will
grow the mounted filesystem to full size of the underlying block device. This is
done through enabling systemd's growfs feature. Hereforth the feature is enabled
by default when inheriting from 'mender-full'. The feature can be disabled using
MENDER_FEATURES_DISABLE_append = " mender-growfs-data".
Updated commit message:
([MEN-2337](https://northerntech.atlassian.net/browse/MEN-2337))
* `FILESEXTRAPATHS_prepend_pn-mender-binary-delta` now needs
to point to the folder containing `arm`, `aarch64` and `x86_64`, not the folder
containing the binary.
* meta-mender layers updated to Yocto warrior
* Splits the mender.conf configuration file into a transient
configuration /etc/mender/mender.conf and a persistent congiguration in
/data/mender/mender.conf. This split is enabled by default, and it can
be opt-out by adding `PACKAGECONFIG_remove = "split-mender-config"` to
local.conf. ([MEN-2757](https://northerntech.atlassian.net/browse/MEN-2757))
* Add a new recipe mender-migrate-configuration to ease the
migration of devices with single mender.conf to the new setup of split
configuration files. To build an updgrade for such device, add the
recipe with `IMAGE_INSTALL_append = " mender-migrate-configuration"`,
disable the split feature (for this update only) with
`PACKAGECONFIG_remove = " split-mender-config"`, and specify which
parameters to migrate (at least the partition parameters) with
`MENDER_PERSISTENT_CONFIGURATION_VARS = "RootfsPartA RootfsPartB"`.
([MEN-2757](https://northerntech.atlassian.net/browse/MEN-2757))
* Fix issue where U-boot is not able to find a valid DTB on Raspberry Pi boards
* add support for Raspberry Pi 4
* Removes the tests covering Mender-Artifact version 1.
([MEN-2156](https://northerntech.atlassian.net/browse/MEN-2156))
* Add mender 2.1.1 and mender-artifact 3.2.0b1 recipes.
* Update recipe for mender-binary-delta beta release v1.0.0b1

## meta-mender thud-v2019.09

_Released 09.17.2019_

### Statistics

A total of 224 lines added, 78 removed (delta 146)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 5 (55.6%) |
| Lluis Campos | 3 (33.3%) |
| Pierre-Jean Texier | 1 (11.1%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 159 (71.0%) |
| Lluis Campos | 63 (28.1%) |
| Pierre-Jean Texier | 2 (0.9%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 8 (88.9%) |
| KONCEPTO | 1 (11.1%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 222 (99.1%) |
| KONCEPTO | 2 (0.9%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| KONCEPTO | 1 (33.3%) |

### Changelogs

#### meta-mender (thud-v2019.09)

New changes in meta-mender since thud-v2019.08:

* Add mender-2.1.0 and mender-artifact-3.1.0.
* `FILESEXTRAPATHS_prepend_pn-mender-binary-delta` now needs
to point to the folder containing `armhf` and `x86_64`, not the folder
containing the binary.
([MEN-2702](https://northerntech.atlassian.net/browse/MEN-2702))
* u-boot-fw-utils: set PACKAGE_ARCH as MACHINE_ARCH
* Update recipe for mender-binary-delta pre-release v0.1.1
* Add meta-mender-commercial layer.
This will host our mender-binary-delta Update Module.

## meta-mender rocko-v2019.08

_Released 09.02.2019_

### Statistics

A total of 89 lines added, 121 removed (delta -32)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 8 (44.4%) |
| Kristian Amlie | 5 (27.8%) |
| Drew Moseley | 3 (16.7%) |
| Ole Petter Orhagen | 1 (5.6%) |
| Jonas Norling | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 116 (63.7%) |
| Kristian Amlie | 51 (28.0%) |
| Drew Moseley | 13 (7.1%) |
| Ole Petter Orhagen | 1 (0.5%) |
| Jonas Norling | 1 (0.5%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 71 (58.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 17 (94.4%) |
| GreenEggs AB | 1 (5.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 181 (99.5%) |
| GreenEggs AB | 1 (0.5%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| GreenEggs AB | 1 (20.0%) |

### Changelogs

#### meta-mender (rocko-v2019.08)

New changes in meta-mender since rocko-v2019.05:

* Fix build failing in do_image_ubimg task
* Demo images now include Yocto LSB package.
([MEN-2421](https://northerntech.atlassian.net/browse/MEN-2421))
* QEMU: Add inventory script for Docker IP and open port 80.
([MEN-2574](https://northerntech.atlassian.net/browse/MEN-2574))
* u-boot-mender: Add define for MENDER_STORAGE_DEVICE
* Add recipes for mender 2.0.1 and mender-artifact 3.0.1
* Remap port 85 on host to 85 in qemu
* Add mender 2.1.0b1 and mender-artifact 3.1.0b1 recipes.
Part of Mender 2.1.0 Beta release.

## meta-mender sumo-v2019.08

_Released 09.02.2019_

### Statistics

A total of 93 lines added, 124 removed (delta -31)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 7 (36.8%) |
| Kristian Amlie | 6 (31.6%) |
| Drew Moseley | 4 (21.1%) |
| Ole Petter Orhagen | 1 (5.3%) |
| Jonas Norling | 1 (5.3%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 111 (59.7%) |
| Kristian Amlie | 57 (30.6%) |
| Drew Moseley | 16 (8.6%) |
| Ole Petter Orhagen | 1 (0.5%) |
| Jonas Norling | 1 (0.5%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 71 (57.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 18 (94.7%) |
| GreenEggs AB | 1 (5.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 185 (99.5%) |
| GreenEggs AB | 1 (0.5%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| GreenEggs AB | 1 (20.0%) |

### Changelogs

#### meta-mender (sumo-v2019.08)

New changes in meta-mender since sumo-v2019.05:

* Fix build failing in do_image_ubimg task
* Demo images now include Yocto LSB package.
([MEN-2421](https://northerntech.atlassian.net/browse/MEN-2421))
* QEMU: Add inventory script for Docker IP and open port 80.
([MEN-2574](https://northerntech.atlassian.net/browse/MEN-2574))
* u-boot-mender: Add define for MENDER_STORAGE_DEVICE
* Add recipes for mender 2.0.1 and mender-artifact 3.0.1
* Remap port 85 on host to 85 in qemu
* Add mender 2.1.0b1 and mender-artifact 3.1.0b1 recipes.
Part of Mender 2.1.0 Beta release.

## meta-mender thud-v2019.08

_Released 08.13.2019_

### Statistics

A total of 125 lines added, 109 removed (delta 16)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 6 (42.9%) |
| Lluis Campos | 3 (21.4%) |
| Drew Moseley | 2 (14.3%) |
| Paul Barker | 2 (14.3%) |
| Ole Petter Orhagen | 1 (7.1%) |

| Developers with the most changed lines | |
|---|---|
| Drew Moseley | 87 (42.6%) |
| Lluis Campos | 85 (41.7%) |
| Kristian Amlie | 27 (13.2%) |
| Paul Barker | 4 (2.0%) |
| Ole Petter Orhagen | 1 (0.5%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 79 (72.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (85.7%) |
| Beta Five Ltd | 2 (14.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 200 (98.0%) |
| Beta Five Ltd | 4 (2.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| Beta Five Ltd | 1 (20.0%) |

### Changelogs

#### meta-mender (thud-v2019.08)

New changes in meta-mender since thud-v2019.07:

* Add mender 2.1.0b1 and mender-artifact 3.1.0b1 recipes.
Part of Mender 2.1.0 Beta release.
* mender: Setup Live installer with HDDIMG
* rpi: Fix several assignment bugs regarding `MENDER_BOOTLOADER_DEFAULT`.
* Remap port 85 on host to 85 in qemu

## meta-mender thud-v2019.07

_Released 07.01.2019_

### Statistics

A total of 64 lines added, 20 removed (delta 44)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 6 (46.2%) |
| Lluis Campos | 3 (23.1%) |
| Drew Moseley | 3 (23.1%) |
| Jonas Norling | 1 (7.7%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 52 (81.2%) |
| Lluis Campos | 6 (9.4%) |
| Drew Moseley | 5 (7.8%) |
| Jonas Norling | 1 (1.6%) |

| Developers with the most report credits (total 1) | |
|---|---|
| Drew Moseley | 1 (100.0%) |

| Developers who gave the most report credits (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (92.3%) |
| GreenEggs AB | 1 (7.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 63 (98.4%) |
| GreenEggs AB | 1 (1.6%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| GreenEggs AB | 1 (25.0%) |


### Changelogs

#### meta-mender (thud-v2019.07)

New changes in meta-mender since thud-v2019.05:

* Fix build failing in do_image_ubimg task
* Demo images now include Yocto LSB package.
([MEN-2421](https://northerntech.atlassian.net/browse/MEN-2421))
* QEMU: Add inventory script for Docker IP and open port 80.
([MEN-2574](https://northerntech.atlassian.net/browse/MEN-2574))
* grub-mender-grubenv: Fix broken 'debug-pause' `PACKAGECONFIG`.
* u-boot-mender: Add define for MENDER_STORAGE_DEVICE
* Add recipes for mender 2.0.1 and mender-artifact 3.0.1

## meta-mender rocko-v2019.05

_Released 05.15.2019_

### Statistics

A total of 14 lines added, 12 removed (delta 2)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 2 (40.0%) |
| Mirza Krak | 1 (20.0%) |
| Ajith P Venugopal | 1 (20.0%) |
| Lluis Campos | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 9 (64.3%) |
| Ajith P Venugopal | 2 (14.3%) |
| Lluis Campos | 2 (14.3%) |
| Mirza Krak | 1 (7.1%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (80.0%) |
| ajithpv@outlook.com | 1 (20.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 12 (85.7%) |
| ajithpv@outlook.com | 2 (14.3%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| ajithpv@outlook.com | 1 (25.0%) |


### Changelogs

#### meta-mender (rocko-v2019.05)

New changes in meta-mender since rocko-v2019.04:

* Fix mender 2.0.x and mender-artifact 3.0.x recipes to use the
correct branches when fetching the source.
* Add missing build dependency on "xz" in Mender Artifact recipe for 3.0.0b1 version
* Add recipes for mender-1.7.1 and mender-artifact-2.4.1.
* Add recipes for mender-2.0.0 and mender-artifact-3.0.0.
Note that these recipes are not enabled by default in thud. If you
want to use them, you have to add this to your build configuration:
```
PREFERRED_VERSION_pn-mender = "2.%"
PREFERRED_VERSION_pn-mender-artifact = "3.%"
PREFERRED_VERSION_pn-mender-artifact-native = "3.%"
```
* Fix GRUB start-up on x86 by renaming "boot.efi" to "bootia32.efi"

## meta-mender sumo-v2019.05

_Released 05.15.2019_

### Statistics

A total of 13 lines added, 11 removed (delta 2)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 2 (50.0%) |
| Lluis Campos | 1 (25.0%) |
| Ajith P Venugopal | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 9 (69.2%) |
| Lluis Campos | 2 (15.4%) |
| Ajith P Venugopal | 2 (15.4%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (75.0%) |
| ajithpv@outlook.com | 1 (25.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 11 (84.6%) |
| ajithpv@outlook.com | 2 (15.4%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 2 (66.7%) |
| ajithpv@outlook.com | 1 (33.3%) |


### Changelogs

#### meta-mender (sumo-v2019.05)

New changes in meta-mender since sumo-v2019.04:

* Add missing build dependency on "xz" in Mender Artifact recipe for 3.0.0b1 version
* Fix mender 2.0.x and mender-artifact 3.0.x recipes to use the
correct branches when fetching the source.
* Add recipes for mender-1.7.1 and mender-artifact-2.4.1.
* Add recipes for mender-2.0.0 and mender-artifact-3.0.0.
Note that these recipes are not enabled by default in thud. If you
want to use them, you have to add this to your build configuration:
```
PREFERRED_VERSION_pn-mender = "2.%"
PREFERRED_VERSION_pn-mender-artifact = "3.%"
PREFERRED_VERSION_pn-mender-artifact-native = "3.%"
```

## meta-mender thud-v2019.05

_Released 05.07.2019_

### Statistics

A total of 323 lines added, 204 removed (delta 119)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 15 (68.2%) |
| Drew Moseley | 3 (13.6%) |
| Lluis Campos | 2 (9.1%) |
| Mirza Krak | 2 (9.1%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 396 (91.7%) |
| Mirza Krak | 17 (3.9%) |
| Drew Moseley | 16 (3.7%) |
| Lluis Campos | 3 (0.7%) |

| Developers with the most lines removed | |
|---|---|
| Mirza Krak | 13 (6.4%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 22 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 432 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |


### Changelogs

#### meta-mender (thud-v2019.05)

New changes in meta-mender since thud-v2019.03:

* Add missing build dep on "xz" in Mender Artifact recipes for
3.0.x versions
* Add recipes for mender-1.7.1 and mender-artifact-2.4.1.
* mender: Do not exclude missing directories.
* Add recipes for mender-2.0.0 and mender-artifact-3.0.0.
Note that these recipes are not enabled by default in thud. If you
want to use them, you have to add this to your build configuration:
```
PREFERRED_VERSION_pn-mender = "2.%"
PREFERRED_VERSION_pn-mender-artifact = "3.%"
PREFERRED_VERSION_pn-mender-artifact-native = "3.%"
```
* Fix error message `Incorrect Usage: flag provided but not defined: -f`
* Add new liblzma dependency for the client.
* linux-raspberrypi-rt: Add mender settings for the PREEMPT_RT kernel.
* Fix mender 2.0.x and mender-artifact 3.0.x recipes to use the
correct branches when fetching the source.

## meta-mender rocko-v2019.04

_Released 04.25.2019_

### Statistics

A total of 582 lines added, 209 removed (delta 373)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 19 (67.9%) |
| Lluis Campos | 5 (17.9%) |
| Drew Moseley | 1 (3.6%) |
| Ole Petter Orhagen | 1 (3.6%) |
| Stoyan Bogdanov | 1 (3.6%) |
| Mirza Krak | 1 (3.6%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 575 (85.2%) |
| Lluis Campos | 56 (8.3%) |
| Mirza Krak | 21 (3.1%) |
| Drew Moseley | 14 (2.1%) |
| Stoyan Bogdanov | 8 (1.2%) |
| Ole Petter Orhagen | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 35 (16.7%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Maciej Borzecki | 1 (50.0%) |
| Drew Moseley | 1 (50.0%) |

| Developers with the most report credits (total 1) | |
|---|---|
| Denis Mosolov | 1 (100.0%) |

| Developers who gave the most report credits (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 27 (96.4%) |
| Konsulko Group | 1 (3.6%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 667 (98.8%) |
| Konsulko Group | 8 (1.2%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 1 (50.0%) |
| RnDity | 1 (50.0%) |

| Employers with the most hackers (total 6) | |
|---|---|
| Northern.tech | 5 (83.3%) |
| Konsulko Group | 1 (16.7%) |


### Changelogs

#### meta-mender (rocko-v2019.04)

New changes in meta-mender since rocko-v2018.11.2:

* allow IMAGE_BOOTLOADER_BOOTSECTOR_OFFSET to be aligend to 512 bytes
([MEN-1845](https://northerntech.atlassian.net/browse/MEN-1845))
* Fix missing wpa_supplicant in Raspberry Pi demo images.
* Add mender 1.6.1 and 1.7.0 recipes.
* Add mender-artifact 2.3.1 and 2.4.0 recipes.
* mender-helpers.bbclass: Add NVMe support
* Adapt to new flags in mender-artifact-3.0.0.
* Some core update modules can now be installed by adding
`modules` to the `PACKAGECONFIG` variable of `mender`. They are
included by default when using the meta-mender-demo layer.
([MEN-2383](https://northerntech.atlassian.net/browse/MEN-2383))
* Install `mender-data-dir.service` to create `/data/mender` directory.
* Add mender-2.0.0b1 and mender-artifact-3.0.0b1.
* Add canary value to U-Boot env to catch bootloader/user-space mismatch.
* Fix error message `Incorrect Usage: flag provided but not defined: -f`

## meta-mender sumo-v2019.04

_Released 04.25.2019_

### Statistics

A total of 545 lines added, 720 removed (delta -175)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 17 (63.0%) |
| Lluis Campos | 4 (14.8%) |
| Mirza Krak | 2 (7.4%) |
| Drew Moseley | 1 (3.7%) |
| Manuel Dipolt | 1 (3.7%) |
| Ole Petter Orhagen | 1 (3.7%) |
| Stoyan Bogdanov | 1 (3.7%) |

| Developers with the most changed lines | |
|---|---|
| Mirza Krak | 551 (47.4%) |
| Kristian Amlie | 533 (45.8%) |
| Lluis Campos | 55 (4.7%) |
| Drew Moseley | 14 (1.2%) |
| Stoyan Bogdanov | 8 (0.7%) |
| Manuel Dipolt | 1 (0.1%) |
| Ole Petter Orhagen | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Mirza Krak | 550 (76.4%) |
| Lluis Campos | 36 (5.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Drew Moseley | 1 (100.0%) |

| Developers with the most report credits (total 1) | |
|---|---|
| Denis Mosolov | 1 (100.0%) |

| Developers who gave the most report credits (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 25 (92.6%) |
| Konsulko Group | 1 (3.7%) |
| manuel@linux-home.at | 1 (3.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1154 (99.2%) |
| Konsulko Group | 8 (0.7%) |
| manuel@linux-home.at | 1 (0.1%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 5 (71.4%) |
| Konsulko Group | 1 (14.3%) |
| manuel@linux-home.at | 1 (14.3%) |


### Changelogs

#### meta-mender (sumo-v2019.04)

New changes in meta-mender since sumo-v2018.12:

* mender-helpers.bbclass: Add NVMe support
* add 'rootwait' to bootargs
* Fix data directory not being empty on rootfs.
([MEN-2290](https://northerntech.atlassian.net/browse/MEN-2290))
* Adapt to new flags in mender-artifact-3.0.0.
* Some core update modules can now be installed by adding
`modules` to the `PACKAGECONFIG` variable of `mender`. They are
included by default when using the meta-mender-demo layer.
([MEN-2383](https://northerntech.atlassian.net/browse/MEN-2383))
* Install `mender-data-dir.service` to create `/data/mender` directory.
* Change variable to access ubi dataimg, points now to the symlink to prevent yocto rebuild error when timestamp/name of ubimg have changed
* Add mender-2.0.0b1 and mender-artifact-3.0.0b1.
* Add canary value to U-Boot env to catch bootloader/user-space mismatch.
* Fix error message `Incorrect Usage: flag provided but not defined: -f`

## meta-mender thud-v2019.03

_Released 03.28.2019_

### Statistics

A total of 358 lines added, 95 removed (delta 263)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 12 (75.0%) |
| Lluis Campos | 2 (12.5%) |
| Manuel Dipolt | 1 (6.2%) |
| Mirza Krak | 1 (6.2%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 350 (97.8%) |
| Lluis Campos | 6 (1.7%) |
| Manuel Dipolt | 1 (0.3%) |
| Mirza Krak | 1 (0.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 15 (93.8%) |
| manuel@linux-home.at | 1 (6.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 357 (99.7%) |
| manuel@linux-home.at | 1 (0.3%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| manuel@linux-home.at | 1 (25.0%) |


### Changelogs

#### meta-mender (thud-v2019.03)

New changes in meta-mender since thud-v2019.02:

* Some core update modules can now be installed by adding
`modules` to the `PACKAGECONFIG` variable of `mender`. They are
included by default when using the meta-mender-demo layer.
([MEN-2383](https://northerntech.atlassian.net/browse/MEN-2383))
* Install `mender-data-dir.service` to create `/data/mender` directory.
* Change variable to access ubi dataimg, points now to the symlink to prevent yocto rebuild error when timestamp/name of ubimg have changed
* grub: ensure "test" module is builtin
* Add mender-2.0.0b1 and mender-artifact-3.0.0b1.
* Adapt to new flags in mender-artifact-3.0.0.

## meta-mender thud-v2019.02

_Released 02.08.2019_

### Statistics

A total of 11 lines added, 2 removed (delta 9)

| Developers with the most changesets |           |
|-------------------------------------|-----------|
| Kristian Amlie                      | 2 (50.0%) |
| Moritz Fischer                      | 1 (25.0%) |
| Stoyan Bogdanov                     | 1 (25.0%) |

| Developers with the most changed lines |           |
|----------------------------------------|-----------|
| Stoyan Bogdanov                        | 8 (72.7%) |
| Kristian Amlie                         | 2 (18.2%) |
| Moritz Fischer                         | 1 (9.1%)  |

| Developers with the most report credits (total 1) |            |
|---------------------------------------------------|------------|
| Denis Mosolov                                     | 1 (100.0%) |

| Developers who gave the most report credits (total 1) |            |
|-------------------------------------------------------|------------|
| Kristian Amlie                                        | 1 (100.0%) |

| Top changeset contributors by employer |           |
|----------------------------------------|-----------|
| Northern.tech                          | 2 (50.0%) |
| Konsulko Group                         | 1 (25.0%) |
| Ettus Research                         | 1 (25.0%) |

| Top lines changed by employer |           |
|-------------------------------|-----------|
| Konsulko Group                | 8 (72.7%) |
| Northern.tech                 | 2 (18.2%) |
| Ettus Research                | 1 (9.1%)  |

| Employers with the most hackers (total 3) |           |
|-------------------------------------------|-----------|
| Konsulko Group                            | 1 (33.3%) |
| Northern.tech                             | 1 (33.3%) |
| Ettus Research                            | 1 (33.3%) |

### Changelogs

#### meta-mender (thud-v2019.02)

New changes in meta-mender since thud-v2019.01:

* mender-helpers.bbclass: Add NVMe support

## meta-mender thud-v2019.01

_Released 01.04.2019_

### Statistics

A total of 80 lines added, 103 removed (delta -23)

| Developers with the most changesets |           |
|-------------------------------------|-----------|
| Kristian Amlie                      | 4 (66.7%) |
| Ole Petter Orhagen                  | 1 (16.7%) |
| Mirza Krak                          | 1 (16.7%) |

| Developers with the most changed lines |             |
|----------------------------------------|-------------|
| Kristian Amlie                         | 158 (92.9%) |
| Mirza Krak                             | 11 (6.5%)   |
| Ole Petter Orhagen                     | 1 (0.6%)    |

| Developers with the most lines removed |            |
|----------------------------------------|------------|
| Kristian Amlie                         | 34 (33.0%) |

| Top changeset contributors by employer |            |
|----------------------------------------|------------|
| Northern.tech                          | 6 (100.0%) |

| Top lines changed by employer |              |
|-------------------------------|--------------|
| Northern.tech                 | 170 (100.0%) |

| Employers with the most hackers (total 3) |            |
|-------------------------------------------|------------|
| Northern.tech                             | 3 (100.0%) |


### Changelogs

#### meta-mender (thud-v2019.01)

New changes in meta-mender since thud-v2018.12:

* part-images: add missing u-boot:deploy dependency for ARM
* Add grub-mender-grubenv 1.2.1 recipe.
* Fix grub-editenv invocation on platforms where it is called
grub2-editenv.
* Fix data directory not being empty on rootfs.
([MEN-2290](https://northerntech.atlassian.net/browse/MEN-2290))

## meta-mender sumo-v2018.12

_Released 12.14.2018_

### Statistics

A total of 31 lines added, 39 removed (delta -8)

| Developers with the most changesets |            |
|-------------------------------------|------------|
| Kristian Amlie                      | 3 (100.0%) |

| Developers with the most changed lines |             |
|----------------------------------------|-------------|
| Kristian Amlie                         | 56 (100.0%) |

| Developers with the most lines removed |           |
|----------------------------------------|-----------|
| Kristian Amlie                         | 8 (20.5%) |

| Developers with the most signoffs (total 3) |            |
|---------------------------------------------|------------|
| Kristian Amlie                              | 3 (100.0%) |

| Top changeset contributors by employer |            |
|----------------------------------------|------------|
| Northern.tech                          | 3 (100.0%) |

| Top lines changed by employer |             |
|-------------------------------|-------------|
| Northern.tech                 | 56 (100.0%) |

| Employers with the most signoffs (total 3) |            |
|--------------------------------------------|------------|
| Northern.tech                              | 3 (100.0%) |

| Employers with the most hackers (total 1) |            |
|-------------------------------------------|------------|
| Northern.tech                             | 1 (100.0%) |

### Changelogs

#### meta-mender (sumo-v2018.12)

New changes in meta-mender since sumo-v2018.11.2:

* Fix missing wpa_supplicant in Raspberry Pi demo images.
* Add mender 1.6.1 and 1.7.0 recipes.
* Add mender-artifact 2.3.1 and 2.4.0 recipes.

## meta-mender thud-v2018.12

_Released 12.13.2018_

### Statistics

A total of 3145 lines added, 2930 removed (delta 215)

| Developers with the most changesets |            |
|-------------------------------------|------------|
| Kristian Amlie                      | 76 (73.1%) |
| Drew Moseley                        | 9 (8.7%)   |
| Michael Davis                       | 5 (4.8%)   |
| Adam Podogrocki                     | 3 (2.9%)   |
| Mirza Krak                          | 2 (1.9%)   |
| Marcin Pasinski                     | 2 (1.9%)   |
| David Bensoussan                    | 2 (1.9%)   |
| Dominik Adamski                     | 1 (1.0%)   |
| Leon Anavi                          | 1 (1.0%)   |
| Ole Petter Orhagen                  | 1 (1.0%)   |

| Developers with the most changed lines |              |
|----------------------------------------|--------------|
| Kristian Amlie                         | 3919 (70.7%) |
| Mirza Krak                             | 635 (11.5%)  |
| Adam Podogrocki                        | 512 (9.2%)   |
| Michael Davis                          | 228 (4.1%)   |
| Drew Moseley                           | 113 (2.0%)   |
| Marcin Pasinski                        | 82 (1.5%)    |
| Eystein Måløy Stenberg                 | 41 (0.7%)    |
| Dominik Adamski                        | 4 (0.1%)     |
| David Bensoussan                       | 2 (0.0%)     |
| Leon Anavi                             | 2 (0.0%)     |

| Developers with the most lines removed |             |
|----------------------------------------|-------------|
| Mirza Krak                             | 616 (21.0%) |
| Adam Podogrocki                        | 293 (10.0%) |
| Marcin Pasinski                        | 72 (2.5%)   |
| Drew Moseley                           | 24 (0.8%)   |

| Developers with the most signoffs (total 107) |            |
|-----------------------------------------------|------------|
| Kristian Amlie                                | 77 (72.0%) |
| Drew Moseley                                  | 10 (9.3%)  |
| Michael Davis                                 | 5 (4.7%)   |
| Adam Podogrocki                               | 3 (2.8%)   |
| Mirza Krak                                    | 2 (1.9%)   |
| Marcin Pasinski                               | 2 (1.9%)   |
| David Bensoussan                              | 2 (1.9%)   |
| Leon Anavi                                    | 1 (0.9%)   |
| Thomas Preston                                | 1 (0.9%)   |
| Ole Petter Orhagen                            | 1 (0.9%)   |

| Developers with the most report credits (total 2) |           |
|---------------------------------------------------|-----------|
| Michael Davis                                     | 1 (50.0%) |
| Stoyan Bogdanov                                   | 1 (50.0%) |

| Developers who gave the most report credits (total 2) |           |
|-------------------------------------------------------|-----------|
| Drew Moseley                                          | 1 (50.0%) |
| Leon Anavi                                            | 1 (50.0%) |

| Top changeset contributors by employer |            |
|----------------------------------------|------------|
| Northern.tech                          | 91 (87.5%) |
| Election Systems & Software            | 5 (4.8%)   |
| RnDity                                 | 4 (3.8%)   |
| Synapticon                             | 2 (1.9%)   |
| Konsulko Group                         | 1 (1.0%)   |
| Codethink Ltd.                         | 1 (1.0%)   |

| Top lines changed by employer |              |
|-------------------------------|--------------|
| Northern.tech                 | 4791 (86.5%) |
| RnDity                        | 516 (9.3%)   |
| Election Systems & Software   | 228 (4.1%)   |
| Synapticon                    | 2 (0.0%)     |
| Konsulko Group                | 2 (0.0%)     |
| Codethink Ltd.                | 2 (0.0%)     |

| Employers with the most signoffs (total 107) |            |
|----------------------------------------------|------------|
| Northern.tech                                | 93 (86.9%) |
| RnDity                                       | 5 (4.7%)   |
| Election Systems & Software                  | 5 (4.7%)   |
| Synapticon                                   | 2 (1.9%)   |
| Konsulko Group                               | 1 (0.9%)   |
| Codethink Ltd.                               | 1 (0.9%)   |

| Employers with the most hackers (total 12) |           |
|--------------------------------------------|-----------|
| Northern.tech                              | 6 (50.0%) |
| RnDity                                     | 2 (16.7%) |
| Election Systems & Software                | 1 (8.3%)  |
| Synapticon                                 | 1 (8.3%)  |
| Konsulko Group                             | 1 (8.3%)  |
| Codethink Ltd.                             | 1 (8.3%)  |

### Changelogs

#### meta-mender (thud-v2018.12)

New changes in meta-mender since sumo-v2018.11.2:

* Add mender-artifact 2.4.0b1 recipe.
* Make mkfs.ubifs and ubinize arguments a bit more customizable.
The new variables `MENDER_FLASH_MINIMUM_IO_UNIT` and
`MENDER_MAXIMUM_LEB_COUNT` have been introduced, which maps directly
to the corresponding arguments of the two tools.
* Beaglebone builds no longer compatible with builds from sumo and older.
The reason is that bootloader switched to GRUB. The old build type can
be restored by removing `mender-grub` and adding `mender-uboot` to
`DISTRO_FEATURES` using the `MENDER_FEATURES` variables.
* Fix `IMAGE_ROOTFS_EXCLUDE_PATH` failing when listing a non-existent path.
* Increase default u-boot MTD partition size to 1MiB.
* Fix inability to patch old u-boot variants of MTDPARTS and
MTDIDS correctly.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* Add mender 1.7.0b1 recipe.
* Fix images not being modifiable by mender-artifact in thud and later.
* Add mender 1.5.1 recipe.
* Add mender 1.6.0 recipe.
* Add mender-artifact 2.3.0 recipe.
* Remove support for `loadaddr` variable and
`CONFIG_LOADADDR` config setting in U-Boot. This only affects boards
that use U-Boot as a first stage bootloader in order to use UEFI to
load GRUB as the second stage bootloader. For most boards it should
not be problematic, since most support `kernel_addr_r`. If there is
a problem however, it might be necessary to forward port [this
patch](https://github.com/mendersoftware/meta-mender/blob/b39aa8aeecdf2b8cce3dbcce25ec044073568348/meta-mender-core/recipes-bsp/u-boot/patches/0007-distro_bootcmd-Switch-bootefi-to-use-loadaddr-by-def.patch)
to the U-Boot version in question.
* Fix boot directory being excluded from thud images
* Add some debug functionality to GRUB booting process.
To use it, enable either or both of `debug-log` and `debug-pause` in
`PACKAGECONFIG` for `grub-mender-grubenv`. The former enables debug
logging in GRUB, which can be tweaked further by setting the
`DEBUG_LOG_CATEGORY` variable. The latter pauses the boot process at
strategic points during the boot, so that screen output can be
captured before it is cleared or scrolls by.
* Fix build error when using any hard drive besides sda/hda, such as sdb.
* Images partitioned with GPT or MSDOS partition tables are
now padded up to the nearest alignment specified in
`MENDER_PARTITION_ALIGNMENT`. Previously the last block might be
shorter.
* Remove meta-mender-orangepi and meta-mender-toradex-nxp
as these will be moved to meta-mender-community for the next stable
branch (thud)
* Make sure mtdimg is not truncated, but has its full length.
* Enable EXTERNALSRC to be used with u-boot-fw-utils-mender-auto-provided.
* Allow disabling auto-generated /etc/fstab
* mender: Enable systemd in mender-systemd FEATURE handling.
As long as `mender-systemd` feature is enabled, it is no longer
necessary to include the block:
```
DISTRO_FEATURES_append = " systemd"
VIRTUAL-RUNTIME_init_manager = "systemd"
DISTRO_FEATURES_BACKFILL_CONSIDERED = "sysvinit"
VIRTUAL-RUNTIME_initscripts = ""
```
* Add canary value to U-Boot env to catch bootloader/user-space mismatch.
* GRUB: Fix error about devicetree command not being found.
* Change default storage on x86 to memory card (mmcblk0).
* Reduce partitioning overhead by default.
The current value of 4 * alignment is excessive, since we now take
alignment into account when calculating rootfs size. Instead, only
count overhead lost to partition table, which is 2 * alignment.
* mender: Allow overrides for MENDER_STORAGE_TOTAL_SIZE_MB_DEFAULT.
* Allow boot partition to be populated with normal package recipes.
* Fix `MENDER_GRUB_STORAGE_DEVICE` variable not being respected.
([MEN-2048](https://northerntech.atlassian.net/browse/MEN-2048))
* GRUB: Make kernel console argument configurable using "console_bootargs".
One can set this variable in some "xx_*_grub.cfg" script with an index
lower than 10, in the grub-mender-grubenv recipe.
* uboot_auto_patch: Switch kernel address from `loadaddr`
back to `kernel_addr_r`. This was discussed with U-Boot developers and
is the proper address variable going forward.
* Fix incorrect Flash bad PEB calculation which led to wrong total image size.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* Add mender 1.6.1 and 1.7.0 recipes.
* Add mender-artifact 2.3.1 and 2.4.0 recipes.
* Auto-select correct `MENDER_STORAGE_DEVICE_BASE` scheme.
This should rarely need to be set by anyone anymore.
* Fix confusing warning flood when MENDER_MTDIDS is unset in a UBI build.
* Switch image names from containing `MACHINE` to containing
`MENDER_DEVICE_TYPE`. So for example, if you have a build for the
raspberrypi3 machine type, with device type of "prod_rpi3", the image
will now be called `core-image-minimal-prod_rpi3.sdimg` instead of
`core-image-minimal-raspberrypi3.sdimg`.
* Fix console logging for systemd on QEMU.
* Fix build error when using GRUB and /dev/mmcblk storage device.
* Add specific patches for u-boot-toradex_2016.11.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* grub: Remove restriction that the core.img be at sector 1
* mender-uboot: Use hex for dev/part numbers in U-Boot.
* Delete all components from pre-1.5 Mender releases.
Remove Mender 1.4.0 and 1.4.1 and Mender artifact 2.2.0.
* Introduce support for a standardized boot method on ARM
using UEFI and GRUB. The UEFI boot standard is fully supported on ARM
in theory, but few board manufacturers implement it in practice.
Therefore U-Boot is still utilized, but acts only as a UEFI loader,
and hence no U-Boot integration is needed. All boot scripts are then
handled by GRUB, which needs no patching.
([MEN-1595](https://northerntech.atlassian.net/browse/MEN-1595), [MEN-1659](https://northerntech.atlassian.net/browse/MEN-1659))
* Add support for PARTUUID in grub-mender-grubenv script.
* Remove colibri-imx7-mender MACHINE type, replaced by colibri-imx7.
* Fix regression that removed boot flag from boot partition.
* Fix regression that caused Beaglebone to not boot.
* QEMU: Always try to run with KVM enabled, only fall back to emulation.
* Fix license checksum sometimes failing in
`u-boot-fw-utils-mender-auto-provided` recipe when U-Boot fork has a
slightly different README file.
* Add PARTUUID generation and integration
* Change default bootloader to GRUB on all non-UBI platforms.
U-Boot will still be used on ARM platforms to provide UEFI that GRUB
can use, but it will not be used for Mender integration. To opt out,
and keep using traditional U-Boot integration, remove `mender-grub`,
and add `mender-uboot` using the `MENDER_FEATURES` variables.
* Fixed support for raspberrypi3-64 and aarch64
* mender-uboot: Allow multi-digit partition/device nums.
* Add mender 1.6.0b1 and mender-artifact 2.3.0b1 recipes.
* Remove obsolete mender pre-1.4 and mender-artifact pre-2.2 recipes.
* Fix regression in QEMU launching after changing image name in 897195ddc3f.
* Replaced default yocto cfg file for grub pre configuration by the proper cfg file without redundant and erroneous search command.
* rpi: update U-boot patch to get rid of warning
* Fix incorrect license tag for mender-artifact recipe.
Little practical difference, since they are all permissive licenses.
* Fix missing wpa_supplicant in Raspberry Pi demo images.
* GRUB: Pass kernel arguments from bootargs variable instead of hard coded.
This allows it to be overridden or modified by adding a script snippet
which sets the variable.
Also log kernel messages to both screen and serial port by default,
and have systemd log to serial port (last "console" argument,
apparently it cannot log to both).
* Add support for GPT BIOS images
* Boot script recipe for demoing OTA updates

## meta-mender sumo-v2018.11.2

_Released 11.16.2018_

#### meta-mender (sumo-v2018.11.2)

New changes in meta-mender since sumo-v2018.11:

* Add mender 1.7.0b1 recipe.
* Add mender-artifact 2.4.0b1 recipe.

## meta-mender sumo-v2018.11

_Released 11.12.2018_

#### meta-mender (sumo-v2018.11)

New changes in meta-mender since sumo-v2018.10:

* QEMU: Always try to run with KVM enabled, only fall back to emulation.

## meta-mender sumo-v2018.10

_Released 10.03.2018_

#### meta-mender (sumo-v2018.10)

New changes in meta-mender since sumo-v2018.09:

* Make sure mtdimg is not truncated, but has its full length.
* Add specific patches for u-boot-toradex_2016.11.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* Fix incorrect Flash bad PEB calculation which led to wrong total image size.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* Make mkfs.ubifs and ubinize arguments a bit more customizable.
The new variables `MENDER_FLASH_MINIMUM_IO_UNIT` and
`MENDER_MAXIMUM_LEB_COUNT` have been introduced, which maps directly
to the corresponding arguments of the two tools.
* Fix inability to patch old u-boot variants of MTDPARTS and
MTDIDS correctly.
([MEN-1849](https://northerntech.atlassian.net/browse/MEN-1849))
* Fix confusing warning flood when MENDER_MTDIDS is unset in a UBI build.

## meta-mender sumo-v2018.09

_Released 09.13.2018_

#### meta-mender (sumo-v2018.09)

New changes in meta-mender since sumo-v2018.08:

* Fix regression in QEMU launching after changing image name in 897195ddc3f.
* GRUB: Pass kernel arguments from bootargs variable instead of hard coded.
This allows it to be overridden or modified by adding a script snippet
which sets the variable.
Also log kernel messages to both screen and serial port by default,
and have systemd log to serial port (last "console" argument,
apparently it cannot log to both).
* Introduce support for a standardized boot method on ARM
using UEFI and GRUB. The UEFI boot standard is fully supported on ARM
in theory, but few board manufacturers implement it in practice.
Therefore U-Boot is still utilized, but acts only as a UEFI loader,
and hence no U-Boot integration is needed. All boot scripts are then
handled by GRUB, which needs no patching.
([MEN-1595](https://northerntech.atlassian.net/browse/MEN-1595), [MEN-1659](https://northerntech.atlassian.net/browse/MEN-1659))
* Auto-select correct `MENDER_STORAGE_DEVICE_BASE` scheme.
This should rarely need to be set by anyone anymore.
* Add some debug functionality to GRUB booting process.
To use it, enable either or both of `debug-log` and `debug-pause` in
`PACKAGECONFIG` for `grub-mender-grubenv`. The former enables debug
logging in GRUB, which can be tweaked further by setting the
`DEBUG_LOG_CATEGORY` variable. The latter pauses the boot process at
strategic points during the boot, so that screen output can be
captured before it is cleared or scrolls by.
* GRUB: Fix error about devicetree command not being found.
* Images partitioned with GPT or MSDOS partition tables are
now padded up to the nearest alignment specified in
`MENDER_PARTITION_ALIGNMENT`. Previously the last block might be
shorter.
* Fix build error when using GRUB and /dev/mmcblk storage device.
* Fix build error when using any hard drive besides sda/hda, such as sdb.
* Fix `IMAGE_ROOTFS_EXCLUDE_PATH` failing when listing a non-existent path.
* Fix `MENDER_GRUB_STORAGE_DEVICE` variable not being respected.
([MEN-2048](https://northerntech.atlassian.net/browse/MEN-2048))
* Allow disabling auto-generated /etc/fstab
* Boot script recipe for demoing OTA updates
* mender: Allow overrides for MENDER_STORAGE_TOTAL_SIZE_MB_DEFAULT.
* mender-uboot: Use hex for dev/part numbers in U-Boot.
* Add mender 1.5.1 recipe.
* Add mender 1.6.0 recipe.
* Add mender-artifact 2.3.0 recipe.

## meta-mender sumo-v2018.08

_Released 08.03.2018_

#### meta-mender (sumo-v2018.08)

New changes in meta-mender since sumo-v2018.07:

* Add mender 1.6.0b1 and mender-artifact 2.3.0b1 recipes.
* Fixed support for raspberrypi3-64 and aarch64
* Fix incorrect license tag for mender-artifact recipe.
Little practical difference, since they are all permissive licenses.
* mender-uboot: Allow multi-digit partition/device nums.
* Fix license checksum sometimes failing in
`u-boot-fw-utils-mender-auto-provided` recipe when U-Boot fork has a
slightly different README file.

## meta-mender sumo-v2018.07

_Released 07.12.2018_

#### meta-mender (sumo-v2018.07)
* Warn when mender.conf settings conflict with Bitbake variables.
* Make sure that new-style "enp" network devices get DHCP address in demo.
* Delete all components from pre-1.3 Mender releases.
All pre-1.3 releases are EOL.
* Rename IMAGE_BOOTLOADER* variables to MENDER_IMAGE_BOOTLOADER*.
* Fix lockfile error due to using system lock directory.
* Licence checksum updated in mender-artifact
* mender: Allow for forcing a specific KERNEL_IMAGETYPE.
* mender-uboot: Add MENDER_UBOOT_POST_SETUP_COMMANDS config point.
* Fix occasional inode corruption issue when re-launching a
previously launched and saved QEMU image.
* QEMU: Limit client setup steps to run on first boot only.
* mender-qemu: increase qemu memory size to 256MiB.
* Let colibri-imx7 and vf boards be handled by automatic patching.
* Fixed issue with build due to unknown image linux-firmware-raspbian-bcm43430
* Fix mender not building if build and host architecture is the same.
* meta-mender-orangepi: Fix up u-boot
* Fix Linux kernel hanging when loaded via U-Boot/UEFI/GRUB
on vexpress-qemu*.
([MEN-1657](https://northerntech.atlassian.net/browse/MEN-1657))
* Add mender-1.3.1 and mender-artifact-2.1.2 recipes.
* Implement `IMAGE_ROOTFS_EXCLUDE_PATH` support. It works the
following way: It contains a space separated list of directories,
relative to the rootfs root (no beginning slash), and any directory
specified will be omitted from the rootfs. If the directory ends in a
slash, only the contents will be omitted, not the directory itself
(useful for mount points). One can then set
`do_image_<imagetype>[respect_exclude_path] = "1"` for certain image
builders to prevent the exclusion and then add them back as separate
partitions there.
* Support for `MENDER_DATA_PART_DIR` has been removed. Use
recipe files to add files directly to the `/data` directory instead.
* mender: Create bmap files.
* tests: Filter out the data partition as the latest build artifact.
* example-state-scripts: Explicitly return 0 from scripts.
* uboot_auto_patch: Simplify definition placement at the expense of beauty.
The resulting patch is uglier because the definitions go into a cross
platform section which is not appropriate for upstream submission. But
it does fix the case where unwanted ifdefs were "hiding" the added
definitions.
* rpi_0_w: Setup Mender required defconfigs
* Implement GRUB and x86-64 support.
([MEN-1430](https://northerntech.atlassian.net/browse/MEN-1430), [MEN-1432](https://northerntech.atlassian.net/browse/MEN-1432), [MEN-1433](https://northerntech.atlassian.net/browse/MEN-1433), [MEN-1434](https://northerntech.atlassian.net/browse/MEN-1434), [MEN-1435](https://northerntech.atlassian.net/browse/MEN-1435), [MEN-1436](https://northerntech.atlassian.net/browse/MEN-1436))
* Implement qemux86-64 machine target.
([MEN-1430](https://northerntech.atlassian.net/browse/MEN-1430), [MEN-1432](https://northerntech.atlassian.net/browse/MEN-1432), [MEN-1433](https://northerntech.atlassian.net/browse/MEN-1433), [MEN-1434](https://northerntech.atlassian.net/browse/MEN-1434), [MEN-1435](https://northerntech.atlassian.net/browse/MEN-1435), [MEN-1436](https://northerntech.atlassian.net/browse/MEN-1436))
* mender: Conditionally add /uboot mount only for SDCards.
* Increased the demo mender-retry-polling interval
([MEN-1006](https://northerntech.atlassian.net/browse/MEN-1006))
* meta-mender-toradex-nxp: Adapt colibri-imx7-mender to U-Boot autopatching
* Fix 'depends upon non-existent task' error in U-Boot recipes without auto patching.
* Use timedatectl, if available, to determine with time is synchronized.
* mender upgraded to 1.4.0.
* mender-artifact upgraded to 2.2.0.
* mender-qemu: More robust detection of MACHINE setting.
* beaglebone: Rename to beaglebone-yocto.
* Add mtdimg image type.
The mtdimg type is an image type meant to be flashed to the entire
Flash device, unlike the ubimg, which should only be flashed to the
ubi area of the mtd device. Either one can be used depending on need.
vexpress-nor image, used in QEMU, was also changed to take advantage
of the new mtdimg image.
([MEN-1597](https://northerntech.atlassian.net/browse/MEN-1597))
* Add LAYERSERIES_COMPAT settings to all Mender layers.
* Replace `MENDER_PARTITION_ALIGNMENT_KB` with
`MENDER_PARTITION_ALIGNMENT`, which is in bytes.
* Rename `MENDER_STORAGE_RESERVED_RAW_SPACE` to
`MENDER_RESERVED_SPACE_BOOTLOADER_DATA`, to better reflect what it is
used for.
* Enable wifi in the raspberry-pi demo image by default.
([MEN-1804](https://northerntech.atlassian.net/browse/MEN-1804))
* mender: Only create vfat boot partition if size is non-zero
* meta-mender-toradex-nxp: increase layer priority to 91
* Fix creating ubifs image.
* tests: Respect user set SSTATE_DIR and DL_DIR variables.
* Make sure auto provided fw-utils use virtual/bootloader setting if present.
* QEMU: Raise systemd service timeout so that it boots properly on slow hosts.
* Fix fstab sometimes not containing boot partition entry.
* Fix build error if `IMAGE_FSTYPES` contains the same entry more than once.
* Implement x86 BIOS support together with GRUB.
It can be enabled by inheriting the `mender-full-bios` class, or by
enabling the `mender-grub` and `mender-bios` features using
`MENDER_FEATURES_ENABLE`.
([MEN-1845](https://northerntech.atlassian.net/browse/MEN-1845))
* Client container init scripts are modified to accept MAC address for qemu through env var, `RANDOM_MAC`.
* added layer dependency on mender layer
* uboot_auto_configure: Fail immediately if a define cannot be added.
Better than failing later at runtime, where the problem is much harder
to debug.
* Warn on unused MENDER_.* variables
([MEN-1603](https://northerntech.atlassian.net/browse/MEN-1603))
* uboot_auto_patch: Switch kernel address from `kernel_addr_r` to `loadaddr`.
* Remove unused IMAGE_UENV_TXT_FILE variable.
* Add U-Boot auto patching support for Flash based devices.
The autopatcher will use UBI as storage medium for both the
filesystems and the U-Boot environment. Mender requires a minimum of
configuration: the `MENDER_MTDIDS` needs to be set for the board, and
will normally go in the `conf/machine/<MACHINE>.conf` file for the
board in question. See documentation for variables `MENDER_MTDIDS`,
`MENDER_IS_IN_MTDID` and `MENDER_MTDPARTS` for more information.
([MEN-1597](https://northerntech.atlassian.net/browse/MEN-1597))
* Partition alignment (`MENDER_PARTITION_ALIGNMENT`) on Flash
devices using UBI is now aligned to the UBI LEB size, which in general
is not a multiple of KiB.
([MEN-1597](https://northerntech.atlassian.net/browse/MEN-1597))
* Add Mender 1.4.1 recipe.
* Clear IMAGE_NAME_SUFFIX for all image types.
* Fix "No rule to make target 'envtools'" error in some U-Boot builds.
* Pregenerate SSH keys for all QEMU images.
* Since the "beaglebone" machine name has changed in upstream
to "beaglebone-yocto", add "beaglebone" to the
`MENDER_DEVICE_TYPES_COMPATIBLE` default, so that older devices can
upgrade even if they have the old device type.
* mender: Copy data partition images to the deploy dir.
* mender: Append to fstab rather than replacing it.
* Fix failed uboot.env install when mender-uboot feature is disabled.
* tests: Also check ARTIFACTIMG_FSTYPE for compatible images.
* uboot_auto_patch: Update to support U-Boot v2018.05.
* uboot_auto_patch: Add support for new Kconfig based
defines.
* mender-uboot: Add MENDER_UBOOT_PRE_SETUP_COMMANDS config point.
* Add Mender 1.5.0 Beta recipe.
* Add mender-1.4.0b1 and mender-artifact-2.2.0b1 recipes.
* Add 'dataimg' as an image type.
It contains the data partition filesystem which is normally part of
the complete partitioned image. To enable it, add `dataimg` to
`IMAGE_FSTYPES`.
([MEN-1879](https://northerntech.atlassian.net/browse/MEN-1879))
* mender: Use only the basename to load DTBs.
* Add Mender 1.5.0 recipe.
* Document SDIMG_ROOTFS_TYPE settings for Raspberry Pi.
* Change rootfs size calculation so it takes alignment into account.
This should fix a few corner cases, where the filesystems may all fit
in terms of bytes, but still would not actually fit because of
partition alignment.
* Added new state script to wait for time sync to complete.
* Drop creation of `authtentoken` file, which is unneeded now.
* Added basic support for orangepi boards
* mender: Cleanup IMAGE_FSTYPES.
* uboot_auto_configure: Handle tabs in defines correctly.

## meta-mender rocko-v2018.07

_Released 07.10.2018_

#### meta-mender (rocko-v2018.07)
* Clear IMAGE_NAME_SUFFIX for all image types.
* Use timedatectl, if available, to determine with time is synchronized.
* Change rootfs size calculation so it takes alignment into account.
This should fix a few corner cases, where the filesystems may all fit
in terms of bytes, but still would not actually fit because of
partition alignment.
Backported to Morty. MENDER_PARTITION_ALIGNMENT_KB instead
of MENDER_PARTITION_ALIGNMENT.
* Fix Linux kernel hanging when loaded via U-Boot/UEFI/GRUB
on vexpress-qemu*.
([MEN-1657](https://northerntech.atlassian.net/browse/MEN-1657))
* Fix occasional inode corruption issue when re-launching a
previously launched and saved QEMU image.
* QEMU: Limit client setup steps to run on first boot only.
* tests: Filter out the data partition as the latest build artifact.
* Licence checksum updated in mender-artifact
* Fixed issue with build due to unknown image linux-firmware-raspbian-bcm43430
* tests: Respect user set SSTATE_DIR and DL_DIR variables.
* Warn when mender.conf settings conflict with Bitbake variables.
* example-state-scripts: Explicitly return 0 from scripts.
* Client container init scripts are modified to accept MAC address for qemu through env var, `RANDOM_MAC`.
* tests: Also check ARTIFACTIMG_FSTYPE for compatible images.
* meta-mender-core: Clean spaces out of UBOOT_MACHINE.

## meta-mender rocko-v2018.06

_Released 06.05.2018_

#### meta-mender rocko-v2018.06
* Add Mender 1.5.0 recipe.
* Add Mender 1.4.1 recipe.
* Enable wifi in the raspberry-pi demo image by default.
([MEN-1804](https://northerntech.atlassian.net/browse/MEN-1804))

## meta-mender rocko-v2018.05

_Released 05.09.2018_

### Changelogs

#### meta-mender (rocko-v2018.05)
* mender: Copy data partition images to the deploy dir.
* Fix mender not building if build and host architecture is the same.
* Increased the demo mender-retry-polling interval
([MEN-1006](https://northerntech.atlassian.net/browse/MEN-1006))
* Fix failed uboot.env install when mender-uboot feature is disabled.
* Implement GRUB and x86-64 support.
([MEN-1430](https://northerntech.atlassian.net/browse/MEN-1430), [MEN-1432](https://northerntech.atlassian.net/browse/MEN-1432), [MEN-1433](https://northerntech.atlassian.net/browse/MEN-1433), [MEN-1434](https://northerntech.atlassian.net/browse/MEN-1434), [MEN-1435](https://northerntech.atlassian.net/browse/MEN-1435), [MEN-1436](https://northerntech.atlassian.net/browse/MEN-1436))
* Implement qemux86-64 machine target.
([MEN-1430](https://northerntech.atlassian.net/browse/MEN-1430), [MEN-1432](https://northerntech.atlassian.net/browse/MEN-1432), [MEN-1433](https://northerntech.atlassian.net/browse/MEN-1433), [MEN-1434](https://northerntech.atlassian.net/browse/MEN-1434), [MEN-1435](https://northerntech.atlassian.net/browse/MEN-1435), [MEN-1436](https://northerntech.atlassian.net/browse/MEN-1436))
* Make sure auto provided fw-utils use virtual/bootloader setting if present.
* Add Mender 1.5.0 Beta recipe.
* mender: Use only the basename to load DTBs.
* mender: Conditionally add /uboot mount only for SDCards.
* Make sure that new-style "enp" network devices get DHCP address in demo.
* mender: Allow for forcing a specific KERNEL_IMAGETYPE.
* Remove unused IMAGE_UENV_TXT_FILE variable.

## meta-mender rocko-v2018.03

_Released 03.19.2018_

#### meta-mender rocko-v2018.03
* mender upgraded to 1.4.0.
* mender-artifact upgraded to 2.2.0.
* Document SDIMG_ROOTFS_TYPE settings for Raspberry Pi.
* Fix creating ubifs image.
* mender-qemu: increase qemu memory size to 256MiB.
* meta-mender-toradex-nxp: increase layer priority to 91

## meta-mender rocko-v2018.02

_Released 02.02.2018_

#### meta-mender rocko-v2018.02
* mender: Append to fstab rather than replacing it.
* Add mender-1.4.0b1 and mender-artifact-2.2.0b1 recipes.
* Fix 'depends upon non-existent task' error in U-Boot recipes without auto patching.
* Add mender-1.3.1 and mender-artifact-2.1.2 recipes.
* QEMU: Raise systemd service timeout so that it boots properly on slow hosts.
* Added new state script to wait for time sync to complete.
* Fix "No rule to make target 'envtools'" error in some U-Boot builds.
* Pregenerate SSH keys for all QEMU images.

## meta-mender rocko-v2018.01

_Released 01.04.2018_

* meta-mender-core: Allow dtbos in KERNEL_DEVICETREE
## meta-mender rocko-v2017.12

_Released 12.20.2017_

* mender-artifact: Fix build failure due to poky golang source directory changes.
* Catch up with latest poky U-Boot v2017.05.
* Fix build failure after poky switched to checking out Go
sources under the full GOPATH.
* rpi-u-boot-scr: Switch to boot.cmd.in style recipe.
* sato: Set NETWORK_MANAGER to systemd.
* Update example-state-scripts to use standard logging.
* Add Mender 1.3.0b1 recipe.
* Work around bug in libpseudo regarding file owners on data partition.
* Add machine configuration for Mender on colibri-imx7
* u-boot: update mender_boot_part_name when mender_boot_part changes
* Remove meta-mender-beaglebone layer. This layer is not
needed anymore for compiling for Beaglebone and should be removed from
all build configurations.
([MEN-1387](https://northerntech.atlassian.net/browse/MEN-1387))
* Add example recipe to show how to deploy files into Mender persistent data partition
* mender-artifact: Fix build failure due to poky golang support changes.
* meta-mender-raspberrypi: increase layer priority to 10
* Fix bug where MENDER_DEVICE_TYPES_COMPATIBLE would only accept one entry.
* mender: Adjust patches for U-Boot v2017.09
* mender: Use GO environment variable to launch the compiler
* Implement heuristic automatic patching of U-Boot.
It can be turned on and off by setting `MENDER_UBOOT_AUTO_CONFIGURE`
to `1` and `0`, respectively, in a `u-boot.bbappend` file. It is on by
default. If the automatic patching is unsuccessful, there is a special
bitbake target that can be used to extract the generated patch and use
it as a basis for a manual patch. It can be invoked with `bitbake -c
save_mender_auto_configured_patch <u-boot-recipe>`, where
`<u-boot-recipe>` is either `u-boot` or the fork of U-Boot that your
board uses. ([MEN-1387](https://northerntech.atlassian.net/browse/MEN-1387))
* Bump mender and mender-artifact to version 1.1.0 and 2.0.0, respectively.
* Remove recipes for Mender 1.0.x series.
* Add Mender 1.3.0 build recipe.

## meta-mender pyro-v2017.12

_Released 12.20.2017_

* Fix bug where MENDER_DEVICE_TYPES_COMPATIBLE would only accept one entry.
* Add Mender 1.3.0 build recipe.
* u-boot: update mender_boot_part_name when mender_boot_part changes
* Update example-state-scripts to use standard logging.
* meta-mender-raspberrypi: increase layer priority to 10
* sato: Set NETWORK_MANAGER to systemd.
* Add machine configuration for Mender on colibri-imx7

## meta-mender pyro-v2017.11

_Released 11.14.2017_

* Add Mender 1.3.0b1 recipe.
* Upstream image has grown significantly, increase to 608MB sdimg.
The noticeably non-round number is to make sure the calculated rootfs
size is divisible by the partition alignment.
