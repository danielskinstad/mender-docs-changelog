---
title: Mender Gateway
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---
## 2.1.0 - 2026-06-09


### Bug fixes


- *(deps)* Update golang-dependencies
 ([bad72df](https://github.com/mendersoftware/mender-gateway/commit/bad72df9d473310022ee29306dde23d22b93d165))  by @mender-test-bot



- Set the correct `Content-Length` when modifying the inventory payload
([MEN-7738](https://northerntech.atlassian.net/browse/MEN-7738)) ([4e555bf](https://github.com/mendersoftware/mender-gateway/commit/4e555bf13d36de43c780d36665691af23a4ae196))  by @tranchitella





- Whitelist cloudflarestorage in example conf
([MEN-8619](https://northerntech.atlassian.net/browse/MEN-8619)) ([1736267](https://github.com/mendersoftware/mender-gateway/commit/1736267a4c07932193cb403e3dbced116e34eda7))  by @danielskinstad






  This will fix the onboarding tutorial for mender-gateway which currently
  results in the following error:
  `c271964d41749feb10da762816c952ee.r2.cloudflarestorage.com returned
  by Mender server is not whitelisted`
- Update Golang version for pre-built binaries to Go 1.25
([SEC-1715](https://northerntech.atlassian.net/browse/SEC-1715)) ([f91a308](https://github.com/mendersoftware/mender-gateway/commit/f91a308c93a21f9e2230f23be47bde498c43dd7f)) 





  Pre-built binaries were still using Go 1.17, which was long ago EOL.
  
  This issue affects pre-built binaries distributed for Yocto integration;
  Debian packages and Container images were not affected.
- Check if DeviceSystem is enabled in inventory script
([MEN-8937](https://northerntech.atlassian.net/browse/MEN-8937)) ([9b2548f](https://github.com/mendersoftware/mender-gateway/commit/9b2548f3b9a03a8a31ce5ebc06f807f135174325))  by @danielskinstad





  Fixed an issue where `mender-inventory-mender-gateway` would send
  `mender_gateway_system_id=<SystemID>` even if DeviceSystem was disabled.
  Fixed by adding an explicit check to the inventory script.
- Make proxy requests to "Auto-auth"" and "Pre-auth" APIs
([MEN-9042](https://northerntech.atlassian.net/browse/MEN-9042)) ([937dc6a](https://github.com/mendersoftware/mender-gateway/commit/937dc6aa251873ed0a9d2a233a35f17e47fdc1a6))  by @alfrunes





  The requests to the management APIs on behalf of devices does not add
  the proxy headers which is required for resolving the correct source IP
  when a request is done on behalf of a device.
  This commit changes the client interface to use a ReverseProxy instance
  to make the API requests to the backend.
- Prevent bursting login requests on token expiry
([MEN-9043](https://northerntech.atlassian.net/browse/MEN-9043)) ([67723de](https://github.com/mendersoftware/mender-gateway/commit/67723def88e2449a082a0c18d93dacc65d5b711d))  by @alfrunes





  Protecting the JWT token with a RW mutex to prevent concurrent login
  requests when the token expires.
- Do not mangle HTTP responses on panic
([MEN-9044](https://northerntech.atlassian.net/browse/MEN-9044)) ([cb4898b](https://github.com/mendersoftware/mender-gateway/commit/cb4898b7d900c15aced189ae715497b7be19ce11))  by @alfrunes



- Fixed error on service restart
([MEN-8931](https://northerntech.atlassian.net/browse/MEN-8931)) ([724aaca](https://github.com/mendersoftware/mender-gateway/commit/724aaca922799a246233faaffd7b2487043cd535))  by @rewanrashid-boop




  Fixed an error where any interrupt or restart of mender-gateway.service would result in fatal exit
  Ticket: MEN-8931




### Features


- Respect HTTP_PROXY, HTTPS_PROXY and HTTPS_PROXY environment variables
([ME-637](https://northerntech.atlassian.net/browse/ME-637)) ([c5865a3](https://github.com/mendersoftware/mender-gateway/commit/c5865a3dd2901d248f2a9bc6ed50a127ce10c6d4))  by @kjaskiewiczz





  Instead of creating empty transport object, clone the default one and
  customize fields that we need to. With default transport, according to
  docs, we will have this behavior:
  > It establishes network connections as needed
  and caches them for reuse by subsequent calls.
  It uses HTTP proxies
  as directed by the environment variables HTTP_PROXY, HTTPS_PROXY
  and NO_PROXY (or the lowercase versions thereof).
  
  It will also default to Go-http-client/2.0 instead of Go-http-client/1.1
  becuase of `ForceAttemptHTTP2: true` in the default transport.




### Security


- Bump github.com/fsnotify/fsnotify
 ([f64bd12](https://github.com/mendersoftware/mender-gateway/commit/f64bd126ffb6c94c3c63f7490ee5752b1c94eeb9))  by @dependabot[bot]




  Bumps the golang-dependencies group with 1 update: [github.com/fsnotify/fsnotify](https://github.com/fsnotify/fsnotify).
  
  
  Updates `github.com/fsnotify/fsnotify` from 1.7.0 to 1.8.0
  - [Release notes](https://github.com/fsnotify/fsnotify/releases)
  - [Changelog](https://github.com/fsnotify/fsnotify/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/fsnotify/fsnotify/compare/v1.7.0...v1.8.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/fsnotify/fsnotify
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: golang-dependencies
  ...
- Bump the golang-dependencies group with 2 updates
 ([9d63732](https://github.com/mendersoftware/mender-gateway/commit/9d6373243c8d5d73b330c98a61b243dcf791f3db))  by @dependabot[bot]




  Bumps the golang-dependencies group with 2 updates: [golang.org/x/sync](https://github.com/golang/sync) and [golang.org/x/sys](https://github.com/golang/sys).
  
  
  Updates `golang.org/x/sync` from 0.8.0 to 0.9.0
  - [Commits](https://github.com/golang/sync/compare/v0.8.0...v0.9.0)
  
  Updates `golang.org/x/sys` from 0.26.0 to 0.27.0
  - [Commits](https://github.com/golang/sys/compare/v0.26.0...v0.27.0)
  
  ---
  updated-dependencies:
  - dependency-name: golang.org/x/sync
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: golang-dependencies
  ...
- Bump github.com/stretchr/testify in the golang-dependencies group
 ([cf4f5ab](https://github.com/mendersoftware/mender-gateway/commit/cf4f5abf64880ffb660850c61386be0be4effc9e))  by @dependabot[bot]




  Bumps the golang-dependencies group with 1 update: [github.com/stretchr/testify](https://github.com/stretchr/testify).
  
  
  Updates `github.com/stretchr/testify` from 1.9.0 to 1.10.0
  - [Release notes](https://github.com/stretchr/testify/releases)
  - [Commits](https://github.com/stretchr/testify/compare/v1.9.0...v1.10.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/stretchr/testify
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: golang-dependencies
  ...
- Bump mender-server
 ([cca6780](https://github.com/mendersoftware/mender-gateway/commit/cca67809a98633e7d75bb0ba82aa335057bcf120))  by @danielskinstad


- Bump test/integration/mender_server
([QA-1003](https://northerntech.atlassian.net/browse/QA-1003)) ([0cb632a](https://github.com/mendersoftware/mender-gateway/commit/0cb632a1f16d3b51f2131bcbb568d4a7381c4773))  by @danielskinstad





  - tests/integration/mender_server 2df3643c91e75ea3c4ed5e5af05a83e2ede363cf => 16dd4b76b3de1e7e980986cb397a7290b50619ff
- Bump golang image in Dockerfile
([QA-1003](https://northerntech.atlassian.net/browse/QA-1003)) ([e0d2e5a](https://github.com/mendersoftware/mender-gateway/commit/e0d2e5aba4aacb51be790f1190e8919c93732246))  by @danielskinstad





  Bump golang:1.23.4 to 1.23.9






## mender-gateway 2.0.0

_Released 12.18.2024_

### Changelogs

#### mender-gateway (2.0.0)

New changes in mender-gateway since 1.2.1:

##### Bug Fixes

* allow different keys for auth request and client certificate.
  ([MEN-7046](https://northerntech.atlassian.net/browse/MEN-7046))
* fix: added public CAs to the Docker container build
  ([MC-7281](https://northerntech.atlassian.net/browse/MC-7281))
* Process `--log-level` before loading configuration

##### Features

* mTLS: cache and protect with force the preauth requests.
  ([MEN-6928](https://northerntech.atlassian.net/browse/MEN-6928))
* Configuration for adding trusted certificate authority

  The new configuration `UpstreamServer.CACertificate` (env:
  upstream_server_ca_certificate` specifies a path to a file containing a
  PEM-encoded certificate chain of trusted CAs.
  ([MEN-6174](https://northerntech.atlassian.net/browse/MEN-6174))
* Load config from environment variables

  Exposes the following environment variables to override the config
  loaded from the file:
   - ARTIFACTS_PROXY_CACHE_LINK_EXPIRE_DURATION
   - ARTIFACTS_PROXY_CACHE_ENABLED
   - ARTIFACTS_PROXY_CACHE_PATH
   - ARTIFACTS_PROXY_CACHE_SECRET
   - ARTIFACTS_PROXY_DOMAIN_WHITELIST
   - ARTIFACTS_PROXY_ENABLED
   - ARTIFACTS_PROXY_GATEWAY_URL
   - DEVICE_SYSTEM_ENABLED
   - DEVICE_SYSTEM_ID
   - HTTPS_ENABLED
   - HTTPS_LISTEN
   - HTTPS_MINIMUM_TLS_VERSION
   - HTTPS_SERVER_CERTIFICATE
   - HTTPS_SERVER_KEY
   - HTTP_ENABLED
   - HTTP_LISTEN
   - MTLS_BLACKLIST_PATH
   - MTLS_CA_CERTIFICATE
   - MTLS_ENABLED
   - MTLS_ENABLE_CACHE
   - MTLS_MENDER_PASSWORD
   - MTLS_MENDER_USERNAME
   - UPSTREAM_SERVER_CA_CERTIFICATE
   - UPSTREAM_SERVER_INSECURE_SKIP_VERIFY
   - UPSTREAM_SERVER_URL

  ,
  ([MEN-7051](https://northerntech.atlassian.net/browse/MEN-7051), [MEN-7182](https://northerntech.atlassian.net/browse/MEN-7182))
* add support for running both HTTP and HTTPS servers at the same time
  ([MEN-7193](https://northerntech.atlassian.net/browse/MEN-7193))
* New configuration `MTLS_INSECURE_SKIP_CLIENT_EXPIRE_AFTER`

  This configuration skips checking the "Not After" attribute in client
  certificate in mutual TLS mode. Enabling this configuration is
  discouraged and should not be used in production environments.
  ([MEN-7363](https://northerntech.atlassian.net/browse/MEN-7363))

##### Other

* Bump golang Docker version to 1.22.1-alpine3.19
* use AutoAccept endpoint in mtls mode
  ([MEN-7194](https://northerntech.atlassian.net/browse/MEN-7194))


## mender-gateway 1.2.1

_Released 12.02.2024_

### Changelogs

#### mender-gateway (1.2.1)

New changes in mender-gateway since 1.2.0:

##### Bug Fixes

* set the correct `Content-Length` when modifying the inventory payload
  ([MEN-7738](https://northerntech.atlassian.net/browse/MEN-7738))


## mender-gateway 1.2.0

_Released 12.28.2023_

### Changelogs

#### mender-gateway (1.2.0)

New changes in mender-gateway since 1.1.0:

##### Features

* build and test using the latest version of golang
  ([QA-614](https://northerntech.atlassian.net/browse/QA-614))


## mender-gateway 1.1.0

_Released 02.20.2023_

### Changelogs

#### mender-gateway (1.1.0)

New changes in mender-gateway since 1.0.1:

##### Features

* New configuration DefaultInventory setting common device attributes

  The 'DefaultInventory' attribute in the root of the configuration object
  sets attributes that will be appended to what the device submits to the
  server. The attributes will not overwrite any value that the device may
  submit for the given attribute name.
  ([MEN-5853](https://northerntech.atlassian.net/browse/MEN-5853))
* New configuration option HTTPS.MinimumTLSVersion

  The new configuration sets the minimum TLS version accepted by the
  mender-gateway server.
  ([MEN-6090](https://northerntech.atlassian.net/browse/MEN-6090))
* Add `mender_gateway_system_id` to the mender-gateway
  inventory script installed along the software. This parameter is
  extracted from the `SystemID` filed in the configuration file when
  present. When not present, the inventory key will not be outputted.
  ([MEN-6287](https://northerntech.atlassian.net/browse/MEN-6287))


## mender-gateway 1.0.1

_Released 09.25.2022_

### Changelogs

#### mender-gateway (1.0.1)

New changes in mender-gateway since 1.0.0:

##### Other

* Licenses are now available in the package, instead of only
  online. ([MEN-5517](https://northerntech.atlassian.net/browse/MEN-5517))


## mender-gateway 1.0.0

_Released 06.14.2022_

### Changelogs

#### mender-gateway (1.0.0)

* First release of mender-gateway
