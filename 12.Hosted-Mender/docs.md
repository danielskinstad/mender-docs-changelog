---
title: Hosted Mender
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## 4.2.0-saas.15 - 2026-08-26


### New features

- *(inventory)* Process orchestrator inventory attributes ([MEN-9632](https://northerntech.atlassian.net/browse/MEN-9632))
- *(workflows)* Add user invitation workflow
- *(tenantadm)* Set limit of test devices with create-org cli ([MEN-9988](https://northerntech.atlassian.net/browse/MEN-9988))
- *(deviceauth)* Test devices support for GET limits ([MEN-9985](https://northerntech.atlassian.net/browse/MEN-9985))
- *(useradm)* Add RBAC rules for accessing alpha versioned endpoints
- *(inventory)* Add endpoint for fetching system device components ([MEN-9794](https://northerntech.atlassian.net/browse/MEN-9794))
- *(useradm)* Remove ability for users to change any other user's email ([MEN-10010](https://northerntech.atlassian.net/browse/MEN-10010))
- *(gui)* Implemented a new email change flow ([MEN-9251](https://northerntech.atlassian.net/browse/MEN-9251))
- *(useradm)* Send the invitation with the POST /users v2 ([MEN-9741](https://northerntech.atlassian.net/browse/MEN-9741))
- *(gui)* Remove email edit from user details view ([MEN-9699](https://northerntech.atlassian.net/browse/MEN-9699))
- *(gui)* Show verification, 2FA, and auth type columns in user list ([MEN-9804](https://northerntech.atlassian.net/browse/MEN-9804))
- *(gui)* Added system device tab to device details ([MEN-9633](https://northerntech.atlassian.net/browse/MEN-9633))
- *(admin-panel)* Add notice broadcast endpoints and workflows client
- *(admin-panel)* Add tenant endpoints with fan-out detail aggregation ([MEN-9760](https://northerntech.atlassian.net/browse/MEN-9760))
- *(admin-panel)* Add user endpoints ([MEN-9760](https://northerntech.atlassian.net/browse/MEN-9760))
- *(admin-panel)* Add notice broadcast endpoints
- *(iot-manager)* Device-status-changed webhook event contains auth set
  Only decommission events does not carry auth sets.

- *(admin-panel)* Add generated api client based on admin-panel specs ([MEN-9765](https://northerntech.atlassian.net/browse/MEN-9765))
- *(admin-panel)* Add dashboard with plan breakdown and trial count ([MEN-9768](https://northerntech.atlassian.net/browse/MEN-9768))
- *(admin-panel)* Add tenant management frontend ([MEN-9766](https://northerntech.atlassian.net/browse/MEN-9766))
- *(admin-panel)* Add user management capabilities ([MEN-9767](https://northerntech.atlassian.net/browse/MEN-9767))
- *(admin-panel)* Add notice broadcast functionality to frontend
- *(admin-panel)* Add nginx Dockerfile for the admin panel frontend ([MEN-9769](https://northerntech.atlassian.net/browse/MEN-9769))
- *(deviceauth)* Add custom rate limiter for assigning test device flag ([MEN-10033](https://northerntech.atlassian.net/browse/MEN-10033))
- *(tenantadm)* Implement endpoint for fetching own tenant token ([MEN-9579](https://northerntech.atlassian.net/browse/MEN-9579))
- *(deployments)* Extend final uniform phase for dynamic deployments ([MEN-9972](https://northerntech.atlassian.net/browse/MEN-9972))
- *(deviceauth)* Add feature flag to restore legacy provision behavior ([MEN-10027](https://northerntech.atlassian.net/browse/MEN-10027))
- *(inventory)* Return the identities with the get devices/:id endpoint ([MEN-9974](https://northerntech.atlassian.net/browse/MEN-9974))
- *(inventory)* Search inventory by identity alpha endpoint ([MEN-9976](https://northerntech.atlassian.net/browse/MEN-9976))
- *(useradm)* Add RBAC permission for search by identity endpoint ([MEN-9976](https://northerntech.atlassian.net/browse/MEN-9976))
- *(deployments)* Return phases and set statuses for uniform deployments ([MEN-9971](https://northerntech.atlassian.net/browse/MEN-9971))

### Improvements

- *(inventory)* Remove extra device read from upsert attributes ([MEN-9632](https://northerntech.atlassian.net/browse/MEN-9632))
- *(inventory)* Lower cyclomatic complexity of ReplaceAttributes ([MEN-9632](https://northerntech.atlassian.net/browse/MEN-9632))
- *(deviceauth)* Refactor mehtod for deleting authentication set ([MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880))
- *(deviceauth)* Reduce cyclomatic complexity of VerifyToken method
- *(generate-delta-worker)* Propagate timeout through context
- *(generate-delta-worker)* Refactor root command initialization
- *(gui)* Allowed email editing only on os & keep it tied to verification on (non-)enterprise
- *(gui)* Let user modifications handle their own dialog visibility
- *(gui)* Let user deletion confirmation rely on common confirmation dialog
- *(gui)* Let user role changes get reflected in the form they happen in right away
- *(gui)* Aligned user details w/ updated design
- *(inventory)* Lower cyclomatic complexity of ReplaceAttributes
- Add openapi spec and go backend scaffold for admin-panel ([MEN-9759](https://northerntech.atlassian.net/browse/MEN-9759))
- *(admin-panel)* Name the notice routes like the rest
- *(deviceauth)* Split out logic for aggregating device status
- *(deviceauth)* Push updateDeviceStatus.GetDeviceById to caller
- *(deviceauth)* Centralize handlers for setting authset status
- *(deviceauth)* Split out updateAuthSetStatus from setAuthSetStatus
- *(deviceauth)* Unify all device status update paths
- *(deviceauth)* Consolidate auth set update: preauth -> accepted
- *(deviceauth)* Move tier handling to updateDeviceStatus
- *(deviceauth)* Use model.Tier everywhere
- *(deviceauth)* Fetch the auth set only if it already exists
- *(deviceauth)* Do not aggregate device status if it will not change
- *(admin-panel)* Add standalone React admin panel frontend ([MEN-9764](https://northerntech.atlassian.net/browse/MEN-9764))
- Replace old get tenant info endpoint with new endpoints
- *(deployments)* Move software RBAC tests to rbac_test.go
- *(gui)* Let deployment log consumers rely on the shared log dialog
- *(gui)* Aligned controlled text input further w/ rhf api
- *(gui)* Converted artifact generation to rhf ([MEN-9318](https://northerntech.atlassian.net/browse/MEN-9318))

### Bug fixes

- *(deviceauth)* Remove device token from cache only when deleting accepted auth set ([MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880))
- *(generate-delta-worker)* Fifo deadlock if download times out
- *(generate-delta-worker)* Asynchronous errors not caught when downloading
- *(deviceauth)* Delete preauthorize device only if there are no auth sets ([MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880))
- *(deviceauth)* Delete orphan auth sets when veryfing token ([MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880))
- *(deviceauth)* Fix error handling when updating device status ([MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880))
- *(useradm)* Extend userauth traefik rule with "users/me/email-change/complete"
- *(deviceconnect)* Restore read deadline to reap dead device connections ([MEN-9934](https://northerntech.atlassian.net/browse/MEN-9934))
- *(inventory)* Return error when failing to find a device
- *(generate-delta-worker)* Always reap mender-binary-delta-generator on error ([MEN-10001](https://northerntech.atlassian.net/browse/MEN-10001))
- *(generate-delta-worker)* Remove hard-coded 15m timeout to upload artifact
- *(deployments)* Stop generating delta artifacts on already installed images ([MEN-10002](https://northerntech.atlassian.net/browse/MEN-10002))
- *(gui)* Ensure correct global retry count is displayed in deployment options
- *(gui)* Let auditlog filters stay in line if there's something telling them to stretch vertically
- *(gui)* Let deployment creation reflect inability to generate delta deployments for trial users ([MEN-9586](https://northerntech.atlassian.net/browse/MEN-9586))
- *(workflows)* Add 5 second delay on retries for provision device jobs
- *(deviceauth)* Improve device provisioning workflow handling ([MEN-9993](https://northerntech.atlassian.net/browse/MEN-9993))
- *(gui)* Don't require email verification to add users on open source builds
- *(gui)* Email verification is required for all multitenant installations
- *(gui)* Require password and gate reset-link checkbox on os
- *(gui)* Check if global setting changed before submitting ([MEN-9995](https://northerntech.atlassian.net/browse/MEN-9995))
- *(create-artifact-worker)* Pin mender-orchestrator-manifest-gen to a release tag ([QA-345](https://northerntech.atlassian.net/browse/QA-345))
- *(deviceconnect)* Allow messages larger than bandlimit rate ([MEN-10014](https://northerntech.atlassian.net/browse/MEN-10014))
  If a message is larger than the per second rate limit for a device, all
  sessions to that device will forcefully terminate. This commit allows
  such messages, by making the peer wait for more than one second until
  the whole message is accepted.

- *(deviceauth)* Check test device usage when accepting device as trial ([MEN-9352](https://northerntech.atlassian.net/browse/MEN-9352))
  When accepting a new device as trial, check usage limits are within
  boundaries before setting the test device flag. If limit is exhausted,
  do not assign the test flag but accept the device.

- *(deviceauth)* Test device status automation for trial accounts ([MEN-10032](https://northerntech.atlassian.net/browse/MEN-10032))
  When a device transitions from accepted to any other status, the trial
  flag is removed from the device for trial accounts.

- *(tenantadm)* Set binary deltas to false on signup for trials ([MEN-9499](https://northerntech.atlassian.net/browse/MEN-9499))
- *(deviceauth)* Count no tier as standard tier when processing preauth ([MEN-9598](https://northerntech.atlassian.net/browse/MEN-9598))
- *(workflows)* Update verify email template to context neutral message ([MEN-9183](https://northerntech.atlassian.net/browse/MEN-9183))
- *(deviceauth)* Protect device status from concurrent updates ([MEN-9997](https://northerntech.atlassian.net/browse/MEN-9997))
- *(deviceauth)* Check limit only if device status transitions to accepted
- *(deviceauth)* Adjust limit check preconditions to account for tiers
- *(deviceauth)* Rejecting or resetting an accepted auth set trigger auditlog
- *(gui)* Change wrong UI status for aborted deployments ([MEN-9983](https://northerntech.atlassian.net/browse/MEN-9983))
- *(gui)* Show auditlog detail information also for device file transfers ([MEN-9316](https://northerntech.atlassian.net/browse/MEN-9316))
- *(gui)* Click on the audilog link not overtaken by row handler ([MEN-9316](https://northerntech.atlassian.net/browse/MEN-9316))
- *(deviceauth)* Ensured flag status is refreshed in cache as well on device status change
- *(deployments)* Support empty tier in incompatible tier deployment substate ([MEN-10074](https://northerntech.atlassian.net/browse/MEN-10074))
- *(deviceauth)* Use canonical tier in auth request error cache key
- *(deviceconnect)* Accesslog shows correct status and adds `wsstatus`
- *(gui)* Ensured data w/ multiple attribute values gets shown in a readable manner ([MEN-10073](https://northerntech.atlassian.net/browse/MEN-10073))

### Dependency updates

- *(deps)* Update module github.com/russellhaering/goxmldsig to v1.6.0 [security]
- *(deps)* Update dependency react-router to v8.3.0 [security]
- *(deps)* Update dependency @babel/plugin-transform-runtime to v8
- *(deps-dev)* Bump svgo from 3.3.3 to 3.3.4 in /frontend
- *(deps-dev)* Bump postcss from 8.5.15 to 8.5.23 in /frontend
- *(deps-dev)* Bump fast-uri from 3.1.2 to 3.1.4 in /frontend
- *(deps)* Bump brace-expansion and gaxios
- *(deps)* Update npm-dev-dependencies
- *(deps)* Update golang-dependencies
- *(deps)* Update npm-prod-dependencies
- *(deps-dev)* Bump fast-uri from 3.1.4 to 3.1.5 in /frontend
- *(deps)* Update npm-mui
- *(deps)* Update docker-base-images
- *(deps)* Bump google.golang.org/grpc in /backend/tests/runner
- *(deps)* Bump pillow from 12.2.0 to 12.3.0 in /backend/tests
- *(deps)* Bump github.com/sigstore/sigstore-go
- *(deps)* Bump js-yaml from 4.2.0 to 4.3.1 in /frontend
- *(deps)* Bump mermaid from 11.15.0 to 11.16.1 in /frontend
- *(deps)* Tidy test dependencies
- *(deps)* Update npm-mui to v9.12.0
- *(deps)* Update docker-compose
- *(deps)* Update ${mirror_registry:-docker.io}/stripe/stripe-cli docker tag to v1.50.5
- *(deps)* Update mongo docker tag to v8.3

### All tickets resolved in this release

| Ticket |
|---|
| [MEN-9632](https://northerntech.atlassian.net/browse/MEN-9632) |
| [MEN-9880](https://northerntech.atlassian.net/browse/MEN-9880) |
| [MEN-9988](https://northerntech.atlassian.net/browse/MEN-9988) |
| [MEN-9985](https://northerntech.atlassian.net/browse/MEN-9985) |
| [MEN-9934](https://northerntech.atlassian.net/browse/MEN-9934) |
| [MEN-9794](https://northerntech.atlassian.net/browse/MEN-9794) |
| [MEN-10001](https://northerntech.atlassian.net/browse/MEN-10001) |
| [MEN-10010](https://northerntech.atlassian.net/browse/MEN-10010) |
| [MEN-10002](https://northerntech.atlassian.net/browse/MEN-10002) |
| [MEN-9251](https://northerntech.atlassian.net/browse/MEN-9251) |
| [MEN-9586](https://northerntech.atlassian.net/browse/MEN-9586) |
| [MEN-9993](https://northerntech.atlassian.net/browse/MEN-9993) |
| [MEN-9741](https://northerntech.atlassian.net/browse/MEN-9741) |
| [MEN-9995](https://northerntech.atlassian.net/browse/MEN-9995) |
| [MEN-9699](https://northerntech.atlassian.net/browse/MEN-9699) |
| [MEN-9804](https://northerntech.atlassian.net/browse/MEN-9804) |
| [MEN-9633](https://northerntech.atlassian.net/browse/MEN-9633) |
| [QA-345](https://northerntech.atlassian.net/browse/QA-345) |
| [MEN-10014](https://northerntech.atlassian.net/browse/MEN-10014) |
| [MEN-9352](https://northerntech.atlassian.net/browse/MEN-9352) |
| [MEN-10032](https://northerntech.atlassian.net/browse/MEN-10032) |
| [MEN-9499](https://northerntech.atlassian.net/browse/MEN-9499) |
| [MEN-9598](https://northerntech.atlassian.net/browse/MEN-9598) |
| [MEN-9759](https://northerntech.atlassian.net/browse/MEN-9759) |
| [MEN-9760](https://northerntech.atlassian.net/browse/MEN-9760) |
| [MEN-9183](https://northerntech.atlassian.net/browse/MEN-9183) |
| [MEN-9997](https://northerntech.atlassian.net/browse/MEN-9997) |
| [MEN-9764](https://northerntech.atlassian.net/browse/MEN-9764) |
| [MEN-9765](https://northerntech.atlassian.net/browse/MEN-9765) |
| [MEN-9768](https://northerntech.atlassian.net/browse/MEN-9768) |
| [MEN-9766](https://northerntech.atlassian.net/browse/MEN-9766) |
| [MEN-9767](https://northerntech.atlassian.net/browse/MEN-9767) |
| [MEN-9769](https://northerntech.atlassian.net/browse/MEN-9769) |
| [MEN-10033](https://northerntech.atlassian.net/browse/MEN-10033) |
| [MEN-9579](https://northerntech.atlassian.net/browse/MEN-9579) |
| [MEN-9983](https://northerntech.atlassian.net/browse/MEN-9983) |
| [MEN-9316](https://northerntech.atlassian.net/browse/MEN-9316) |
| [MEN-9972](https://northerntech.atlassian.net/browse/MEN-9972) |
| [MEN-10027](https://northerntech.atlassian.net/browse/MEN-10027) |
| [MEN-9974](https://northerntech.atlassian.net/browse/MEN-9974) |
| [MEN-10074](https://northerntech.atlassian.net/browse/MEN-10074) |
| [MEN-9976](https://northerntech.atlassian.net/browse/MEN-9976) |
| [MEN-10073](https://northerntech.atlassian.net/browse/MEN-10073) |
| [MEN-9318](https://northerntech.atlassian.net/browse/MEN-9318) |
| [MEN-9971](https://northerntech.atlassian.net/browse/MEN-9971) |


## 4.2.0-saas.14 - 2026-07-17


### New features

- *(useradm)* Add RBAC rules for /user/me/email-change/start endpoint
- *(useradm)* Add endpoint for starting own email update request ([MEN-9708](https://northerntech.atlassian.net/browse/MEN-9708))
- *(useradm)* Add endpoint for getting pending email update request ([MEN-9712](https://northerntech.atlassian.net/browse/MEN-9712))
- *(useradm)* Add endpoint for canceling own email update request ([MEN-9711](https://northerntech.atlassian.net/browse/MEN-9711))
- *(useradm)* Add endpoint for completing own email update request ([MEN-9708](https://northerntech.atlassian.net/browse/MEN-9708))
- *(useradm)* Return pending email change request with GET users/me ([MEN-9715](https://northerntech.atlassian.net/browse/MEN-9715))
- *(gui)* Added incompatible tier substate support ([MEN-9312](https://northerntech.atlassian.net/browse/MEN-9312))
- *(gui)* Add an email change validation route ([MEN-9950](https://northerntech.atlassian.net/browse/MEN-9950))

### Bug fixes

- *(deviceconnect)* Only allow one connection per device at a time
- *(useradm)* Invalidate password reset requests on email change completion
- *(useradm)* Return only one status on bad user updates
- *(gui)* Close the device drawer when filtering for test devices
- *(deviceconnect)* Enforce tenant access scope for device connections
- *(deviceconnect)* Stream transmission control ack messages before buffering
- *(gui)* Fixed issue that crashed ungrouped distribution widget
- *(gui)* Reverts "hide pat creation and revocation for read-only users"
- *(gui)* Show / set real attempts value in global setting
- *(gui)* Show accurate attempt number per device in deployment status
- *(generate-delta-worker)* Mender-binary-delta runs inside work directory ([MEN-9992](https://northerntech.atlassian.net/browse/MEN-9992))

### Dependency updates

- *(deps)* Update module golang.org/x/net to v0.55.0 [security]
- *(deps)* Update module golang.org/x/crypto to v0.52.0 [security]
- *(deps)* Update dependency markdown to v3.8.1 [security]
- *(deps)* Update module github.com/aws/aws-sdk-go-v2/service/bedrockruntime to v1.50.4 [security]
- *(deps)* Update module go.opentelemetry.io/otel to v1.41.0 [security]
- *(deps-dev)* Bump morgan in /frontend/tests/e2e_tests
- *(deps)* Bump golang.org/x/net from 0.54.0 to 0.55.0 in /backend
- *(deps)* Bump github.com/sigstore/sigstore-go
- *(deps)* Bump golang.org/x/crypto from 0.51.0 to 0.52.0 in /backend
- *(deps)* Update dependency mendersoftware/mender-artifact to v4.4.1
- *(deps)* Update docker-base-images
- *(deps)* Update golang-dependencies
- *(deps)* Upgrade miniredis to stable v2.38.0 and gosjonq to v2.5.2
- *(deps-dev)* Bump ws from 8.20.0 to 8.21.0 in /frontend
- *(deps)* Update npm-dev-dependencies
- *(deps)* Update npm-mui to v9.9.0
- *(deps)* Downgrade mender-artifact to v0.0.0-20250724101633-c5f6563a4bcf

### All tickets resolved in this release

| Ticket |
|---|
| [MEN-9708](https://northerntech.atlassian.net/browse/MEN-9708) |
| [MEN-9712](https://northerntech.atlassian.net/browse/MEN-9712) |
| [MEN-9711](https://northerntech.atlassian.net/browse/MEN-9711) |
| [MEN-9715](https://northerntech.atlassian.net/browse/MEN-9715) |
| [MEN-9312](https://northerntech.atlassian.net/browse/MEN-9312) |
| [MEN-9950](https://northerntech.atlassian.net/browse/MEN-9950) |
| [MEN-9992](https://northerntech.atlassian.net/browse/MEN-9992) |


## 4.2.0-saas.13 - 2026-07-08


### Bug fixes


- *(deviceauth)* Skip ratelimiting on bad tokens
 ([fe92177](https://github.com/mendersoftware/mender-server-enterprise/commit/fe92177f482681e2feaea5f188ff3cdfdd46390f))  by @bahaa-ghazal



- *(gui)* Make device detail tab strip scrollable on mobile
([ME-683](https://northerntech.atlassian.net/browse/ME-683)) ([a4e12b8](https://github.com/mendersoftware/mender-server-enterprise/commit/a4e12b8c36515cdc16d9a1eb40db64a728d2d08a))  by @nickanderson





  The device-details tab strip used the default standard Tabs variant,
  which has no horizontal scrolling. Once the drawer became width-
  constrained by BaseDrawer (72d1fa0c), overflowing tabs such as
  Troubleshoot were clipped and unreachable on mobile. Make the strip
  horizontally scrollable so every tab stays reachable regardless of
  drawer width (ME-683).

- *(gui)* Fixed an issue when deploying to a dynamic group targeting a single device
([MEN-9530](https://northerntech.atlassian.net/browse/MEN-9530)) ([1c97770](https://github.com/mendersoftware/mender-server-enterprise/commit/1c97770dafd1c70bdfe25c036167d2a7fa794e6a))  by @mzedel




- *(gui)* Excluded status from device identity details as it's shown below
([MEN-7891](https://northerntech.atlassian.net/browse/MEN-7891)) ([837631d](https://github.com/mendersoftware/mender-server-enterprise/commit/837631d7cac96163b07a9ef996b4d048901df99f))  by @mzedel




- *(gui)* Let empty role permission selection close the selection dropdown
([MEN-9276](https://northerntech.atlassian.net/browse/MEN-9276)) ([4697bce](https://github.com/mendersoftware/mender-server-enterprise/commit/4697bce91a37549d8fb2526ee3f5344412241772))  by @mzedel




- *(gui)* Fixed an issue that prevented opening deployment reports via internal links
([MEN-9909](https://northerntech.atlassian.net/browse/MEN-9909)) ([3d3c412](https://github.com/mendersoftware/mender-server-enterprise/commit/3d3c41232ccb65dfd5bd72db19b47bf3108f8430))  by @mzedel





  - always parse deployment url params on link navigation now

- *(gui)* Align delete icon for delete intents across the ui
([MEN-8279](https://northerntech.atlassian.net/browse/MEN-8279)) ([76d8549](https://github.com/mendersoftware/mender-server-enterprise/commit/76d85497e55a934216b1c78f5b7487ed76dc9556))  by @mzedel




- *(gui)* Clear stale group selection when opening devices from search
([ME-680](https://northerntech.atlassian.net/browse/ME-680)) ([acc6d6f](https://github.com/mendersoftware/mender-server-enterprise/commit/acc6d6f47438ac0889b77a6d1063326dc136e750))  by @mzedel





  only consider a pre-existing group selection when navigating if the
  url is set accordingly - otherwise assume device selection is preferred

- *(gui)* Align device limit validation constraints for sp tenants
([ME-585](https://northerntech.atlassian.net/browse/ME-585)) ([f9ed84c](https://github.com/mendersoftware/mender-server-enterprise/commit/f9ed84cf1297af9d6682f1282a7af40e8cc5fda3))  by @mzedel





  the input validation didn't take the current tenant allocation into account - while the remainder of the form did

- *(gui)* Hide pat creation and revocation for read-only users
([MEN-8386](https://northerntech.atlassian.net/browse/MEN-8386)) ([67251dd](https://github.com/mendersoftware/mender-server-enterprise/commit/67251ddc70dc4e6bcedf35542892dedd18d9d321))  by @mzedel




- *(gui)* Stop filtering out current group from move-to-group dialog
([MEN-9736](https://northerntech.atlassian.net/browse/MEN-9736)) ([6356dbb](https://github.com/mendersoftware/mender-server-enterprise/commit/6356dbb9199fdf24339a28c8f362b4dcda27b809))  by @mzedel





  The destination group dropdown excluded the currently-open sidebar group,
  preventing users from moving devices into the group they were viewing

- *(gui)* Fixed an issue that could lead to unintended dashboard widget removal
([MEN-9865](https://northerntech.atlassian.net/browse/MEN-9865)) ([ebf2f5a](https://github.com/mendersoftware/mender-server-enterprise/commit/ebf2f5ab08db6d38d7d8c8d6c34dc13da7dc97ea))  by @mzedel




- *(gui)* Use absolute path in SP tenant catch-all redirect
([MEN-9489](https://northerntech.atlassian.net/browse/MEN-9489)) ([714b0fb](https://github.com/mendersoftware/mender-server-enterprise/commit/714b0fb69860c32ec045b816ed3dd4ab245ecee2))  by @mzedel




- *(tenantadm)* Allow non-ASCII names when creating child tenants
([ME-686](https://northerntech.atlassian.net/browse/ME-686)) ([970ff41](https://github.com/mendersoftware/mender-server-enterprise/commit/970ff41d6f716fb24faa181f0d1539462913ec8f))  by @LudvigAnderson






- *(tenantadm)* Use the proper context to get the workflows url
([MEN-9926](https://northerntech.atlassian.net/browse/MEN-9926)) ([1bdc294](https://github.com/mendersoftware/mender-server-enterprise/commit/1bdc294573e14dd73c0a6bf491531e5b767d537c))  by @merlin-northern






- *(workflows)* Generalize further the email_notification workflow
([QA-1646](https://northerntech.atlassian.net/browse/QA-1646)) ([ae3ed20](https://github.com/mendersoftware/mender-server-enterprise/commit/ae3ed20cf666b12ab39ace23f132063dfbdf8603))  by @merlin-northern










### Documentation


- *(inventory)* Update list of supported MongoDB operators
([MEN-9927](https://northerntech.atlassian.net/browse/MEN-9927)) ([9f33045](https://github.com/mendersoftware/mender-server-enterprise/commit/9f33045a35f1bb0f55fa5130bcb52ed7c8862ba4))  by @kjaskiewiczz




- *(inventory)* Support boolean attribute values in responses
([MEN-9813](https://northerntech.atlassian.net/browse/MEN-9813)) ([aa2b6de](https://github.com/mendersoftware/mender-server-enterprise/commit/aa2b6deba3c88951e1aed901c14ae4b07a64b6b7))  by @bahaa-ghazal




- *(useradm)* Add api spec for V2 /users/me endpoint
([MEN-9705](https://northerntech.atlassian.net/browse/MEN-9705)) ([c014a7c](https://github.com/mendersoftware/mender-server-enterprise/commit/c014a7c2ab713f75cecbe888fa221dd72a42ebbd))  by @bahaa-ghazal




- *(useradm)* Add api spec for /user/me/email-change/complete endpoint
([MEN-9710](https://northerntech.atlassian.net/browse/MEN-9710)) ([9021a0f](https://github.com/mendersoftware/mender-server-enterprise/commit/9021a0f7aaa0ab3f0c42c0f7edba7db288e991b7))  by @bahaa-ghazal








### Features


- *(admin-panel)* Add deprecation notice broadcast tab
 ([4b18770](https://github.com/mendersoftware/mender-server-enterprise/commit/4b18770afad8b59ea0bfb3d9f51177351b6335df))  by @alfrunes






  Adds a new "Deprecation notice" tab to the hosted Mender admin
  panel for sending feature-deprecation announcements to every active
  tenant. The page is intentionally minimal: paste feature details
  (Markdown), pick the audience (tenant admins by default, or all
  users), preview, then send a test or fire the broadcast.
  
  The form bakes in sensible defaults for subject, title, preheader,
  greeting, and intro so the operator only needs to write the
  feature-specific text. All defaults are overridable under the
  collapsible "Customize" block.

- *(admin-panel)* Use the email_notification to send emails
([QA-1646](https://northerntech.atlassian.net/browse/QA-1646)) ([83d917a](https://github.com/mendersoftware/mender-server-enterprise/commit/83d917a8e64e324a71ce797cd3885cd69b0267b3))  by @merlin-northern






- *(deviceauth)* Add new test device limit
([MEN-9352](https://northerntech.atlassian.net/browse/MEN-9352)) ([b63a7f1](https://github.com/mendersoftware/mender-server-enterprise/commit/b63a7f1feea0e4ebc3477bf92b6d3f2f2f94db20))  by @bahaa-ghazal




- *(deviceauth)* Apply device limit when assigning test devices
([MEN-9352](https://northerntech.atlassian.net/browse/MEN-9352)) ([02214e6](https://github.com/mendersoftware/mender-server-enterprise/commit/02214e6018d3a3d74a8a75ebb93446c64434346e))  by @bahaa-ghazal




- *(deviceauth)* Add device flags to ratelimit's context
([MEN-9235](https://northerntech.atlassian.net/browse/MEN-9235)) ([d7c04cd](https://github.com/mendersoftware/mender-server-enterprise/commit/d7c04cdf5db9c31bf4e894505bfb8bb0c6c7cd84))  by @bahaa-ghazal




- *(deviceauth)* Add caching for device flags
 ([57a6788](https://github.com/mendersoftware/mender-server-enterprise/commit/57a6788bfdebac0717bd617f5f22f34706802776))  by @bahaa-ghazal



- *(devicemonitor)* Add server URL setting defaulting to https://hosted.mender.io
([QA-1646](https://northerntech.atlassian.net/browse/QA-1646)) ([ed22c19](https://github.com/mendersoftware/mender-server-enterprise/commit/ed22c191630e06e9410e9c29ad214639027118c4))  by @merlin-northern





  This change introduces a new setting (like useradm has) that points
  to the url of the server we are running under. It is needed
  for the porting to the generalized email_notification workflow.

- *(gui)* Added test device status chip to device list
([MEN-9670](https://northerntech.atlassian.net/browse/MEN-9670)) ([dc717c4](https://github.com/mendersoftware/mender-server-enterprise/commit/dc717c4192e0703f475ec82d8f694b967f227abf))  by @mineralsfree




- *(gui)* Added special filter handling for test device flag
([MEN-9670](https://northerntech.atlassian.net/browse/MEN-9670)) ([138d2ed](https://github.com/mendersoftware/mender-server-enterprise/commit/138d2ed747f854894b3562be07fad5ce40243971))  by @mineralsfree




- *(gui)* Add disclaimer that synchronized updates were removed in client 4
([MEN-9723](https://northerntech.atlassian.net/browse/MEN-9723)) ([1a8e50b](https://github.com/mendersoftware/mender-server-enterprise/commit/1a8e50b5fb5ab11dca1a289e7ca0a5dcf16a0434))  by @mzedel




- *(gui)* Expand access to advanced device filter operators for everyone & all plans
([MEN-9927](https://northerntech.atlassian.net/browse/MEN-9927)) ([2491c1d](https://github.com/mendersoftware/mender-server-enterprise/commit/2491c1da7634120031d75f32e32ec403468e03ea))  by @mzedel




- *(gui)* Prevented autoselection in autocomplete
([MEN-8643](https://northerntech.atlassian.net/browse/MEN-8643)) ([a13bcf9](https://github.com/mendersoftware/mender-server-enterprise/commit/a13bcf9498c684c5e19f494d5e3590e091b79af6))  by @mzedel




- *(gui)* Added multi-select with checkboxes component
 ([222538d](https://github.com/mendersoftware/mender-server-enterprise/commit/222538d3b702e2e157475305192edf72cd157245))  by @mzedel



- *(gui)* Added text only display mode & aligned autoselection default
 ([72955da](https://github.com/mendersoftware/mender-server-enterprise/commit/72955dab9028b1518fb7cb57c82331718b26dd44))  by @mzedel



- *(gui)* Added rhf integrated async autocomplete
 ([8434505](https://github.com/mendersoftware/mender-server-enterprise/commit/843450539bb7510ce3d68fe440121eeb5903946c))  by @mzedel



- *(gui)* Add confirmation dialog for bulk reject/dismiss actions
([MEN-9601](https://northerntech.atlassian.net/browse/MEN-9601)) ([6fc4b43](https://github.com/mendersoftware/mender-server-enterprise/commit/6fc4b43aa5f994b5b2396cc68f56baa31a301140))  by @mzedel




- *(inventory)* Support additional MongoDB operators
([MEN-9927](https://northerntech.atlassian.net/browse/MEN-9927)) ([9093a43](https://github.com/mendersoftware/mender-server-enterprise/commit/9093a43dc6d9cbba5c9b86eff57558ec8cd63508))  by @kjaskiewiczz





  With this commit we add support for given operators:
  $gt, $gte, $lt, $lte, $ltne, $ne, $exists, $regex

- *(tenantadm)* Apply test device limit when creating organization
([MEN-9352](https://northerntech.atlassian.net/browse/MEN-9352)) ([642ad4e](https://github.com/mendersoftware/mender-server-enterprise/commit/642ad4edb5dcd11420ce8faf8f7710597c4f12ba))  by @bahaa-ghazal




- *(useradm)* Implement V2 /users/me for own user updates
([MEN-9705](https://northerntech.atlassian.net/browse/MEN-9705)) ([e7b8c6f](https://github.com/mendersoftware/mender-server-enterprise/commit/e7b8c6f824fec279089d9036774ac6d33829c0d2))  by @bahaa-ghazal




- *(workflows)* Add email change request workflow
([MEN-9713](https://northerntech.atlassian.net/browse/MEN-9713)) ([18cf940](https://github.com/mendersoftware/mender-server-enterprise/commit/18cf940356ea288acdbe7181af6f2372aac4101f))  by @bahaa-ghazal








### Refactor


- *(gui)* Use destructuring in deviceStatus
([MEN-9670](https://northerntech.atlassian.net/browse/MEN-9670)) ([1238a85](https://github.com/mendersoftware/mender-server-enterprise/commit/1238a858c3344745d772e8922e45e58a669ec4d6))  by @mineralsfree




- *(gui)* Moved chipselect to forms directory and updated consumer imports
 ([c79fcfd](https://github.com/mendersoftware/mender-server-enterprise/commit/c79fcfddfa79e03be781f0bc4fbdbe05d7e9d7b6))  by @mzedel



- *(gui)* Moved unused asyncautocomplete
 ([e4912bf](https://github.com/mendersoftware/mender-server-enterprise/commit/e4912bfcdebb26cb240e086b18e2858792db7606))  by @mzedel



- *(gui)* Dashboard code improvements
([MEN-9312](https://northerntech.atlassian.net/browse/MEN-9312)) ([5691019](https://github.com/mendersoftware/mender-server-enterprise/commit/569101991d0afe5edf6ed5fe91afcb5e5f141d8e))  by @mineralsfree




- Use requset and response attributes with OAS clients
([MEN-9813](https://northerntech.atlassian.net/browse/MEN-9813)) ([f2ca2cf](https://github.com/mendersoftware/mender-server-enterprise/commit/f2ca2cf4d4b55d4a4131f54cc6b09dcd48a75f90))  by @bahaa-ghazal









## 4.2.0-saas.12 - 2026-06-25


### Bug fixes


- *(deployments)* Workaround potential upsert race when creating release
([ME-633](https://northerntech.atlassian.net/browse/ME-633)) ([1f4e963](https://github.com/mendersoftware/mender-server-enterprise/commit/1f4e9632015d856f543a0b46f798ed6838e9f2db))  by @frodeha




- *(deployments)* Sanitize manifest name
([MEN-9844](https://northerntech.atlassian.net/browse/MEN-9844)) ([0565ce2](https://github.com/mendersoftware/mender-server-enterprise/commit/0565ce2971bc44838c10ec7d60d3ecf66916190f))  by @frodeha




- *(deployments)* Prettify error when uploading corrupt manifest artifact
([MEN-9844](https://northerntech.atlassian.net/browse/MEN-9844)) ([984189a](https://github.com/mendersoftware/mender-server-enterprise/commit/984189a14f2dc35c8ae5b695169c432a3e4951a3))  by @frodeha




- *(deviceconnect)* Consolidate default config with config.yaml file
 ([98d656a](https://github.com/mendersoftware/mender-server-enterprise/commit/98d656acf4f9cfcb5e06e69b8c2764af08fa0e70))  by @alfrunes




  The default nats configuration was silently overwritten by the default
  configuration file. The actual default does not make much sense in a
  containerized environments so aligned the default with the value
  inherited (by accident) from the config file.

- *(deviceconnect)* Nats returns an error if failing initial connect
 ([2dfe9e2](https://github.com/mendersoftware/mender-server-enterprise/commit/2dfe9e2c0eecb81008c00b8beb7f59131d4ee842))  by @alfrunes




  Instead of retrying indefinitely.

- *(deviceconnect)* Resolve send on closed channel panic in PipeWriter
 ([b16d373](https://github.com/mendersoftware/mender-server-enterprise/commit/b16d373931750216b28139628ca92a3958672239))  by @frodeha




- *(gui)* Let onboarding tip to create a deployment point to the right button again
 ([0e021a5](https://github.com/mendersoftware/mender-server-enterprise/commit/0e021a56fbada94b2b5ab7c3bba4a05549f19aad))  by @mzedel



- *(gui)* Let all manifest related file types be rejected if they are too large
 ([bfb3e1c](https://github.com/mendersoftware/mender-server-enterprise/commit/bfb3e1c6529b7f4cb53f52b5c933080cf5b3cbdd))  by @mzedel




   - not just `.mender` artifacts

- *(gui)* Prevented release & manifest tag change inputs from causing a page refresh & data loss
([MEN-9850](https://northerntech.atlassian.net/browse/MEN-9850)) ([4d8587c](https://github.com/mendersoftware/mender-server-enterprise/commit/4d8587c0efbfb5bcc614ef61af8c9235166edfc0))  by @mzedel




- *(gui)* Correct accepted devices percentage calculation
([MEN-9864](https://northerntech.atlassian.net/browse/MEN-9864)) ([2355e98](https://github.com/mendersoftware/mender-server-enterprise/commit/2355e986127a2948ea030772fbe5b1ffe365509a))  by @mzedel




- *(gui)* Add rbac support for software/ manifest related functionality via updated nt-gui packages
 ([daf0806](https://github.com/mendersoftware/mender-server-enterprise/commit/daf0806f35e06e92c7bad0ab6a702572520d4e29))  by @mzedel



- *(iot-manager)* Align inconsistent default database name config
 ([3463bf0](https://github.com/mendersoftware/mender-server-enterprise/commit/3463bf0802d9e30cdf11f1cdbb92f82183a9601c))  by @alfrunes




  The database name in the config file is inconsistent with the actual
  default. Starting the service with an empty configuration file would
  render the database empty. This commit also removes all the config file
  overrides.

- *(useradm)* Add software endpoints to ReadReleases permission set
([MEN-9881](https://northerntech.atlassian.net/browse/MEN-9881)) ([fda9c23](https://github.com/mendersoftware/mender-server-enterprise/commit/fda9c23a529b8d6c83b15600db5f479ff7b42d56))  by @frodeha




- *(useradm)* Add read release by name to ReadReleases permission set
([MEN-9881](https://northerntech.atlassian.net/browse/MEN-9881)) ([ddcd39a](https://github.com/mendersoftware/mender-server-enterprise/commit/ddcd39a056dbe080935629f80929c8d2ce9f723e))  by @frodeha




- *(useradm)* Check if user is verified when assigning to tenant
([MEN-9660](https://northerntech.atlassian.net/browse/MEN-9660)) ([7030f72](https://github.com/mendersoftware/mender-server-enterprise/commit/7030f72e543a6730ded01e54401a5e2e8f283dd1))  by @bahaa-ghazal




- *(workflows)* Use WORKFLOWS_MENDER_URL correctly in monitoring alerts
([MEN-9876](https://northerntech.atlassian.net/browse/MEN-9876)) ([7d083dd](https://github.com/mendersoftware/mender-server-enterprise/commit/7d083dd471ae92176ce92e7880d2603a6654f98d))  by @frodeha








### Documentation


- *(deployments)* Extend deployment status with "incompatible_tier" status
([MEN-9630](https://northerntech.atlassian.net/browse/MEN-9630)) ([9e23201](https://github.com/mendersoftware/mender-server-enterprise/commit/9e232014a1cd4206371e5d057790e16c780ef023))  by @bahaa-ghazal




- *(deviceauth)* Added id param according to openAPI syntax
 ([81ec188](https://github.com/mendersoftware/mender-server-enterprise/commit/81ec18874fd66c474482f5cae8faf43c62ed88d4))  by @mineralsfree







### Features


- *(deployments)* Add custom fast validation for manifest
([MEN-9660](https://northerntech.atlassian.net/browse/MEN-9660)) ([f9b0212](https://github.com/mendersoftware/mender-server-enterprise/commit/f9b021287dfc07f4dc8cb1fd7cdd98bf03d6f219))  by @bahaa-ghazal




- *(deployments)* Add rbac to software endpoints
([MEN-9881](https://northerntech.atlassian.net/browse/MEN-9881)) ([57ad195](https://github.com/mendersoftware/mender-server-enterprise/commit/57ad195275e9720622f4f19fed4d41f53bc19aff))  by @frodeha




- *(deployments)* Restrict manifest to system tier devices
([MEN-9630](https://northerntech.atlassian.net/browse/MEN-9630)) ([a5c98c2](https://github.com/mendersoftware/mender-server-enterprise/commit/a5c98c295c55195e4f23ef3683f6279567d154bf))  by @bahaa-ghazal





  Extend the existing feature flag `orchestrator_manifests` which restricts manifests
  to system devices when enabled, and vice versa. This also introduce a new device deployment
  status `incompatible_tier` for deployments that do not satisfy this condition.





### Refactor


- *(deviceauth)* Replace custom workflows client with generated one
([QA-1498](https://northerntech.atlassian.net/browse/QA-1498)) ([2eaafc3](https://github.com/mendersoftware/mender-server-enterprise/commit/2eaafc330a0ee891368250af915412b6431e7e4b))  by @bahaa-ghazal




- *(deviceauth)* Replace custom inventory client with generated one
([QA-1498](https://northerntech.atlassian.net/browse/QA-1498)) ([1b71262](https://github.com/mendersoftware/mender-server-enterprise/commit/1b71262e301c6b6db1165674e51a04b2c5053de7))  by @bahaa-ghazal




- *(deviceauth)* Replace custom iotmanager client with generated one
([QA-1498](https://northerntech.atlassian.net/browse/QA-1498)) ([0e7d2a4](https://github.com/mendersoftware/mender-server-enterprise/commit/0e7d2a40baa79797fe08b4d2f01ef04bcfa2223f))  by @bahaa-ghazal




- *(deviceauth)* Replace custom tenantadm client with generated one
([QA-1498](https://northerntech.atlassian.net/browse/QA-1498)) ([9935e5d](https://github.com/mendersoftware/mender-server-enterprise/commit/9935e5d2f0aa6030a54f3e3e58527989a125b686))  by @bahaa-ghazal




- *(gui)* Let onboarding tooltip position be handled by related components via mui v9 slotprops
 ([e382fbf](https://github.com/mendersoftware/mender-server-enterprise/commit/e382fbf0a8a4e0a930f7248f685911c9b9c8b20c))  by @mzedel



- *(gui)* Handle notifications on group creation instead of relying on store to do so
([MEN-9872](https://northerntech.atlassian.net/browse/MEN-9872)) ([a6b86bc](https://github.com/mendersoftware/mender-server-enterprise/commit/a6b86bc0d956b12d7e65357b8affd549519f10aa))  by @mzedel





  - in order to fix styling issues







## 4.2.0-saas.11 - 2026-06-17 [ROLLED BACK]

!!! warning "Release Rolled Back"
    We reverted Hosted Mender to **4.2.0-saas.10**, and the features/fixes listed below are currently unavailable. We will reintroduce them in the upcoming release.

### Bug fixes


- *(deployments)* Manifest component update order is in the range 1-100
 ([d72434b](https://github.com/mendersoftware/mender-server-enterprise/commit/d72434b49ed33d7a66995b4a25d9a634c63b1395))  by @frodeha




- *(deployments)* Support clearing manifest tags and/or notes
([MEN-9846](https://northerntech.atlassian.net/browse/MEN-9846)) ([e0a6631](https://github.com/mendersoftware/mender-server-enterprise/commit/e0a6631577b5e1a03217cac0887f7c279dab252e))  by @frodeha




- *(deployments)* Remove release from tag validation error
([MEN-9845](https://northerntech.atlassian.net/browse/MEN-9845)) ([41ea077](https://github.com/mendersoftware/mender-server-enterprise/commit/41ea077e5cc8cb202ca11c5d194a162d610a37b4))  by @frodeha




- *(deployments)* Encode generate manifest location header
([MEN-9855](https://northerntech.atlassian.net/browse/MEN-9855)) ([f31de80](https://github.com/mendersoftware/mender-server-enterprise/commit/f31de809302e435eb912d8bb4a9ab647f5e3ed44))  by @frodeha




- *(deviceauth)* Check auth request signature before processing request
 ([b823045](https://github.com/mendersoftware/mender-server-enterprise/commit/b823045ec245776508b7918b21c54bcf6c7a6970))  by @alfrunes




  Reverts 9a371de75681ddf95990bae4300e456331133441 from
  https://github.com/mendersoftware/deviceauth

- *(deviceauth)* `maintenance propagate-inventory` sync tier and flags
 ([1642b97](https://github.com/mendersoftware/mender-server-enterprise/commit/1642b97c022cc3bd850f81694b64f4946d84b6e8))  by @alfrunes





  The command to sync deviceauth data to inventory service also propagates
  the tier and test_device flags.

- *(deviceconnect)* Properly handle stream close errors
 ([6083411](https://github.com/mendersoftware/mender-server-enterprise/commit/6083411c2df4dccd80e623f3f9f51bb9cd291dec))  by @alfrunes



- *(deviceconnect)* Double response on file transfer error handling
 ([1018b88](https://github.com/mendersoftware/mender-server-enterprise/commit/1018b882d29dd903515e0902f75adb4a7706f6ba))  by @alfrunes



- *(deviceconnect)* Ensure mutual exclusive access to ws connection
 ([c532bbe](https://github.com/mendersoftware/mender-server-enterprise/commit/c532bbe357f89c682520270893c9ad42a798c7d1))  by @alfrunes



- *(deviceconnect)* Fixed an issue that would break file transfers w/ a device
 ([ca871b9](https://github.com/mendersoftware/mender-server-enterprise/commit/ca871b9568d2729385351ff7561ffc00460c9cf1))  by @mzedel




  this seems due to an always enabled throttling even if throttling isn't enabled

- *(devicemonitor)* Set device group in alert emails correctly
([QA-1501](https://northerntech.atlassian.net/browse/QA-1501)) ([c34b271](https://github.com/mendersoftware/mender-server-enterprise/commit/c34b2719d5ac0bafcb0fa950b0bce48251f94301))  by @frodeha




- *(gui)* Simplified version information handling to rely on server build time info only
 ([df99594](https://github.com/mendersoftware/mender-server-enterprise/commit/df99594d20a28a47105c4046f7c46599add5e8d1))  by @mzedel




  - more granular version info was removed without replacement

- *(gui)* Reset filtering state when switching groups
([ME-664](https://northerntech.atlassian.net/browse/ME-664)) ([6dc390b](https://github.com/mendersoftware/mender-server-enterprise/commit/6dc390b4d687495adf40e3a938f94217acd6b88c))  by @mineralsfree




  + reset when selecting tier, status
  Ticket: ME-664

- *(gui)* Let manifests always point out missing releases when showing or editing their details
([MEN-9838](https://northerntech.atlassian.net/browse/MEN-9838)) ([a163920](https://github.com/mendersoftware/mender-server-enterprise/commit/a1639200f65e213c9b9476558c6e17e494d4c202))  by @mzedel




- *(gui)* Ensured manifest filter inputs are only usable for users on the required plan
([MEN-9851](https://northerntech.atlassian.net/browse/MEN-9851)) ([b8a7bb0](https://github.com/mendersoftware/mender-server-enterprise/commit/b8a7bb0ac77e16ec2d034c26518c22848b3ba535))  by @mzedel




- *(gui)* Ensured manifests can be linked to directly
([MEN-9840](https://northerntech.atlassian.net/browse/MEN-9840)) ([0341e2e](https://github.com/mendersoftware/mender-server-enterprise/commit/0341e2ebb74da86972c81da7c7ece05dfe08f513))  by @mzedel





  only releases are supposed to be referenced via the browser path, manifests & delta jobs via an id query param

- *(gui)* Ensured tags & device types don't contain whitespace
([MEN-9835](https://northerntech.atlassian.net/browse/MEN-9835)) ([402f6c9](https://github.com/mendersoftware/mender-server-enterprise/commit/402f6c9a4dfc4378df629f8ee6a9708f3d529c4a))  by @mzedel





  to align w/ backend & client expectations

- *(gui)* Let tags etc. no longer appear editable when they are only rendered as data
([MEN-9852](https://northerntech.atlassian.net/browse/MEN-9852)) ([f7e82e5](https://github.com/mendersoftware/mender-server-enterprise/commit/f7e82e55c277d6803dddf1a938b1c9887cc308f3))  by @mzedel




- *(gui)* Ensured manifest handles multi document yaml imports properly
([MEN-9836](https://northerntech.atlassian.net/browse/MEN-9836)) ([2cbc612](https://github.com/mendersoftware/mender-server-enterprise/commit/2cbc6128df40e6410a06dd4ae3ae32bda2087bc4))  by @mzedel





  since there's no clear handling of such a scenario the user will only get informed

- *(gui)* Aligned yaml validation further w/ backend expectations
 ([7053a24](https://github.com/mendersoftware/mender-server-enterprise/commit/7053a24f8fdbfa42a9b6f58f403e6ee6a718ca47))  by @mzedel



- *(pkg)* Modify hubspot client to better handle invalid email addresses
([MEN-9786](https://northerntech.atlassian.net/browse/MEN-9786)) ([df8dc87](https://github.com/mendersoftware/mender-server-enterprise/commit/df8dc87d4b6038cd6a2c1cbf2e37fcea79e0a7fc))  by @kjaskiewiczz




- *(tenantadm)* Set "NT Last Sync" when synchronizing tenants with HubSpot
([MEN-9785](https://northerntech.atlassian.net/browse/MEN-9785)) ([aff6bbf](https://github.com/mendersoftware/mender-server-enterprise/commit/aff6bbfd83f28397f148717cc5e7a04db9f7d62d))  by @kjaskiewiczz




- *(useradm)* Allow users with oauth2 SSO to trigger password reset
([MEN-9691](https://northerntech.atlassian.net/browse/MEN-9691)) ([3d3a0f4](https://github.com/mendersoftware/mender-server-enterprise/commit/3d3a0f43fc08752902c2641756578c26b7cdf6d6))  by @alfrunes




- *(useradm)* Assigning password always overwrite current credentials
([MEN-9691](https://northerntech.atlassian.net/browse/MEN-9691)) ([bdcc420](https://github.com/mendersoftware/mender-server-enterprise/commit/bdcc42055e050301fa8434e6997363bf9c59b88e))  by @alfrunes




- *(useradm)* Lock password reset to current state of user
([MEN-9691](https://northerntech.atlassian.net/browse/MEN-9691)) ([19b8b89](https://github.com/mendersoftware/mender-server-enterprise/commit/19b8b89cbf74677cdd4fb05d4857f3966c3b9c67))  by @alfrunes





  Invalidates issued reset links once one request is completed.

- *(workflows)* Expand email variables before suppression check
([MEN-9866](https://northerntech.atlassian.net/browse/MEN-9866)) ([fae821c](https://github.com/mendersoftware/mender-server-enterprise/commit/fae821c3c545164e702ed6d76ff1b35cda620fb5))  by @frodeha








### Documentation


- *(auditlogs)* Add actions: `password_change` and `auth_method_change`
 ([ae6d751](https://github.com/mendersoftware/mender-server-enterprise/commit/ae6d75125a0481a5793aeff9c5f3cce2fdf80f45))  by @alfrunes



- *(deployments)* Added compatible_types to list software endpoint
 ([67469a9](https://github.com/mendersoftware/mender-server-enterprise/commit/67469a9a664bd215ae5ff202139520cc3004924e))  by @frodeha




- *(deviceauth)* Add API documentation for assigning device flags
([MEN-9575](https://northerntech.atlassian.net/browse/MEN-9575)) ([16ca6cf](https://github.com/mendersoftware/mender-server-enterprise/commit/16ca6cffa2aa813b2f6f9af4bcd3c62b62592263))  by @alfrunes




- *(tenantadm)* Added OAS for upgrade tenant subscription endpoint
([QA-1513](https://northerntech.atlassian.net/browse/QA-1513)) ([814064c](https://github.com/mendersoftware/mender-server-enterprise/commit/814064c7d4b61ef91874884e354fba5162cccb2e))  by @frodeha








### Features


- *(admin-panel)* Move admin-panel to mender-server-enterprise
([MEN-7864](https://northerntech.atlassian.net/browse/MEN-7864)) ([1aa25ea](https://github.com/mendersoftware/mender-server-enterprise/commit/1aa25ea2af361d563d44c43ffed04435a8701b67))  by @alfrunes




- *(deployments)* Added compatible_types to software
 ([589b53b](https://github.com/mendersoftware/mender-server-enterprise/commit/589b53bf2708fc485c4c137a9fb09f4a7b1ddb44))  by @frodeha




- *(deviceauth)* Add feature flag configuration `features.device_flags`
([MEN-9575](https://northerntech.atlassian.net/browse/MEN-9575)) ([c055845](https://github.com/mendersoftware/mender-server-enterprise/commit/c05584513bb17d1c6c26e9f8645595795421aae4))  by @alfrunes




- *(deviceauth)* New API to set device flags
([MEN-9575](https://northerntech.atlassian.net/browse/MEN-9575)) ([8b339ca](https://github.com/mendersoftware/mender-server-enterprise/commit/8b339ca26d4b700a0d402547a9cc4ed56494f1f1))  by @alfrunes






  The new API to assign device flags allows flagging devices as test
  devices which has more generous polling rate limits.

- *(deviceauth)* Accepting devices as trial automatically assign test_device
([MEN-9576](https://northerntech.atlassian.net/browse/MEN-9576)) ([4935fce](https://github.com/mendersoftware/mender-server-enterprise/commit/4935fce4cf90006d0a2dc9f4fcf58d5787dc8746))  by @alfrunes





  By default newly accepted devices for trial accounts are marked as test
  devices to allow frequent polling for a more seamless on-boarding
  experience.

- *(deviceconnect)* Bandwidth control over device connections
 ([8e998c7](https://github.com/mendersoftware/mender-server-enterprise/commit/8e998c7911882e52739768f1adaf869c5cb8bb0a))  by @alfrunes




  Added a new set of configuration to control the bandwidth for devices:
  ```yaml
  bandlimit:
    # Enable bandlimit control (disabled by default)
    enable: false
    # Control the bandwidth rate at which a device can send and receive data
    devices:
      # Template expression for grouping band limits.
      group_expression: "{{.Identity.Plan}}"
      # Named bandlimit groups, the value is a float64 with the number of bytes per second.
      groups:
        enterprise: 10e6  # 10 MB/s
        professional: 5e6 #  5 MB/s
      # The default bandlimit (bytes per second) if no group matches.
      default: 100e3 # 100 KB/s
  ```

- *(gui)* Enabeld manifest notes and tags editing
([MEN-9604](https://northerntech.atlassian.net/browse/MEN-9604)) ([e4e09b9](https://github.com/mendersoftware/mender-server-enterprise/commit/e4e09b93ddaec00f2b0e2c1394542256d067edc9))  by @mzedel




- *(gui)* Let non-existent manifest component be visually different
([MEN-9669](https://northerntech.atlassian.net/browse/MEN-9669)) ([458be57](https://github.com/mendersoftware/mender-server-enterprise/commit/458be57345595697ccaac795270980a403ef3863))  by @mzedel




- *(gui)* Added an unlink Oauth button in profile settings
([MEN-9258](https://northerntech.atlassian.net/browse/MEN-9258)) ([90b1902](https://github.com/mendersoftware/mender-server-enterprise/commit/90b190251a55e6f5f641f0afd0d70cab7f9ef829))  by @mineralsfree




- *(gui)* Added create from copy support for manifest upload
([MEN-9558](https://northerntech.atlassian.net/browse/MEN-9558)) ([9dde0dc](https://github.com/mendersoftware/mender-server-enterprise/commit/9dde0dcb97de406b58be370b7a90f4494dc43be7))  by @mineralsfree




- *(useradm)* Audit log and notification email completing password reset
([MEN-9781](https://northerntech.atlassian.net/browse/MEN-9781)) ([f9c4f2c](https://github.com/mendersoftware/mender-server-enterprise/commit/f9c4f2c829d95562b0d7805f4349e9ec1096c104))  by @alfrunes





  When completing password reset, the user gets an email notification and
  an audit log is recorded. If the user completes password reset and
  changes authentication method, this is reflected in the audit log action
  and the security notification.
  Instructions on how to restore (link) the OAuth2 method is also included
  in the email template.

- *(useradm)* Audit log and email notification when linking OAuth2 SSO
([MEN-9716](https://northerntech.atlassian.net/browse/MEN-9716)) ([00ad363](https://github.com/mendersoftware/mender-server-enterprise/commit/00ad3635346c45d7db00e2c64cb19e070420d469))  by @alfrunes





  When successfully linking a single sign-on method to the account, an
  audit log and a user notification informs about the authentication
  method change.

- *(workflows)* Add 'email_suppression_recipients' setting
([MEN-9866](https://northerntech.atlassian.net/browse/MEN-9866)) ([4b0c18e](https://github.com/mendersoftware/mender-server-enterprise/commit/4b0c18e19423a958a5b2775f8107de87b97a6fee))  by @frodeha








### Refactor


- *(devicemonitor)* Replace client with OpenAPI generated
([QA-1501](https://northerntech.atlassian.net/browse/QA-1501)) ([69b054f](https://github.com/mendersoftware/mender-server-enterprise/commit/69b054f16c458fc0ec77a7c070b2684eaf38b665))  by @alfrunes




- *(gui)* Let input handle submission errors internally to keep user changes
 ([bd0a954](https://github.com/mendersoftware/mender-server-enterprise/commit/bd0a954c3d0235b9726d861b365caba92b316709))  by @mzedel



- *(gui)* Let notes & description inputs handle submissions consistently
 ([8e92097](https://github.com/mendersoftware/mender-server-enterprise/commit/8e920971862a1607f62883b6734c13313db944f3))  by @mzedel




  - to prevent user data loss

- *(gui)* Align user editing drawer with updated design
([MEN-9332](https://northerntech.atlassian.net/browse/MEN-9332)) ([a687e88](https://github.com/mendersoftware/mender-server-enterprise/commit/a687e881f5575240391e960e0137cce4eda64396))  by @mzedel





  & remove password reset checkbox

- *(gui)* Increased setting item rendering flexibility
 ([3ef7004](https://github.com/mendersoftware/mender-server-enterprise/commit/3ef7004ece7d04ef68a1655f0d4641dcb8dc849b))  by @mzedel



- *(gui)* Promote toggle settings to have their own component
 ([f51fc6a](https://github.com/mendersoftware/mender-server-enterprise/commit/f51fc6aaf3ef2f5bd64ab66dc33a0492d01fb35d))  by @mzedel



- *(gui)* Ensure consistent appearance of (toggle )setting items
 ([9924ddf](https://github.com/mendersoftware/mender-server-enterprise/commit/9924ddf055d74a77c1599e2c5e368b1ef3bbb585))  by @mzedel




  & align width w/ updated design

- *(gui)* Align global settings with updated design
([MEN-9327](https://northerntech.atlassian.net/browse/MEN-9327)) ([418b1ec](https://github.com/mendersoftware/mender-server-enterprise/commit/418b1ec62f5af993e27dbf8574f2fbd2415e2aff))  by @mzedel




- *(gui)* Align roles & users overview with updated design
([MEN-9335](https://northerntech.atlassian.net/browse/MEN-9335)) ([7595a53](https://github.com/mendersoftware/mender-server-enterprise/commit/7595a530134499f0de88ea58fc78cde30e664eaf))  by @mzedel




- *(gui)* Align role creation/editing drawer with updated design
([MEN-9333](https://northerntech.atlassian.net/browse/MEN-9333)) ([b15c8a2](https://github.com/mendersoftware/mender-server-enterprise/commit/b15c8a247e748c2d2cd875f58d55ee9f8c986bd0))  by @mzedel




- *(gui)* Improved typescript adoption in artifact details
([MEN-9319](https://northerntech.atlassian.net/browse/MEN-9319)) ([3a23ed3](https://github.com/mendersoftware/mender-server-enterprise/commit/3a23ed338391caf52c4fd26abce2184492140edd))  by @mineralsfree




- *(gui)* Align user settings with updated design
([MEN-9336](https://northerntech.atlassian.net/browse/MEN-9336)) ([1bba7e8](https://github.com/mendersoftware/mender-server-enterprise/commit/1bba7e8e9fa86583ca04e80cd087f80e61601d2e))  by @mzedel




- *(gui)* Let organization organization + sso settings rely more on default setting appearance
 ([88b1d37](https://github.com/mendersoftware/mender-server-enterprise/commit/88b1d379ec6bac9eb9e6b1b6cd357780befe3d8b))  by @mzedel




  to further align w/ updated design

- *(pkg)* Remove duplicate code paths in rest.utils
 ([541f1f3](https://github.com/mendersoftware/mender-server-enterprise/commit/541f1f3e05b350179c1bc07691b1391575b4b8dd))  by @alfrunes



- *(useradm)* Use generated deployments client
([QA-1513](https://northerntech.atlassian.net/browse/QA-1513)) ([e6900ea](https://github.com/mendersoftware/mender-server-enterprise/commit/e6900ea925f7bf2d7ba5fb00698150f956f169d2))  by @frodeha




- *(useradm)* Use generated inventory client
([QA-1513](https://northerntech.atlassian.net/browse/QA-1513)) ([03e2310](https://github.com/mendersoftware/mender-server-enterprise/commit/03e231099fb785e67687e0fc5b513f45190fb261))  by @frodeha




- *(useradm)* Use generated tenantadm client
([QA-1513](https://northerntech.atlassian.net/browse/QA-1513)) ([c0a97fe](https://github.com/mendersoftware/mender-server-enterprise/commit/c0a97fe843e2059d32d7075404ab633765cd03e6))  by @frodeha




- *(useradm)* Use generated workflows client
([QA-1513](https://northerntech.atlassian.net/browse/QA-1513)) ([71df140](https://github.com/mendersoftware/mender-server-enterprise/commit/71df140ce80925d3a4b812bf33e9f93c667aee10))  by @frodeha




- Added support for `external` test environment in ng tests
 ([09aefa4](https://github.com/mendersoftware/mender-server-enterprise/commit/09aefa4dc814073b07b1afdf822aaab20d8e1482))  by @frodeha



- Update opensource ng tests to support abstract environments
 ([6f6e31f](https://github.com/mendersoftware/mender-server-enterprise/commit/6f6e31fe11693effa95db241f78a133056807f4a))  by @frodeha



- Update enterprise ng tests to support abstract environments
 ([1acaae5](https://github.com/mendersoftware/mender-server-enterprise/commit/1acaae58541d030ff968b4a0cf6264304ae93e82))  by @frodeha









## 4.2.0-saas.10 - 2026-05-29


### Bug fixes


- *(deployments)* Remove shadowing of ReleaseBase `kind` property
([MEN-9753](https://northerntech.atlassian.net/browse/MEN-9753)) ([7eb0476](https://github.com/mendersoftware/mender-server-enterprise/commit/7eb0476468069fd7370d0f0ad80bebe718f7051e))  by @frodeha




- *(gui)* Ensured manifest actions have a reasonable label when manifest details are shown
 ([edf5adf](https://github.com/mendersoftware/mender-server-enterprise/commit/edf5adf35253c669047328405a8ab1e339616016))  by @mzedel



- *(gui)* Unwraped the plan upgrade request to handle the errors correctly
 ([37c2e9f](https://github.com/mendersoftware/mender-server-enterprise/commit/37c2e9f91d6f1396de9c33527af2838196f66759))  by @mineralsfree



- *(gui)* Ensured internal links can be opened in a new tab too
 ([b7b9b4e](https://github.com/mendersoftware/mender-server-enterprise/commit/b7b9b4e2f68c9beefca9308ede9129f1ba0caa38))  by @mzedel



- *(inventory)* Temporarily allow boolean attribute values internally
([ME-670](https://northerntech.atlassian.net/browse/ME-670)) ([6571a86](https://github.com/mendersoftware/mender-server-enterprise/commit/6571a865a7708f57b84abbdf67392046aef88049))  by @frodeha




- *(pkg)* Allow unknown fields in responses to pkg/api/client
 ([ab878ad](https://github.com/mendersoftware/mender-server-enterprise/commit/ab878ade79a363b8485b707bf5c3d6c72ae1b274))  by @frodeha








### Documentation


- *(deployments)* Document tag filtering in get software alpha endpoint
([MEN-9607](https://northerntech.atlassian.net/browse/MEN-9607)) ([e007b93](https://github.com/mendersoftware/mender-server-enterprise/commit/e007b9315a381d0f984d014ccf9ef8fa3c9cc101))  by @frodeha








### Features


- *(deployments)* Added tag filtering in get software alpha endpoint
([MEN-9607](https://northerntech.atlassian.net/browse/MEN-9607)) ([9821532](https://github.com/mendersoftware/mender-server-enterprise/commit/9821532e849472bcdd934dd715fb58ddc6c32ad9))  by @frodeha




- *(gui)* Added tag filtering on manifests list
([MEN-9560](https://northerntech.atlassian.net/browse/MEN-9560)) ([b88baf5](https://github.com/mendersoftware/mender-server-enterprise/commit/b88baf54e3f29b0d9cb3803ee03293779c128b21))  by @mzedel








### Refactor


- *(deviceconnect)* Unify session initialization across APIs
 ([fee796e](https://github.com/mendersoftware/mender-server-enterprise/commit/fee796e10069edddbe41d503bd160af7207c37ab))  by @alfrunes



- *(deviceconnect)* Replace workflows client with OAS generated client
([QA-1500](https://northerntech.atlassian.net/browse/QA-1500)) ([224cfae](https://github.com/mendersoftware/mender-server-enterprise/commit/224cfae1b4c8678f7bf55fe15a8c57875980fc83))  by @alfrunes




- *(gui)* Aligned multiline text input w/ updated design & usage
([MEN-9730](https://northerntech.atlassian.net/browse/MEN-9730)) ([9d42833](https://github.com/mendersoftware/mender-server-enterprise/commit/9d428339db1f8ace159a426efd81939ab281db11))  by @mzedel








### Revert


- Remove workflows and audit logs from open-source
 ([b487d4c](https://github.com/mendersoftware/mender-server-enterprise/commit/b487d4c7d87f4fdeb0c0a5ee6bc40f6db37ee849))  by @alfrunes




  This reverts commit f0fa5736d1579bd8616488eb92fc3dea22b9b768.






## 4.2.0-saas.9 - 2026-05-27


### Bug fixes


- *(deployments)* Set default value for SettingMaxDeploymentArtifactSizeMicroDevices
([MEN-9688](https://northerntech.atlassian.net/browse/MEN-9688)) ([c2d595e](https://github.com/mendersoftware/mender-server-enterprise/commit/c2d595e8fe100dac885917c3454baf0c70b995a6))  by @kjaskiewiczz




- *(deployments)* Parse manifest tags as csv
 ([7fd1c6c](https://github.com/mendersoftware/mender-server-enterprise/commit/7fd1c6c19560f7baf896f48c586c67d01f0e5b4b))  by @frodeha




- *(deployments)* Validate release type before removing its artifact
 ([a594dbc](https://github.com/mendersoftware/mender-server-enterprise/commit/a594dbccfcc588891bdeb4224db001c579e84d34))  by @bahaa-ghazal




  Currently, we try to delete the artifact attached to a release before deleting the release itself.
  If the name belongs to a manifest, it will delete the artifact without deleting the manifest.

- *(deployments)* Omit empty tags when listing software tags
 ([3b9731e](https://github.com/mendersoftware/mender-server-enterprise/commit/3b9731e60d7fd24796baafd47ae729cd6db2df98))  by @bahaa-ghazal



- *(deployments)* Prevent manifest upload from exceeding tag limit
 ([8afdf77](https://github.com/mendersoftware/mender-server-enterprise/commit/8afdf772ecd3cf079631fea731672c462c6b9af3))  by @alfrunes



- *(deployments)* Set correct location header when generating manifests
 ([62ed4f9](https://github.com/mendersoftware/mender-server-enterprise/commit/62ed4f9f73d3f66dd7d75469e1d79497f7175522))  by @frodeha




- *(deviceconnect)* Improve error handling reaching session recording limit
 ([1b097ed](https://github.com/mendersoftware/mender-server-enterprise/commit/1b097ed4d437e76b7b30167c07113bd2664a0d8a))  by @alfrunes




  When reaching the limit for the session, the websocket connection is
  closed instead of leaving it open and detached.

- *(deviceconnect)* Mender commands regression after stream migration
 ([a991a25](https://github.com/mendersoftware/mender-server-enterprise/commit/a991a258c0f6a4ba207c9d4a09178fbffeb24738))  by @alfrunes




  Due to a duplicate implementation of the mender commands API for the
  internal APIs, only the public APIs were migrated to use the new
  connection oriented streams.

- *(devicemonitor)* Added missing AlertDetail properties to oas
 ([3420f2a](https://github.com/mendersoftware/mender-server-enterprise/commit/3420f2ad724941205795fc1f6198cf84aa2f9d05))  by @frodeha




- *(gui)* Fixed an issue that prevented requiring confirmation on deployment creation
 ([7820676](https://github.com/mendersoftware/mender-server-enterprise/commit/782067689f23fa7e9b98e9d4b32a15d472de1f47))  by @mzedel



- *(pkg)* Masking error when checking for invalidated cache
 ([8f8f718](https://github.com/mendersoftware/mender-server-enterprise/commit/8f8f71867469e4e86ef44636d26b94167b9fedf6))  by @alfrunes




  When getting a value from the cache using the pkg/redis.GetCache, any
  other error than redis.Nil is masked by ErrCacheInvalid making it appear
  that the cache was invalidated on any other type of error.

- *(pkg)* Hubspot: add missing property "trial expiration" to tenant model
([MEN-9733](https://northerntech.atlassian.net/browse/MEN-9733)) ([e6a770d](https://github.com/mendersoftware/mender-server-enterprise/commit/e6a770d9de7ded180320c3461be465b0adfd6bb6))  by @kjaskiewiczz




- *(pkg)* Modify hubspot client to ignore contacts with invalid email addresses
([MEN-9732](https://northerntech.atlassian.net/browse/MEN-9732)) ([3b766a1](https://github.com/mendersoftware/mender-server-enterprise/commit/3b766a1a39cd8bec62d17376cf1adb7e124cf0c8))  by @kjaskiewiczz





  This commit adds special handling for INVALID_EMAIL error from HubSpot.
  The reason for that is that HubSpot has more strict email address
  validation than our backend.
  We will not synchronize users with email addresses that are considered
  invalid by HubSpot.

- *(useradm)* Require password before returning missing two-factor
([MEN-9722](https://northerntech.atlassian.net/browse/MEN-9722)) ([ea20692](https://github.com/mendersoftware/mender-server-enterprise/commit/ea206922b767ade1e88b1997732b83fb4d9b76a5))  by @alfrunes





  To disclose whether a user has two-factor enabled, it needs to first
  enter the correct password to prevent user enumeration.

- *(useradm)* Harden basic auth timing information
 ([71f9424](https://github.com/mendersoftware/mender-server-enterprise/commit/71f942413b674bcdc924320b976ff9102200cf08))  by @alfrunes



- *(useradm)* Allow ReadAuditLogs to access session playback
([ME-660](https://northerntech.atlassian.net/browse/ME-660)) ([8ba2311](https://github.com/mendersoftware/mender-server-enterprise/commit/8ba2311876e08fcbb6a3b5d0644ecb73a47589b2))  by @LudvigAnderson






- *(workflows)* Remove HTML version of security notifications
([MEN-9662](https://northerntech.atlassian.net/browse/MEN-9662)) ([f628f4b](https://github.com/mendersoftware/mender-server-enterprise/commit/f628f4b4bb494092bab0a44c005cb47fde6b7596))  by @alfrunes




- *(workflows)* Bump version of security e-mail workflows
 ([2fc68d9](https://github.com/mendersoftware/mender-server-enterprise/commit/2fc68d9cfb6842b07717834591c6a7f5161d6e03))  by @frodeha





  In f628f4b4bb494092bab0a44c005cb47fde6b7596 we removed the HTML version
  of these security e-mail notifications. We need to also bump the version
  of each workflow definition so they are updated in the database. Without
  this, the workflows fail to execute as they're expecting the html
  template to exist still.





### Documentation


- *(deployments)* Added OAS for list software tags alpha endpoint
([MEN-9434](https://northerntech.atlassian.net/browse/MEN-9434)) ([f227825](https://github.com/mendersoftware/mender-server-enterprise/commit/f227825cd7049734999cd59601325c3e508bbcb4))  by @frodeha




- *(deployments)* Added OAS for generate manifest alpha endpoint
([MEN-9556](https://northerntech.atlassian.net/browse/MEN-9556)) ([c0fc772](https://github.com/mendersoftware/mender-server-enterprise/commit/c0fc772e6f4ef44a299ea09dfc91f0596ecc2ab2))  by @frodeha




- *(deployments)* Remove invalid encoding from manifest upload request body
 ([e269f60](https://github.com/mendersoftware/mender-server-enterprise/commit/e269f604f4fb6c7ab7b900522b65607fd325c86a))  by @frodeha




- *(deployments)* Add API spec for `DELETE /manifests` endpoint
([MEN-9555](https://northerntech.atlassian.net/browse/MEN-9555)) ([786c098](https://github.com/mendersoftware/mender-server-enterprise/commit/786c09874d17d4fb9fc5d8d65284bf1b167ef8e4))  by @bahaa-ghazal




- *(deployments)* Add tag query to get manifests alpha endpoint
([MEN-9434](https://northerntech.atlassian.net/browse/MEN-9434)) ([f028555](https://github.com/mendersoftware/mender-server-enterprise/commit/f0285554967f13cb3c9f812c470843592df77197))  by @frodeha




- *(deployments)* Remove status code 402 from 'Explain Log' API
([MEN-9673](https://northerntech.atlassian.net/browse/MEN-9673)) ([ac43a3e](https://github.com/mendersoftware/mender-server-enterprise/commit/ac43a3ec300eb4982be36823453a14f3055b3e55))  by @alfrunes




- *(deployments)* Add `GET /software` endpoint for listing softwares
([MEN-9607](https://northerntech.atlassian.net/browse/MEN-9607)) ([8fa9bec](https://github.com/mendersoftware/mender-server-enterprise/commit/8fa9bec4f5ee5e0ae751d75472d1abf7f41f1f07))  by @bahaa-ghazal




- *(deployments)* API specification for updating manifest metadata
([MEN-9554](https://northerntech.atlassian.net/browse/MEN-9554)) ([0737096](https://github.com/mendersoftware/mender-server-enterprise/commit/073709632c20c3b8ddf7374d247206feeba488f3))  by @alfrunes




- *(deployments)* Align internal deploy configuration with reality
 ([f748010](https://github.com/mendersoftware/mender-server-enterprise/commit/f748010789ce21a3308fe9fc2a7a59a5861ab79e))  by @alfrunes



- *(devicemonitor)* Document missing alert properties
([QA-1502](https://northerntech.atlassian.net/browse/QA-1502)) ([1e1f193](https://github.com/mendersoftware/mender-server-enterprise/commit/1e1f193c1047b239fbfd651feae7d563bb778cfe))  by @frodeha




- *(tenantadm)* Add device_limits to create child tenant request body
([MEN-9571](https://northerntech.atlassian.net/browse/MEN-9571)) ([687c0b7](https://github.com/mendersoftware/mender-server-enterprise/commit/687c0b7b0b2de77922bfd33b25158b224f389617))  by @frodeha








### Features


- *(create-artifact-worker)* Added new command for generating manifests
([MEN-9556](https://northerntech.atlassian.net/browse/MEN-9556)) ([e4e29c9](https://github.com/mendersoftware/mender-server-enterprise/commit/e4e29c9d7ebf9e3e363d1a32d68de5a8b0389fe9))  by @frodeha




- *(deployments)* Add endpoint for deleting manifests
([MEN-9555](https://northerntech.atlassian.net/browse/MEN-9555)) ([614d1b4](https://github.com/mendersoftware/mender-server-enterprise/commit/614d1b4416c86809beb1e2b91f7a305e7271cbed))  by @bahaa-ghazal




- *(deployments)* Implemented get software tags alpha endpoint
([MEN-9434](https://northerntech.atlassian.net/browse/MEN-9434)) ([498bc6d](https://github.com/mendersoftware/mender-server-enterprise/commit/498bc6d6aac4aae977ca6ba0b1506b62f888253f))  by @frodeha




- *(deployments)* Endpoint for updating tags and notes of a Manifest
([MEN-9554](https://northerntech.atlassian.net/browse/MEN-9554)) ([c1f8944](https://github.com/mendersoftware/mender-server-enterprise/commit/c1f89443588acd58a61a746e41a87b37337d82dd))  by @alfrunes





  A new PATCH API for a Manifest resource allows updating the notes and
  tags of a manifest.

- *(deployments)* Added implementation for generate manifest endpoint
([MEN-9556](https://northerntech.atlassian.net/browse/MEN-9556)) ([088a528](https://github.com/mendersoftware/mender-server-enterprise/commit/088a52885ff39420da23f1d3c405bd1a1091d601))  by @frodeha




- *(deployments)* Implement endpoint for listing software
([MEN-9607](https://northerntech.atlassian.net/browse/MEN-9607)) ([5b645f1](https://github.com/mendersoftware/mender-server-enterprise/commit/5b645f161b3a5e6487f1dd1bda29593070aadf53))  by @bahaa-ghazal




- *(deviceconnect)* Add reliable transmission control over NATS sessions
([MEN-4595](https://northerntech.atlassian.net/browse/MEN-4595)) ([343308f](https://github.com/mendersoftware/mender-server-enterprise/commit/343308fb4fb3610cb73e45d0d052a477dcea2abd))  by @alfrunes





  To remove the end-to-end transmission control bottleneck from the protocol,
  we need to fix the unreliable link.

- *(gui)* Added Manifest creation Drawer
([MEN-9436](https://northerntech.atlassian.net/browse/MEN-9436)) ([0e0095a](https://github.com/mendersoftware/mender-server-enterprise/commit/0e0095a9ea4ed904e64e9cc8dc7bb40279f8ef66))  by @mineralsfree




- *(gui)* No longer hide rbac settings for users capable of managing rbac
 ([16ecc24](https://github.com/mendersoftware/mender-server-enterprise/commit/16ecc2470360fc7711e7a7a79679cb9494c31917))  by @mzedel



- *(gui)* Added manifests removal functionality
([MEN-9609](https://northerntech.atlassian.net/browse/MEN-9609)) ([bb99a1f](https://github.com/mendersoftware/mender-server-enterprise/commit/bb99a1f2cc9b288345bef8a3239fd696fdcba9e2))  by @mineralsfree




- *(useradm)* Link an oauth2 provider via POST /oauth2/link
([MEN-9257](https://northerntech.atlassian.net/browse/MEN-9257)) ([0561444](https://github.com/mendersoftware/mender-server-enterprise/commit/0561444a21e0dffa20ac61519bc477de6c778381))  by @merlin-northern






- *(useradm)* Added config for e-mail domains that is auto verified
 ([977bbbc](https://github.com/mendersoftware/mender-server-enterprise/commit/977bbbc9848b8850e2520cd5f860543bedf91fad))  by @frodeha





  Added a new configuration option that instructs useradm to
  automatically verify users created with an e-mail address
  from one of the domains in the list. This option is intended
  for use in test and/or demo environments where the use of users
  with fake e-mail addresses is common/useful.
  
  The use of this configuration option is not adviced outside of
  such environments and by default no domains are trusted in this
  way.

- *(useradm)* Verify users email address when they successfully use a password reset link
([MEN-9156](https://northerntech.atlassian.net/browse/MEN-9156)) ([af0cd61](https://github.com/mendersoftware/mender-server-enterprise/commit/af0cd61f00143b445597222c366565c95db1b601))  by @kjaskiewiczz




- *(workflows)* Added config option for suppressing e-mail sending
 ([d4eef18](https://github.com/mendersoftware/mender-server-enterprise/commit/d4eef18b57030693b4ce612343e4bbf7478b195d))  by @frodeha





  Added a configuration option in workflows that instructs the server
  to not send e-mails to configured domains. This is useful in test/demo
  environments where the use of fake e-mails (which will bounce and affect
  e-mail reputation) is common.
  
  By default no domains are suppressed.





### Refactor


- *(deployments)* Replace get release tags with get software tags
 ([7f32320](https://github.com/mendersoftware/mender-server-enterprise/commit/7f323206b002110fdd79ff476870fc35c630534b))  by @frodeha




- *(deviceconfig)* Migrate internal clients to use OAS client
 ([7cb8f66](https://github.com/mendersoftware/mender-server-enterprise/commit/7cb8f66843cba0c740351bed191ca211c191dc6c))  by @alfrunes



- *(deviceconnect)* Refactor playback to use connection oriented stream
 ([0f515e5](https://github.com/mendersoftware/mender-server-enterprise/commit/0f515e5578c0535be5435024d1df0ed085eec7c2))  by @alfrunes



- *(deviceconnect)* Consolidate error handling and ws close frame
 ([fa2e24e](https://github.com/mendersoftware/mender-server-enterprise/commit/fa2e24e91fbbacd3a55e3d04ba7340a43b32e52f))  by @alfrunes



- *(deviceconnect)* Mender command APIs to use connection oriented streams
 ([0ecf9ed](https://github.com/mendersoftware/mender-server-enterprise/commit/0ecf9ed134961b85df3f754857f55d96af4694d2))  by @alfrunes



- *(deviceconnect)* File transfer to use connection oriented NATS transport
([MEN-4595](https://northerntech.atlassian.net/browse/MEN-4595)) ([da9ecda](https://github.com/mendersoftware/mender-server-enterprise/commit/da9ecda360a09cd11ddb5ecb9711fa6ef32a039a))  by @alfrunes




- *(gui)* Add rhf foundation to deployment creation
 ([33a70df](https://github.com/mendersoftware/mender-server-enterprise/commit/33a70df32769b4f4606177b1b2b2c0985f9cb9d6))  by @mzedel




  - as an intermediate step to sync form values back to the parent component for location param sync

- *(gui)* Migrate checkbox only sections to rhf compatible
 ([3c61aee](https://github.com/mendersoftware/mender-server-enterprise/commit/3c61aee7f71b2e0464a6b9a84a28e456bd6a569f))  by @mzedel



- *(gui)* Migrate deployment retries to numberinput/  rhf
 ([fd6db48](https://github.com/mendersoftware/mender-server-enterprise/commit/fd6db48fd03a606679ce81cf8da8982ffe94783a))  by @mzedel




  - attempts vs retry conversion now happens on submit

- *(gui)* Let deployment device limit rely on numberinput/ rhf
 ([9004f01](https://github.com/mendersoftware/mender-server-enterprise/commit/9004f015bc077a994dd66aa9ec9eb6e2a57170b8))  by @mzedel



- *(gui)* Migrate synced deployments to rhf value tracking too
 ([0116371](https://github.com/mendersoftware/mender-server-enterprise/commit/011637193868015b445925d730af5232c5f59642))  by @mzedel



- *(gui)* Track deployment scheduling with rhf too
 ([63cf60e](https://github.com/mendersoftware/mender-server-enterprise/commit/63cf60e4c2963fdcf74f8f238eeec406ddddb32a))  by @mzedel



- *(gui)* Migrate target device + proxy deployment release selection to rhf
 ([9245535](https://github.com/mendersoftware/mender-server-enterprise/commit/92455355b91b52b03335074c7f471980ddaae5f2))  by @mzedel



- *(gui)* Prepared deployment phase config for design changes
 ([71dbadc](https://github.com/mendersoftware/mender-server-enterprise/commit/71dbadcd534795c60f8077ede72ceecac4cb43ed))  by @mzedel



- *(gui)* Remove deployment object reliance for rhf
 ([48abeb2](https://github.com/mendersoftware/mender-server-enterprise/commit/48abeb22b098fd76cedad7e5630009864ef8a935))  by @mzedel




  - non-form native deployment information is extracted to a separate hook to limit data sync efforts, at the cost of potential extra requests

- *(gui)* Unified quick actions to use reusable component for consistent styling
 ([c8248b9](https://github.com/mendersoftware/mender-server-enterprise/commit/c8248b91ad6d3947f28a0385b2a1a3c721e118ac))  by @mzedel



- *(inventory)* Migrate internal clients to OAS generated client
([QA-1502](https://northerntech.atlassian.net/browse/QA-1502)) ([cac46d2](https://github.com/mendersoftware/mender-server-enterprise/commit/cac46d21ad8af80102d42ab2eaa7aa5f5b47b742))  by @frodeha




- *(inventory)* Remove devicemonitor client
([QA-1502](https://northerntech.atlassian.net/browse/QA-1502)) ([580e19b](https://github.com/mendersoftware/mender-server-enterprise/commit/580e19be52defde359502066f8f21513a9fa0dec))  by @frodeha





  Devicemonitor is not a supported opensource feature. As part of an
  ongoing migration effort to use autogenerated internal clients we are
  replacing handwritten clients wherever possible. Since devicemonitor is
  not a supported opensource feature, the autogenerated client in opensource
  does not include the devicemonitor API. Therefore we're simply removing
  the handwritten one here.
  
  We're leaving the inventory HTTP APIs that used the client previously as
  to not introduce API breakage, but they will always find 0 alerts,
  effectively making them into no-ops here in opensource.

- *(iot-manager)* Replace internal clients with OpenAPI generated
([QA-1511](https://northerntech.atlassian.net/browse/QA-1511)) ([9430289](https://github.com/mendersoftware/mender-server-enterprise/commit/9430289becbe8af513167f27b3a860f8aa1fc848))  by @alfrunes




- *(useradm)* Lower cyclometic complexity and trim redundant email state
 ([0476529](https://github.com/mendersoftware/mender-server-enterprise/commit/0476529e20dd9f7edd0da1244c4806d982abbe0e))  by @alfrunes







### Revert


- "fix(deployments): Put log explain endpoint behind paywall"
([MEN-9673](https://northerntech.atlassian.net/browse/MEN-9673)) ([1a1d044](https://github.com/mendersoftware/mender-server-enterprise/commit/1a1d044152027273cb233438af9cdd049045b29d))  by @alfrunes





  This reverts commit 438bc53a3665f3a74f9df04b0d69738ad3b5173d.
- "refactor(deployments): replace get release tags with get software tags"
 ([0d42895](https://github.com/mendersoftware/mender-server-enterprise/commit/0d42895baa4c6cba39f25bc1367f4a879ec17db6))  by @alfrunes




  This reverts commit 7f323206b002110fdd79ff476870fc35c630534b.






## 4.2.0-saas.8 - 2026-05-07


### Bug fixes


- *(deployments)* Skip inventory fallback when result page overshoots
([ME-651](https://northerntech.atlassian.net/browse/ME-651)) ([84c2cb6](https://github.com/mendersoftware/mender-server-enterprise/commit/84c2cb655f89e17ba420782e349a7991b1a01f53))  by @LudvigAnderson






- *(deployments)* Check software kind when fetching a manifest
 ([4cdedc4](https://github.com/mendersoftware/mender-server-enterprise/commit/4cdedc4353f034b41358a7e98ec43ee70cc745bd))  by @bahaa-ghazal



- *(deviceconnect)* Properly flush session recording
 ([212e018](https://github.com/mendersoftware/mender-server-enterprise/commit/212e0188dff1a674e58b90a487e4ad2f1e0a0b91))  by @alfrunes




  If client closes the connection, the context is cancelled
  and the buffered data is not recorded.

- *(gui)* Refresh the configuration device details on finished deployment
([MEN-6415](https://northerntech.atlassian.net/browse/MEN-6415)) ([1e88383](https://github.com/mendersoftware/mender-server-enterprise/commit/1e883830f6497b6ea62d1b58e4a67ae486409d4d))  by @merlin-northern







- *(gui)* Ensured deployment phase size input doesn't get fully compressed
 ([1c9ec69](https://github.com/mendersoftware/mender-server-enterprise/commit/1c9ec69383153db901363fbaed937ef37da0c131))  by @mzedel



- *(gui)* Fixed an issue that could crash the app by showing & hiding search results too fast
 ([6d69a62](https://github.com/mendersoftware/mender-server-enterprise/commit/6d69a625e3f90947a027a29ee832384cf736c4c0))  by @mzedel







### Refactor


- *(deviceconnect)* Move buffering and compression to Recorder interface
 ([e7231c4](https://github.com/mendersoftware/mender-server-enterprise/commit/e7231c4f7e0bcaf43281b0e480f8e7fab6c59ab2))  by @alfrunes




  Swapped the order of gzip compression and buffered I/O to always write
  fixed compressed record sizes. Previous implementation would flush when
  writing block size of uncompressed data.







## 4.2.0-saas.7 - 2026-05-05


### Bug fixes


- *(deployments)* Stop decreasing phase counter on failed deployments
([MEN-9509](https://northerntech.atlassian.net/browse/MEN-9509)) ([44f86a6](https://github.com/mendersoftware/mender-server-enterprise/commit/44f86a699a28d77c2162e3dbd620c728fc7d52a5))  by @bahaa-ghazal




- *(deployments)* Removed type discriminator from ReleaseBase JSON
 ([a4f4a14](https://github.com/mendersoftware/mender-server-enterprise/commit/a4f4a14b64b481753164e4771f37c1b8dda46145))  by @frodeha



- *(deployments)* Removed omitempty from ImageMeta description
 ([74a46d4](https://github.com/mendersoftware/mender-server-enterprise/commit/74a46d436bcce415af1eedabb5b774e9b2566bc7))  by @frodeha




  The `description` property of ImageMeta maps to the description property
  of both ArtifactV2 and ArtifactV1 in OAS. In V2, description is marked
  as required, while in V1 it is not. Removing the required from V2 would
  be a breaking change, so we must rather always return a (potentially
  empty) value in order to respect both versions.

- *(deployments)* Made 'modified' an optional property of Manifest
([MEN-9049](https://northerntech.atlassian.net/browse/MEN-9049)) ([9b4e1ca](https://github.com/mendersoftware/mender-server-enterprise/commit/9b4e1ca2916ce2a11d134ee74bb34d709612a683))  by @frodeha




- *(deployments)* Added description validation in multipart uploads
([MEN-9049](https://northerntech.atlassian.net/browse/MEN-9049)) ([10e1233](https://github.com/mendersoftware/mender-server-enterprise/commit/10e123345ead09e87ee3f12d1c4f650dfec720cf))  by @frodeha




- *(deployments)* Set Manifest modified based on artifact modified
 ([ff00f2c](https://github.com/mendersoftware/mender-server-enterprise/commit/ff00f2c00451c2746f11eaa2b11381163f8d9571))  by @frodeha




- *(deployments)* Use common default openapi client configuration
 ([5ddd1a1](https://github.com/mendersoftware/mender-server-enterprise/commit/5ddd1a1a3f3689ff40aaafc30c4f883174c62379))  by @frodeha




- *(deployments)* Fixed an issue that prevented filtering deployments by group in some cases
([MEN-9639](https://northerntech.atlassian.net/browse/MEN-9639)) ([7ade951](https://github.com/mendersoftware/mender-server-enterprise/commit/7ade951ff6339165e8e8d733ad593c08cac8607f))  by @mzedel




- *(deployments)* Correct total count when result page overshoots
([MEN-9643](https://northerntech.atlassian.net/browse/MEN-9643)) ([fe9ee10](https://github.com/mendersoftware/mender-server-enterprise/commit/fe9ee10663029f4b7519d660752d5e630d5138fc))  by @LudvigAnderson






  The `/api/management/v2/deployments/deployments` endpoint previously returned `X-Total-Count: 0` when the requested page was beyond the last page of a non-empty result set. The total count is now preserved through empty pages.

- *(deviceauth)* Standardized and condensed internal limit APIs
([MEN-9470](https://northerntech.atlassian.net/browse/MEN-9470)) ([4cf6b45](https://github.com/mendersoftware/mender-server-enterprise/commit/4cf6b4515b863759caffbd6ea14d9575cfeb674b))  by @frodeha





  Removed some unused internal limits API endpoints, adapted the API
  response format used in the managment APIs and standardized on a
  single way of reading limits in the business logic layer. Instead
  of having 3-4 different business logic operations to read limits /
  tenant limits / tenants limit / tenants limits. We now have one read
  limits and one read limit (which simple calls read limits internally)
  operation.
  
  The aim is to have _one_ place we have reading logic (0 vs -1 etc) and
  caching instead of many.

- *(deviceauth)* Used inventory statistics as current limit usage
([MEN-9470](https://northerntech.atlassian.net/browse/MEN-9470)) ([07342b3](https://github.com/mendersoftware/mender-server-enterprise/commit/07342b38fb612f9ed52806c8acfd08eedb42d23e))  by @frodeha





  Rely on the inventory statistics provided by inventory over the
  current_usage of the local limit (which isn't reliably set) when
  validating if a limit can be decreased (e.g to make sure the limit can't
  be set below the current number of accepted devices).

- *(deviceauth)* Restrict deviceconnect device endpoints to troubleshoot add-on
 ([895049f](https://github.com/mendersoftware/mender-server-enterprise/commit/895049f3346df0936dd7428cafce8e7ecf6b26c2))  by @bahaa-ghazal



- *(deviceconnect)* Connection status race condition on disconnect
 ([f819f9e](https://github.com/mendersoftware/mender-server-enterprise/commit/f819f9ed54f59ed220c0168fce4d673f3d1ab8b7))  by @alfrunes





  When a mender-connect agent disconnects, the status is not always
  updated as the context is cancelled independently from a separate go
  routine leading to a race condition. This commit changes the database
  update to the main go routine and ensures the operation is not cancelled
  by external events.

- *(gui)* Soften warning about sharing tenant token
([ME-620](https://northerntech.atlassian.net/browse/ME-620)) ([d143cb9](https://github.com/mendersoftware/mender-server-enterprise/commit/d143cb986f37ba29372ad38153559e44d91ec2fa))  by @nickanderson





  Update the warning message to accurately reflect the risk of unauthorized device authorization requests instead of comparing the token to a password.

- *(gui)* Removed react-ga workaround to allow re-enabling ga tracking
 ([16b3626](https://github.com/mendersoftware/mender-server-enterprise/commit/16b3626048bcd3db14a403a948150076bc5dbbb1))  by @mzedel



- *(gui)* Ensured table column changes are consistently applied for all rows if they are set
 ([872e6ba](https://github.com/mendersoftware/mender-server-enterprise/commit/872e6ba056d5ce35051c34ad5263fa172f27eebe))  by @mzedel



- *(gui)* Fixed an issue that prevented changing the device identity attribute on the device list
 ([dd534aa](https://github.com/mendersoftware/mender-server-enterprise/commit/dd534aa4b4beca19c1d5e52535fca95131be0349))  by @mzedel



- *(gui)* Aligned the deployment status dark mode background color
 ([f341bb3](https://github.com/mendersoftware/mender-server-enterprise/commit/f341bb3b41fca533303be6bd5bb97a9eb505261d))  by @mineralsfree



- *(gui)* Restored onchange password strength indication
 ([6197b33](https://github.com/mendersoftware/mender-server-enterprise/commit/6197b33fa1fcf354a6751b6751743359cb571470))  by @mzedel



- *(inventory)* Properly sanitize device attribute
 ([ef55aa4](https://github.com/mendersoftware/mender-server-enterprise/commit/ef55aa4a487e555c513ffd4b30596ea1eaf968df))  by @alfrunes




  Prevent devices to assign scope and make timestamp value read-only.

- *(pkg)* Used http as default scheme in openapi client configs
 ([3f2b54a](https://github.com/mendersoftware/mender-server-enterprise/commit/3f2b54a5739e506b474c7a1310dd6f6f721ded95))  by @frodeha




- *(tenantadm)* Adjusted tenantadm to work with new limits format
([MEN-9470](https://northerntech.atlassian.net/browse/MEN-9470)) ([cd8a0f6](https://github.com/mendersoftware/mender-server-enterprise/commit/cd8a0f6f00d7239002d7b3535f8ecb90cdc5f014))  by @frodeha




- *(tenantadm)* Limit organization name length to 256 char
([MEN-9423](https://northerntech.atlassian.net/browse/MEN-9423)) ([f0f5197](https://github.com/mendersoftware/mender-server-enterprise/commit/f0f519700e932605f249bcfc6c31e52a59254ee6))  by @bahaa-ghazal




- *(useradm)* Fix CountUsers method after moving other parts to mongo driver v2
([MEN-9593](https://northerntech.atlassian.net/browse/MEN-9593)) ([b8fb816](https://github.com/mendersoftware/mender-server-enterprise/commit/b8fb816de8d682a1fcab315e29a820cf65d15ca2))  by @kjaskiewiczz



  With this commit we are using mongo driver v2 in
  the datastore_mongo_enterprise_stats.go too.
  Otherwise the method doesnt work at all.
  
  MEN-9593
  Signed-off-by: Krzysztof Jaskiewicz <krzysztof.jaskiewicz@northern.tech>

- *(useradm)* Limit email and password length to 256 char
([MEN-9423](https://northerntech.atlassian.net/browse/MEN-9423)) ([34e6104](https://github.com/mendersoftware/mender-server-enterprise/commit/34e61042ffdce77954664788401d5c61a295827e))  by @bahaa-ghazal




- *(useradm)* Check HTTP method when evaluating access rules
 ([1f0e7d9](https://github.com/mendersoftware/mender-server-enterprise/commit/1f0e7d90f3e70256e3859909d4cf8dea2209be32))  by @bahaa-ghazal



- Propagate device with proper tier
([MEN-9594](https://northerntech.atlassian.net/browse/MEN-9594)) ([d2e59b5](https://github.com/mendersoftware/mender-server-enterprise/commit/d2e59b5ffe19e67ff4abe466cd642ef801c3d1fb))  by @kjaskiewiczz



  MEN-9594
  Signed-off-by: Krzysztof Jaskiewicz <krzysztof.jaskiewicz@northern.tech>




### Documentation


- *(deployments)* Added OAS spec for new API to upload manifest
 ([7f5d5ef](https://github.com/mendersoftware/mender-server-enterprise/commit/7f5d5ef7759e85e1dbdcf984875a9107fbd5b389))  by @alfrunes



- *(deployments)* Added OAS for new read Manifest alpha endpoints
 ([e6f6960](https://github.com/mendersoftware/mender-server-enterprise/commit/e6f69608fafff245c0c2be429982e8d12cf97b94))  by @frodeha



- *(deployments)* Added 402 as response to manifest endpoints
 ([34b073c](https://github.com/mendersoftware/mender-server-enterprise/commit/34b073cb0a6074f489c7e4fb744eec607ed2f145))  by @frodeha




- *(deployments)* Added x-mender-plan to manifest alpha endpoints
 ([44ec3b4](https://github.com/mendersoftware/mender-server-enterprise/commit/44ec3b4fa1e101f79bdbb22aca131d27e5870253))  by @frodeha




- *(deployments)* Added description of tag filtering in releases endpoint
 ([e6d3b18](https://github.com/mendersoftware/mender-server-enterprise/commit/e6d3b181243462166e7b646c507a1f1d38ce0e83))  by @frodeha




- *(deviceconfig)* Add configure add-on tag to endpoints
([QA-1588](https://northerntech.atlassian.net/browse/QA-1588)) ([2c2ec73](https://github.com/mendersoftware/mender-server-enterprise/commit/2c2ec73ab1655b8f8417608c62bd5c229a9d0cde))  by @bahaa-ghazal




- *(deviceconnect)* Add troubleshoot add-on tag to endpoints
([QA-1588](https://northerntech.atlassian.net/browse/QA-1588)) ([c019b44](https://github.com/mendersoftware/mender-server-enterprise/commit/c019b44a58fef1c04144eefee3c146fc6431deed))  by @bahaa-ghazal




- *(devicemonitor)* Add monitor add-on and plan tags to endpoints
([QA-1588](https://northerntech.atlassian.net/browse/QA-1588)) ([0a7102b](https://github.com/mendersoftware/mender-server-enterprise/commit/0a7102b4e40b0f0e85ec745879557cbe2bbcadff))  by @bahaa-ghazal




- *(inventory)* Consolidate device attribute definitions
 ([144a914](https://github.com/mendersoftware/mender-server-enterprise/commit/144a914e0c24fbe093665c6b1a7fb6f127d3c869))  by @alfrunes



- *(tenantadm)* Add new endpoint for obtaining tenant information
([MEN-5248](https://northerntech.atlassian.net/browse/MEN-5248)) ([90e7a30](https://github.com/mendersoftware/mender-server-enterprise/commit/90e7a30a783ba674e1c0ecbf9a793d8015946a32))  by @bahaa-ghazal





  This endpoint behaves exactly like the `/user/tenant` endpoint,
  but the `tenant_token` is omitted from the response for security reasons.

- *(useradm)* Align POST `/users` documentation with implementation
 ([13a3e43](https://github.com/mendersoftware/mender-server-enterprise/commit/13a3e434d48ffdea457ec0f9ba60381983f1e059))  by @bahaa-ghazal



- *(useradm)* Add plan tag to endpoints
([QA-1588](https://northerntech.atlassian.net/browse/QA-1588)) ([1e98bf7](https://github.com/mendersoftware/mender-server-enterprise/commit/1e98bf721323320120a61431962d80dbb5b94b25))  by @bahaa-ghazal




- *(workflows)* Fix incorrectly documented workflows schemas
 ([7bb2740](https://github.com/mendersoftware/mender-server-enterprise/commit/7bb2740a114cf6292d82ccb93df3f941be8e2976))  by @alfrunes



- Replaced invalid openapi formats
 ([9b3c81b](https://github.com/mendersoftware/mender-server-enterprise/commit/9b3c81b52bc843020d2685500dc65c25fdd06a5f))  by @mineralsfree






### Features


- *(deployments)* Prevent uploading manifests to artifacts API
([MEN-9435](https://northerntech.atlassian.net/browse/MEN-9435)) ([2bb4778](https://github.com/mendersoftware/mender-server-enterprise/commit/2bb4778e55dec3b2b64a6f8be38839a0a4f1ced2))  by @alfrunes





  If manifests feature flag is enabled (`orchestrator_manifests.enabled`)
  the regular artifact upload endpoint prevents uploading
  `mender-orchestrator-manifest` module artifact types.

- *(deployments)* New API for uploading orchestrator manifests
([MEN-9408](https://northerntech.atlassian.net/browse/MEN-9408)) ([07377de](https://github.com/mendersoftware/mender-server-enterprise/commit/07377de9e76b996986bd894c1161e084049b49ce))  by @alfrunes





  Available when the `orchestrator_manifests.enabled` feature flag is set.

- *(deployments)* Added alpha endpoint for listing manifests
([MEN-9409](https://northerntech.atlassian.net/browse/MEN-9409)) ([a3cef6e](https://github.com/mendersoftware/mender-server-enterprise/commit/a3cef6e894fe94797e7c185cb26a4916e06b17ba))  by @frodeha




- *(deployments)* Added get manifest alpha endpoint
([MEN-9410](https://northerntech.atlassian.net/browse/MEN-9410)) ([375b60d](https://github.com/mendersoftware/mender-server-enterprise/commit/375b60d4d9a3822500811f560232347869780cf8))  by @frodeha




- *(deployments)* Added enterprise requirement on manifest routes
 ([39cf5bc](https://github.com/mendersoftware/mender-server-enterprise/commit/39cf5bcd0dac78a8b19582cabf799c14f347e57e))  by @frodeha




- *(gui)* Added generic contentsection component based on devicedatacollapse
([MEN-9302](https://northerntech.atlassian.net/browse/MEN-9302)) ([a5f1635](https://github.com/mendersoftware/mender-server-enterprise/commit/a5f163555561a7da82def7aec59d6322fe1a6255))  by @mzedel




- *(gui)* Added possibility to interact w/ the gui w/o a running backend
 ([21b26f8](https://github.com/mendersoftware/mender-server-enterprise/commit/21b26f88018e01955cfc66a984b3e36db35ebc5e))  by @mzedel




  - this relies on the mockdata defined in nt-gui/testing + the msw handlers from there

- *(gui)* Added manifest upload tip
 ([6e894b6](https://github.com/mendersoftware/mender-server-enterprise/commit/6e894b6af7619d11ddf0ad0e38992dcb6ec937f8))  by @mzedel



- *(gui)* Added manifests list & filters components
 ([db7e44d](https://github.com/mendersoftware/mender-server-enterprise/commit/db7e44d17f47cfe0f06fb3993e8febabdcfc013d))  by @mzedel



- *(gui)* Added manifest quick actions component
 ([be70703](https://github.com/mendersoftware/mender-server-enterprise/commit/be70703357db19d35eddb3439c52542530f65f5b))  by @mzedel



- *(gui)* Added view to show details of software manifests
 ([a4dd767](https://github.com/mendersoftware/mender-server-enterprise/commit/a4dd767a42e776384e1d9768aa0a8c6a35e99988))  by @mzedel



- *(gui)* Added quick actions relevant when inspecting a single manifest
 ([f276a24](https://github.com/mendersoftware/mender-server-enterprise/commit/f276a24943c0bc2425f457bf0debed7347965ddb))  by @mzedel



- *(gui)* Added NumberField from MUI documentation
([MEN-9138](https://northerntech.atlassian.net/browse/MEN-9138)) ([25b2a9d](https://github.com/mendersoftware/mender-server-enterprise/commit/25b2a9d4da78385709a8d27c4b7a14a07a8b3177))  by @mineralsfree




- *(pkg)* Shared default openapi client configuration
 ([25e6a65](https://github.com/mendersoftware/mender-server-enterprise/commit/25e6a653170daa7c8f196144791249f3f7b86e8d))  by @frodeha





  Added a way to create shared default client configurations for use
  when instantiating new openapi clients. The goal is to standardize
  as much as possible and reduce copy/pasting.
  
  I also made this shared default client configuration able to forward
  the requestID from one service to another transparently. This is not
  being forwarded currently which breaks distributed tracing.

- *(tenantadm)* Add endpoint for fetching current user tenant
([MEN-5248](https://northerntech.atlassian.net/browse/MEN-5248)) ([3e1e043](https://github.com/mendersoftware/mender-server-enterprise/commit/3e1e0439cb50c07cec3d542f2a7365a2c33cff85))  by @bahaa-ghazal




- *(useradm)* Notify user when assigned to tenant
([MEN-8967](https://northerntech.atlassian.net/browse/MEN-8967)) ([c5603fa](https://github.com/mendersoftware/mender-server-enterprise/commit/c5603fad250f4c2e908d5ec1e2c6f340a8367db3))  by @bahaa-ghazal




- *(useradm)* Cli to sync users with hubspot
([MEN-8861](https://northerntech.atlassian.net/browse/MEN-8861)) ([ba150d0](https://github.com/mendersoftware/mender-server-enterprise/commit/ba150d03f19e1b764d13f400ef4968222ac48b0b))  by @merlin-northern






- *(useradm)* Notify new users created by admins
([MEN-8967](https://northerntech.atlassian.net/browse/MEN-8967)) ([b96206b](https://github.com/mendersoftware/mender-server-enterprise/commit/b96206bdfda938493067917df4051eda70949f59))  by @bahaa-ghazal




- *(useradm)* Redirect to the new landing page for OAuth2 provider assign
([MEN-8743](https://northerntech.atlassian.net/browse/MEN-8743)) ([7861ae7](https://github.com/mendersoftware/mender-server-enterprise/commit/7861ae72a5e1af890d8802ea8826519a536d5550))  by @merlin-northern






- *(workflows)* Create workflow for sending email on user tenant assignment
([MEN-8967](https://northerntech.atlassian.net/browse/MEN-8967)) ([4b90d36](https://github.com/mendersoftware/mender-server-enterprise/commit/4b90d36b1da10e0c268d958754d4be9fee132135))  by @bahaa-ghazal




- New redis URL parameter `cluster` to enable cluster mode
 ([09c4a30](https://github.com/mendersoftware/mender-server-enterprise/commit/09c4a3051705136f6c2819fb6c1aeb0e93466a67))  by @alfrunes




  The parameter has the same effect as specifying multiple addresses and
  enables Redis cluster mode.
- Redis cluster max_retries uses hook that handles IP changes
([MEN-9371](https://northerntech.atlassian.net/browse/MEN-9371)) ([2388853](https://github.com/mendersoftware/mender-server-enterprise/commit/23888532ce13c45b90581628e91ee5c5a193d6c3))  by @alfrunes





  The redis URL parameter `max_retries` no longer use different default
  than ordinary client options which has default of 3.
  The `max_retries` also uses a hook that better handles nodes being
  assigned new IP addresses, for example if hosted as Kubernetes
  statefulset.




### Refactor


- *(auditlogs)* Used generated devauth client directly
 ([15c3715](https://github.com/mendersoftware/mender-server-enterprise/commit/15c371584a3283936226d395346d27686d275aee))  by @frodeha




- *(auditlogs)* Used generated useradm client directly
 ([403bb11](https://github.com/mendersoftware/mender-server-enterprise/commit/403bb117d95d8e87a200f192ac8f44142962341d))  by @frodeha




- *(auditlogs)* Deleted client shims
 ([f77334c](https://github.com/mendersoftware/mender-server-enterprise/commit/f77334c305098bb0ce7d1174c396f93d23156379))  by @frodeha




- *(deployments)* Split artifact parsing to separate func
 ([28db280](https://github.com/mendersoftware/mender-server-enterprise/commit/28db280cab4d8a9ad86368c6b6c3317df9bfa844))  by @alfrunes




  To separate the artifact reader to allow custom artifact reader
  for manifest validation.

- *(deployments)* Better default sort direction releases and images
([MEN-9409](https://northerntech.atlassian.net/browse/MEN-9409)) ([e0f6a98](https://github.com/mendersoftware/mender-server-enterprise/commit/e0f6a98c672396d550c519d245f1bc3bc15ca51c))  by @frodeha




- *(deployments)* Common find options for releases and manifests
([MEN-9409](https://northerntech.atlassian.net/browse/MEN-9409)) ([99b2ffc](https://github.com/mendersoftware/mender-server-enterprise/commit/99b2ffc12c96c650e007aefbfd6d904907425e92))  by @frodeha




- *(deployments)* Replace custom clients with OAS generated ones
 ([9db76ca](https://github.com/mendersoftware/mender-server-enterprise/commit/9db76ca5ed0461bb9ad5ad6d64791f89ebaa8720))  by @alfrunes



- *(deployments)* Migrate enterprise ISC to OAS generated clients
([QA-1497](https://northerntech.atlassian.net/browse/QA-1497)) ([e56d7a1](https://github.com/mendersoftware/mender-server-enterprise/commit/e56d7a1c415bd29b9b4ec4f74931d843567d3933))  by @alfrunes





  Migrated clients used for inter service communication to clients
  generated from the OpenAPI specification.

- *(deviceauth)* Change unlimited limit representation from 0 to -1
([MEN-9535](https://northerntech.atlassian.net/browse/MEN-9535)) ([73da8fe](https://github.com/mendersoftware/mender-server-enterprise/commit/73da8febfbbfa98595d388054a4efc5575ada6ff))  by @LudvigAnderson






- *(deviceauth)* Don't aggregate usage if device limit is zero
([MEN-9471](https://northerntech.atlassian.net/browse/MEN-9471)) ([d5d2fae](https://github.com/mendersoftware/mender-server-enterprise/commit/d5d2faee1714f510a793f616ab25e30d6a961bad))  by @LudvigAnderson






- *(gui)* Adopted basedrawer across applicable drawer instances
 ([72d1fa0](https://github.com/mendersoftware/mender-server-enterprise/commit/72d1fa0cb9bb65f0641eba460af864e2f67cab4b))  by @mzedel



- *(gui)* Extracted release filters into dedicated component
 ([ee53ecf](https://github.com/mendersoftware/mender-server-enterprise/commit/ee53ecf7df06e0b920b307106f94efa10cba37b8))  by @mzedel



- *(gui)* Extracted filter logic from releases component
 ([e4e9f69](https://github.com/mendersoftware/mender-server-enterprise/commit/e4e9f69b229bcb89a21af5f153592ada7b2c75aa))  by @mzedel



- *(gui)* Encapsulated release retrieval & refresh handling
 ([205edf1](https://github.com/mendersoftware/mender-server-enterprise/commit/205edf1d57286ef62607705b82ffcb0073696c3b))  by @mzedel




  - to allow clearer distinction between different software tabs & prevent data retrieval by hidden details tabs

- *(gui)* Made use of manifest components in releases view
 ([7963fbc](https://github.com/mendersoftware/mender-server-enterprise/commit/7963fbc51acafd305209357608b4c5414364b6fa))  by @mzedel



- *(gui)* Dryed up software tabs definitions
 ([f5679de](https://github.com/mendersoftware/mender-server-enterprise/commit/f5679def67f788e16cf55677586831e36d726049))  by @mzedel



- *(gui)* Removed capitalization option as it won't be applicable
 ([d48660a](https://github.com/mendersoftware/mender-server-enterprise/commit/d48660a67c95c8a4b2ab4a9d0365febc4dcd07be))  by @mzedel




  -  due to css limitations on text-transforms: the `inline` class prevents this from ever working

- *(pkg)* Move parsing of custom redis options to separate func
 ([4fab88e](https://github.com/mendersoftware/mender-server-enterprise/commit/4fab88e60fd0107ca8eecd6ed68dd8e8229526c2))  by @alfrunes



- *(tenantadm)* Use HubSpot client from common pkg
([MEN-9460](https://northerntech.atlassian.net/browse/MEN-9460)) ([1b7c081](https://github.com/mendersoftware/mender-server-enterprise/commit/1b7c081b93cde25fa436e14818d8ea5ecb42e07f))  by @kjaskiewiczz




- *(tenantadm)* Remove HubSpot client from tenantadm directory
([MEN-9460](https://northerntech.atlassian.net/browse/MEN-9460)) ([c2a3990](https://github.com/mendersoftware/mender-server-enterprise/commit/c2a3990256a02ab8f3b8abca9d6c63a475c1b926))  by @kjaskiewiczz




- *(tenantadm)* Change rate limits implementation in sync-tenants-v2 command
([MEN-9513](https://northerntech.atlassian.net/browse/MEN-9513)) ([a8b7ed6](https://github.com/mendersoftware/mender-server-enterprise/commit/a8b7ed6c5e9bb9fb261abe8e92236bdf596bf682))  by @kjaskiewiczz





  This PR replaces the `throttle-ms` option (which added a static sleep time
  to every call in the sync-tenants command) with a simple `limit` option,
  which restricts the number of tenants we synchronize with HubSpot per second.
  
  The motivation for this throttling is that for each tenant,
  we make calls to internal and external services to gather additional information.
  We want to avoid both spikes in our internal traffic and exhausting
  request quotas for external services like Stripe.







## 4.2.0-saas.6 - 2026-04-08


### Bug fixes


- *(deviceauth)* Check if new limit is less then current usage
([MEN-9481](https://northerntech.atlassian.net/browse/MEN-9481)) ([08d24e6](https://github.com/mendersoftware/mender-server-enterprise/commit/08d24e6d4576bdabb75186490743bb7164dbd377))  by @bahaa-ghazal




- *(gui)* Ensured deployment target devices are not needlessly wrapped on smaller viewports
 ([0d3cb6a](https://github.com/mendersoftware/mender-server-enterprise/commit/0d3cb6af0ede6d2e587a855738bd06b82c6dce9e))  by @mzedel



- *(gui)* Fixed an issue crashing the ui if deploying to a dynamic group targeting only a device id
 ([40f5aee](https://github.com/mendersoftware/mender-server-enterprise/commit/40f5aee1d7c90dcb9e08f350622bff67b26b3b9a))  by @mzedel



- *(gui)* Removed invitation to copy in read-only displays if we can't notify about success
 ([3c84df9](https://github.com/mendersoftware/mender-server-enterprise/commit/3c84df9ccb9c847d53c572fd579a46c1ef93e3b8))  by @mzedel



- *(gui)* Made artifact downloads less likely to trigger security incident notifications
 ([488a04b](https://github.com/mendersoftware/mender-server-enterprise/commit/488a04b2e7971953784b7c89484dc7f0e9449a0e))  by @mzedel




  - by getting their download locations only once the user clicks

- *(tenantadm)* Add missing updated_at property to tenant HubSpot object
([MEN-8832](https://northerntech.atlassian.net/browse/MEN-8832)) ([372d57a](https://github.com/mendersoftware/mender-server-enterprise/commit/372d57a4547af7cfaa76cb92f7e8fb5ab93f4a40))  by @kjaskiewiczz




- *(tenantadm)* Check if new child limit is less then current usage
([MEN-9481](https://northerntech.atlassian.net/browse/MEN-9481)) ([12da6ce](https://github.com/mendersoftware/mender-server-enterprise/commit/12da6cee1e90dadba583930d191a559323f40bfd))  by @bahaa-ghazal








### Documentation


- *(deployments)* Extended deployment creation with recurring phases
 ([d1f9d35](https://github.com/mendersoftware/mender-server-enterprise/commit/d1f9d354b4da15807b22cbbebfd834b390bce45e))  by @alfrunes




  Added recurring phases parameter to deployment object and new deployment
  parameters.

- *(deployments)* Added docs for experimental endpoints
([MEN-9400](https://northerntech.atlassian.net/browse/MEN-9400)) ([c2c16b1](https://github.com/mendersoftware/mender-server-enterprise/commit/c2c16b1e0fa8e01753235f61384601de66059af8))  by @mzedel




- *(inventory)* Added internal endpoint for getting usage statistics
 ([0954761](https://github.com/mendersoftware/mender-server-enterprise/commit/0954761c7f16d0a4cb1ae0d1a82a3b74f83b5a49))  by @alfrunes







### Features


- *(deployments)* New rollout strategy `uniform_phases`
 ([ab691bb](https://github.com/mendersoftware/mender-server-enterprise/commit/ab691bb05d22114f8bb7dd547edeeeb14f47b003))  by @alfrunes




  Extended the deployments API with `uniform_phases` rollout strategy for
  deploying releases. Uniform phases are defined by number of devices per
  phase, time interval between consecutive phases and an optional start
  timestamp for the first phase.

- *(gui)* Let release & related software focused content appear as software in navigation & links
([MEN-9413](https://northerntech.atlassian.net/browse/MEN-9413)) ([b4d293d](https://github.com/mendersoftware/mender-server-enterprise/commit/b4d293dc6f93d4ab7f8dff68d6fb85a49b0ae485))  by @mzedel




- *(tenantadm)* Add "NT Last Sync" property to HubSpot tenant object schema
([MEN-8832](https://northerntech.atlassian.net/browse/MEN-8832)) ([b891a3e](https://github.com/mendersoftware/mender-server-enterprise/commit/b891a3e43d367de34aa804b2ca79857a1a36ab3f))  by @kjaskiewiczz




- *(tenantadm)* Extend command for synchronizing tenant
([MEN-8832](https://northerntech.atlassian.net/browse/MEN-8832)) ([e16113f](https://github.com/mendersoftware/mender-server-enterprise/commit/e16113f2117cd4b6be30b0e3494c9f84e5c1a17c))  by @kjaskiewiczz





  With this commit, the command is actually able to synchronize tenants.
  Tenant synchronization is done in batches and the batch size is dictated
  by maximum batch size supported by HubSpot.

- *(tenantadm)* Extend command for synchronizing tenants with HubSpot
([MEN-9463](https://northerntech.atlassian.net/browse/MEN-9463)) ([059a2d3](https://github.com/mendersoftware/mender-server-enterprise/commit/059a2d38e1eef7dcb38fae23ae4e43b3abbf8559))  by @kjaskiewiczz





  Add information about first deployment creation date.





### Refactor


- *(gui)* Cleanup after device id selection dialog extraction & design alignment
 ([1620eea](https://github.com/mendersoftware/mender-server-enterprise/commit/1620eea43e4ed82a81e75eb03b1c2532529c2193))  by @mzedel



- *(tenantadm)* Consolidate HubspotObject with upsert input
([MEN-8832](https://northerntech.atlassian.net/browse/MEN-8832)) ([f9b9338](https://github.com/mendersoftware/mender-server-enterprise/commit/f9b9338676805b5ce797ebae3f9d172c07364251))  by @kjaskiewiczz










## 4.2.0-saas.5 - 2026-03-23


### Bug fixes


- *(gui)* Made ai analysis depend on ai feature activation
 ([ec3fdb8](https://github.com/mendersoftware/mender-server-enterprise/commit/ec3fdb826feeb4962c2f27ae2abae13aa05d1c67))  by @mzedel



- *(inventory)* Correcting order of operations in aggregation in SearchDevices
([ME-642](https://northerntech.atlassian.net/browse/ME-642)) ([e5459d4](https://github.com/mendersoftware/mender-server-enterprise/commit/e5459d4c730662e2dcfbd476c204a56f461f3a44))  by @merlin-northern










### Features


- *(gui)* Adjusted the max limit in group and role definition
([MEN-9223](https://northerntech.atlassian.net/browse/MEN-9223)) ([272b13e](https://github.com/mendersoftware/mender-server-enterprise/commit/272b13eab729b7db2d00a69f05a77ac6a9c5c259))  by @mineralsfree








### Refactor


- *(deployments)* Move common part of releases to new model
 ([31e5ece](https://github.com/mendersoftware/mender-server-enterprise/commit/31e5ecec03e0c34d5ad45591b4dec17697cfeb9d))  by @alfrunes




  To make room for ReleaseManifests (enterprise) sharing most of the same structure.

- *(useradm)* Remove sso/login parameters from POST /api/management/v1/useradm/users
([MEN-9295](https://northerntech.atlassian.net/browse/MEN-9295)) ([c72bd1b](https://github.com/mendersoftware/mender-server-enterprise/commit/c72bd1b009c44a20d20d625463f8a90295babee9))  by @LudvigAnderson












## 4.2.0-saas.4 - 2026-03-20


### Bug fixes


- *(deployments)* Treat `artifact_too_big` as finished state
([MEN-9456](https://northerntech.atlassian.net/browse/MEN-9456)) ([460a280](https://github.com/mendersoftware/mender-server-enterprise/commit/460a2809258f21d5c8cedb2271dc8da1ef2166a5))  by @frodeha




- Deserialization of Setting preventing use of AI summary
 ([45ccf0a](https://github.com/mendersoftware/mender-server-enterprise/commit/45ccf0ac91426795ca51916f3e6642f95b308d98))  by @alfrunes




  A change in the default deserialization of bson document in the mongo v2
  driver blocks the consent check to use AI feature.




### Features


- *(tenantadm)* New command for synchronizing data with HubSpot
([MEN-8832](https://northerntech.atlassian.net/browse/MEN-8832)) ([0e6fcbe](https://github.com/mendersoftware/mender-server-enterprise/commit/0e6fcbed81751e58cc71da69829040174ad3998e))  by @kjaskiewiczz





  This commit introduces only part of the functionality of this new
  command.
  With this commit it's possible to create custom tenant object in HubSpot
  (--init flag).
  Data synchronization will be added in the next iteration.

- *(useradm)* Invalidate password reset tokens on password change
([MEN-9199](https://northerntech.atlassian.net/browse/MEN-9199)) ([e6f92ac](https://github.com/mendersoftware/mender-server-enterprise/commit/e6f92ac8a577581b1de09b06c3dde9e7ba7cd420))  by @bahaa-ghazal










## 4.2.0-saas.3 - 2026-03-17


### Bug fixes


- *(create-artifact-worker)* Hardened single file generation input validations
 ([484cc2a](https://github.com/mendersoftware/mender-server-enterprise/commit/484cc2a13ad44d93cdf0f3c2ea9155b9bac4a969))  by @mzedel




  - this should limit path traversal possibilities and reduce possibilities for malicious user inputs

- *(deployments)* Reject deployments names longer than 256 characters
([MEN-9222](https://northerntech.atlassian.net/browse/MEN-9222)) ([4983b46](https://github.com/mendersoftware/mender-server-enterprise/commit/4983b46f115a3a52b5bda1c6f9628e1826d5c603))  by @bahaa-ghazal




- *(deployments)* Nil pointer dereference getting non-existing deployment
([MEN-9429](https://northerntech.atlassian.net/browse/MEN-9429)) ([647084b](https://github.com/mendersoftware/mender-server-enterprise/commit/647084be4e3298534daba7474607347efb2ec7b6))  by @alfrunes




- *(deviceauth)* Set correct rate limits for micro devices
([MEN-9308](https://northerntech.atlassian.net/browse/MEN-9308)) ([7651ee1](https://github.com/mendersoftware/mender-server-enterprise/commit/7651ee10c656b8aed37df6c302e2029421272d59))  by @frodeha




- *(gui)* Fixed typo in integration removal confirmation
 ([a37fdd4](https://github.com/mendersoftware/mender-server-enterprise/commit/a37fdd4f2d0c5bb007f217a75885f2f2ab44e3dd))  by @mzedel



- *(gui)* Fixed an issue that could misrepresent progress in a phased deployment
 ([049aff5](https://github.com/mendersoftware/mender-server-enterprise/commit/049aff51ac7ecdc7c8ce7baa2aece7fffba7bde6))  by @mzedel



- *(gui)* Show alert if dynamic group is removed after deployment
([ME-550](https://northerntech.atlassian.net/browse/ME-550)) ([43b717e](https://github.com/mendersoftware/mender-server-enterprise/commit/43b717efe1ffeddf302d1a16fdd6bcc7ec515492))  by @mineralsfree




- *(gui)* Fixed an issue that could hinder the device config difference view if none were found
 ([36f4395](https://github.com/mendersoftware/mender-server-enterprise/commit/36f43953f9b8fc5addb3b7ac12317c304af357da))  by @mzedel



- *(gui)* Restored copying values via the copy indicator after switch to new data display
 ([c956de6](https://github.com/mendersoftware/mender-server-enterprise/commit/c956de65518a37c2b69441c4358301b78b40342c))  by @mzedel



- *(gui)* Added handling of `artifact_too_big` deployment sub-status
([MEN-9456](https://northerntech.atlassian.net/browse/MEN-9456)) ([c17104d](https://github.com/mendersoftware/mender-server-enterprise/commit/c17104dcc4bb168ea89e61ca20ab5ddf8db243d5))  by @frodeha




- *(gui)* Fixed an issue that could lead the ui to a faulty state when handling `noauth` devices
 ([0ee4eb3](https://github.com/mendersoftware/mender-server-enterprise/commit/0ee4eb30fc7b72b468677afae9e3abc2f8a66367))  by @mzedel



- *(gui)* Ensured all filtering options have a readable title
([MEN-9485](https://northerntech.atlassian.net/browse/MEN-9485)) ([c40e077](https://github.com/mendersoftware/mender-server-enterprise/commit/c40e077abfc47857a4c62a5dd27fc728c493e16f))  by @mzedel




- *(inventory)* Reject group names longer than 256 characters
([MEN-9222](https://northerntech.atlassian.net/browse/MEN-9222)) ([3fa1208](https://github.com/mendersoftware/mender-server-enterprise/commit/3fa1208839159f3f755d5f9ce37bdbf106bc4187))  by @bahaa-ghazal




- *(tenantadm)* Do not clear authentication tokens when adding disabled addon to tenant
([MEN-9428](https://northerntech.atlassian.net/browse/MEN-9428)) ([a7c7701](https://github.com/mendersoftware/mender-server-enterprise/commit/a7c77012e9802bb0db92e6f7662431d82356617f))  by @kjaskiewiczz




- *(useradm)* Reject role names longer than 256 characters
([MEN-9222](https://northerntech.atlassian.net/browse/MEN-9222)) ([db912de](https://github.com/mendersoftware/mender-server-enterprise/commit/db912de5abc8599e0ceabc8c45a27a8b7c4ded58))  by @bahaa-ghazal




- *(workflows)* Set correct verification request expiration in e-mail
([MEN-9259](https://northerntech.atlassian.net/browse/MEN-9259)) ([4193f59](https://github.com/mendersoftware/mender-server-enterprise/commit/4193f59fe5637b4a461cfbde418dbec6e4b43ef8))  by @frodeha




- Unmarshal `interface{}` as bson.M using v2 mongo-driver
([MEN-9419](https://northerntech.atlassian.net/browse/MEN-9419)) ([dff3e6a](https://github.com/mendersoftware/mender-server-enterprise/commit/dff3e6a6ba26dfcd75cb3dcd6312fb2be25f592b))  by @bahaa-ghazal



- Return standard tier form inventory and device-auth if unset (#1022)
([MEN-9365](https://northerntech.atlassian.net/browse/MEN-9365)) ([fa817b2](https://github.com/mendersoftware/mender-server-enterprise/commit/fa817b2f49dd088b102b32619113199757e25aa3))  by @merlin-northern in #1022









### Documentation


- *(useradm)* Updated email verification API docs
([MEN-9259](https://northerntech.atlassian.net/browse/MEN-9259)) ([a5e206b](https://github.com/mendersoftware/mender-server-enterprise/commit/a5e206bd9cd73d25a4dd9e330aaaf990d3738fb0))  by @frodeha




- Added explanation for e2e test usage
 ([3990a32](https://github.com/mendersoftware/mender-server-enterprise/commit/3990a323aadcd67f74df6673663f2bc2bf48c5f1))  by @mzedel






### Features


- *(deployments)* Aligned deployment filtering w/ ux expectations
([MEN-9407](https://northerntech.atlassian.net/browse/MEN-9407)) ([40465c8](https://github.com/mendersoftware/mender-server-enterprise/commit/40465c8ea836e4594ace29eda5d7ab61eacbb0bb))  by @mzedel




- *(deviceauth)* Support for tiers in preauthorization
([MEN-9457](https://northerntech.atlassian.net/browse/MEN-9457)) ([3e14ea2](https://github.com/mendersoftware/mender-server-enterprise/commit/3e14ea251ef175e059badbd4b7a800b792489385))  by @merlin-northern






- *(gui)* Enabled dark mode support for saml + other editors
([MEN-9060](https://northerntech.atlassian.net/browse/MEN-9060)) ([5abebe7](https://github.com/mendersoftware/mender-server-enterprise/commit/5abebe71a900be81377ab680b3411b5c8ab7a938))  by @mzedel





  - made use of common editor wrapper to do so

- *(gui)* Added time limited announcement for ai analysis feature to let more users benefit from it
 ([a6ee288](https://github.com/mendersoftware/mender-server-enterprise/commit/a6ee28892f6e4897e88da68d449e610ddf86f1d7))  by @mzedel



- *(gui)* Added tier support to sp tenant dashboard
([MEN-8880](https://northerntech.atlassian.net/browse/MEN-8880)) ([ba67fb3](https://github.com/mendersoftware/mender-server-enterprise/commit/ba67fb3d8bed4bb50e3179795c5c097bc1561b5c))  by @mineralsfree




- *(gui)* Added tier support to child tenant creation form
([MEN-8880](https://northerntech.atlassian.net/browse/MEN-8880)) ([88e7d08](https://github.com/mendersoftware/mender-server-enterprise/commit/88e7d08d37d5be0e40e594339719a95cd323503b))  by @mineralsfree




- *(gui)* Added tier support to child view and edit drawer
([MEN-8880](https://northerntech.atlassian.net/browse/MEN-8880)) ([ab45bda](https://github.com/mendersoftware/mender-server-enterprise/commit/ab45bdac0b80d6e515d61a661f40fb34efc75fbe))  by @mineralsfree




- *(gui)* Added sp tenant support request form
([MEN-8880](https://northerntech.atlassian.net/browse/MEN-8880)) ([02bbdd6](https://github.com/mendersoftware/mender-server-enterprise/commit/02bbdd633065edeb1cd14b403763d8aaba5fcc9c))  by @mineralsfree




- *(gui)* Added new Activate page for email verification
([MEN-9260](https://northerntech.atlassian.net/browse/MEN-9260)) ([7ab20bc](https://github.com/mendersoftware/mender-server-enterprise/commit/7ab20bc103f47bd6f61214ce105c63560035d648))  by @mineralsfree




- *(gui)* Added tiers to device auth set list item and identity
([ME-634](https://northerntech.atlassian.net/browse/ME-634)) ([eea0409](https://github.com/mendersoftware/mender-server-enterprise/commit/eea0409573c465317595e10bc08b6ecac4e95d4f))  by @mineralsfree




- *(gui)* Extract SettingsItem as reusable common-ui component
([MEN-9311](https://northerntech.atlassian.net/browse/MEN-9311)) ([485375b](https://github.com/mendersoftware/mender-server-enterprise/commit/485375b2ed596706ef36bce584bd6cee5b7c5102))  by @mzedel




- *(gui)* Added filtering by tiers on device list page
([MEN-9465](https://northerntech.atlassian.net/browse/MEN-9465)) ([8bcf567](https://github.com/mendersoftware/mender-server-enterprise/commit/8bcf567452619563e736152b68448fcfd6c25e6e))  by @mineralsfree




- *(gui)* Let device/release selections no longer persist when navigating to a new page
 ([3d0eec4](https://github.com/mendersoftware/mender-server-enterprise/commit/3d0eec44e49b6d07c4b5f6ba5e491df350b95658))  by @mzedel



- *(gui)* Add DocsTextLink variant for inline documentation links
([MEN-9321](https://northerntech.atlassian.net/browse/MEN-9321)) ([5441af8](https://github.com/mendersoftware/mender-server-enterprise/commit/5441af8acb765ae1347d5a12b4cf9c880adf1621))  by @mzedel




- *(useradm)* Added handling of expired verification links
([MEN-9259](https://northerntech.atlassian.net/browse/MEN-9259)) ([8ccf0db](https://github.com/mendersoftware/mender-server-enterprise/commit/8ccf0db4e1ab32f458b3dbdae77c14f4734423c2))  by @frodeha




- *(useradm)* Invalidate password reset tokens on email change
([MEN-9198](https://northerntech.atlassian.net/browse/MEN-9198)) ([4cb7677](https://github.com/mendersoftware/mender-server-enterprise/commit/4cb7677aeee6c0d49182b4f494425557e5ea7a51))  by @bahaa-ghazal




- *(useradm)* Add configuration parameters for HubSpot integration
([MEN-9459](https://northerntech.atlassian.net/browse/MEN-9459)) ([79967cf](https://github.com/mendersoftware/mender-server-enterprise/commit/79967cf4d8b920203c5862ad26fd0edae51b1931))  by @kjaskiewiczz








### Refactor


- Migrate mongo-driver to v2
([QA-1448](https://northerntech.atlassian.net/browse/QA-1448)) ([73425d5](https://github.com/mendersoftware/mender-server-enterprise/commit/73425d59fa6268842be7d6cbeb40e6f100cc62c8))  by @bahaa-ghazal




- *(deviceauth)* Remove dead code
 ([bbdcc10](https://github.com/mendersoftware/mender-server-enterprise/commit/bbdcc10144a3b9dec4ac58f83a5dd6c2ae641ef7))  by @kjaskiewiczz



- *(gui)* Unified deployment progress rendering
 ([0f2507a](https://github.com/mendersoftware/mender-server-enterprise/commit/0f2507a5e04f0fcb5e198c46273d1c1800601d87))  by @mzedel




  - single entrypoint component to decide on what to render based on deployment state according to a passed variant
  - isolated synchronized deployments sections
  - increased separation between presentation & phase data deduction to try and improve clarity
  - expanded type coverage

- *(gui)* Made deployments list rendering handle screen sizes by itself
 ([f39e0ae](https://github.com/mendersoftware/mender-server-enterprise/commit/f39e0ae052babf62a90379a49b74318e05a342fd))  by @mzedel




  - increased reliance on deployment progress renderer
  - ensured intended column alignment for date/ time columns





### Security


- *(gui)* Updated backend interaction package
 ([ebf7509](https://github.com/mendersoftware/mender-server-enterprise/commit/ebf75098bb0d18ff2e1947e644e52b3957806a87))  by @mzedel




  - to bring in new deployment substate, device & release selection behaviour changes, adjusted security nudging







## 4.2.0-saas.2 - 2026-02-19


### Bug fixes


- *(auditlogs)* Filtering logs by actor email use correct email validation
 ([85cf5e4](https://github.com/mendersoftware/mender-server-enterprise/commit/85cf5e4fe93ea72fbf38791f56ac4dfa2d3f074d))  by @alfrunes



- *(deployments)* Aligned empty delta jobs list representation w/ documentation
 ([70069b4](https://github.com/mendersoftware/mender-server-enterprise/commit/70069b4c58f7b7d619ee018c5ac855a61df7f12b))  by @mzedel




  - the returned `null` is another spec alignment issue the ui ran into

- *(deviceauth)* Replace unique authset index to include tier
([MEN-9039](https://northerntech.atlassian.net/browse/MEN-9039)) ([243c17b](https://github.com/mendersoftware/mender-server-enterprise/commit/243c17bf453851784e1073a41303ee2e18f880f4))  by @alfrunes





  Loosen the uniqueness constraint to allow multiple auth sets across
  different tiers to allow switching tiers if limits permits.

- *(deviceauth)* Prevent SP/child tenants from having unlimited limits
([MEN-9273](https://northerntech.atlassian.net/browse/MEN-9273)) ([d5fbdeb](https://github.com/mendersoftware/mender-server-enterprise/commit/d5fbdeb4ac9d35d969b21cbbe640f9dc3df3f1f1))  by @bahaa-ghazal




- *(generate-delta-worker)* Use absolute path for binaries
 ([9e60b37](https://github.com/mendersoftware/mender-server-enterprise/commit/9e60b37d8e5ae6953b4da8f0decb56d3de4dbdf3))  by @bahaa-ghazal



- *(generate-delta-worker)* Add delta image ID when reporting success
([MEN-9168](https://northerntech.atlassian.net/browse/MEN-9168)) ([5ce1a29](https://github.com/mendersoftware/mender-server-enterprise/commit/5ce1a29f115859cfc5fb0dad655d92258b77bc9e))  by @alfrunes




- *(gui)* Fixed an issue that could hinder re-opening a troubleshoot connection to a device
 ([79a4cbf](https://github.com/mendersoftware/mender-server-enterprise/commit/79a4cbf2b705096388d93e108abfadc6d1cd08f0))  by @mzedel



- *(gui)* Prevented key column in short data displays from breaking views by overflowing
 ([cefdc48](https://github.com/mendersoftware/mender-server-enterprise/commit/cefdc480296cb2c21ffed9ac163f2f08b3b1652b))  by @mzedel



- *(gui)* Made internal browser navigation explicit to prevent disagreements in app & url state
 ([41519b2](https://github.com/mendersoftware/mender-server-enterprise/commit/41519b293266b6edc20df0463ffdc4eb2261dde8))  by @mzedel



- *(gui)* Aligned link behaviour in deployment report
 ([19fe6e5](https://github.com/mendersoftware/mender-server-enterprise/commit/19fe6e5b233b7be5cb7d1e393ed5342eb6e67165))  by @mzedel



- *(gui)* Fixed an issue that would prevent importing config data into a partly populated editor
([ME-614](https://northerntech.atlassian.net/browse/ME-614)) ([c14d30a](https://github.com/mendersoftware/mender-server-enterprise/commit/c14d30af802aeb5bd441605897f0695a7816fd06))  by @mzedel




- *(gui)* Removed the automatic pie-chart height adjustment
 ([7ca60aa](https://github.com/mendersoftware/mender-server-enterprise/commit/7ca60aa5baaba19dd99b4d7ecf5f0eeaa24e885c))  by @mineralsfree



- *(gui)* Fixed the email verification flow for oauth2 users
 ([df03220](https://github.com/mendersoftware/mender-server-enterprise/commit/df032208bb6a7e82a576fefaf6a92fb90e985cc9))  by @mineralsfree



- *(gui)* Fixed an issue that prevented seeing devices linked to if multiple devices were targeted
 ([fb41635](https://github.com/mendersoftware/mender-server-enterprise/commit/fb4163513015daf69bad33a946c578bcf6e605c6))  by @mzedel



- *(gui)* Fixed an issue that might confuse tenants without a device limit by showing a limit
 ([c866e3a](https://github.com/mendersoftware/mender-server-enterprise/commit/c866e3a5204690f570dda3a92722089369bb577d))  by @mzedel



- *(gui)* Removed the state from billing address form
([MEN-9275](https://northerntech.atlassian.net/browse/MEN-9275)) ([a1b53aa](https://github.com/mendersoftware/mender-server-enterprise/commit/a1b53aae7f3890ffb2da55833b9957d8814a3779))  by @mineralsfree




- *(gui)* Subscription drawer fixes
([MEN-9275](https://northerntech.atlassian.net/browse/MEN-9275)) ([c30f731](https://github.com/mendersoftware/mender-server-enterprise/commit/c30f731f07a288acdda46177e1b3d798d9ab44cb))  by @mineralsfree




- *(gui)* Fixed the artifact select changing height issue
([MEN-9248](https://northerntech.atlassian.net/browse/MEN-9248)) ([fcea9b7](https://github.com/mendersoftware/mender-server-enterprise/commit/fcea9b738398650f17beb7e1169b320b5a6aa804))  by @mineralsfree




- *(gui)* Added placeholder when 0 releases found in filter
([MEN-9248](https://northerntech.atlassian.net/browse/MEN-9248)) ([f0916d0](https://github.com/mendersoftware/mender-server-enterprise/commit/f0916d0e6169c8de33c5bc20c460d08dfae28b4c))  by @mineralsfree




- *(gui)* Added selected state for release in the filter
([MEN-9248](https://northerntech.atlassian.net/browse/MEN-9248)) ([1a9aff1](https://github.com/mendersoftware/mender-server-enterprise/commit/1a9aff1da76dca821aba0015acd4b1fa4e7120f8))  by @mineralsfree





  + display release note instead of 1st artifact description

- *(gui)* Let subscription page handle products retrieval to prevent erroneous on-prem requests
 ([0239183](https://github.com/mendersoftware/mender-server-enterprise/commit/02391837ec03c9e13515eb19e5d9e6dd1466aade))  by @mzedel



- *(iot-manager)* Fix re-encrypt to encrypt ALL secrets
 ([edea736](https://github.com/mendersoftware/mender-server-enterprise/commit/edea73654f23e984e99c2ae5f9805896cf011a80))  by @alfrunes



- *(tenantadm)* Validate device tier limits when changing subscription
([MEN-9208](https://northerntech.atlassian.net/browse/MEN-9208)) ([353fb05](https://github.com/mendersoftware/mender-server-enterprise/commit/353fb0583374007ee22f7823e2f1a32209068305))  by @bahaa-ghazal




- *(tenantadm)* Set limit to 0 for unspecified tier products
 ([2047178](https://github.com/mendersoftware/mender-server-enterprise/commit/20471786ea60626c4d6a25ceba9ac1cc4ee70368))  by @bahaa-ghazal



- *(tenantadm)* Make BillingProfile.state optional
 ([0fe48cc](https://github.com/mendersoftware/mender-server-enterprise/commit/0fe48cc55ba51ecf157fa52af990a1dcba0526f9))  by @alfrunes




- *(tenantadm)* Block upgrading tenants with unlimited limits to Service Provider
([MEN-9273](https://northerntech.atlassian.net/browse/MEN-9273)) ([0114b79](https://github.com/mendersoftware/mender-server-enterprise/commit/0114b793c0b51276bb6c4156a66ebb8227f37d19))  by @bahaa-ghazal




- *(tenantadm)* Prevent assigning tenants with unlimited limts as children tenants
([MEN-9273](https://northerntech.atlassian.net/browse/MEN-9273)) ([fdc35c5](https://github.com/mendersoftware/mender-server-enterprise/commit/fdc35c5162d646e7cca67e5a2cc05cb49bb98ec5))  by @bahaa-ghazal




- *(tenantadm)* Create tenant before setting limits in deviceauth
 ([d085644](https://github.com/mendersoftware/mender-server-enterprise/commit/d08564472c8077f1cf6b3e0cf3c169bd020700de))  by @bahaa-ghazal




  This is important so deviceauth can evaluate if limits is valid

- *(tenantadm)* Set new default trial device limits
 ([ebe1212](https://github.com/mendersoftware/mender-server-enterprise/commit/ebe12125f904d37aab615a7e92c56e17050161f6))  by @frodeha





  Trial tenants are from now given a limit of:
     * 5 standard devices
     * 5 micro devices
  
  When we release support for system devices they will be given a limit of
  5 of those as well.

- *(useradm)* Internal API not deleting users with inconsistent tenant data
([MEN-9274](https://northerntech.atlassian.net/browse/MEN-9274)) ([f5c4574](https://github.com/mendersoftware/mender-server-enterprise/commit/f5c45745a2018c09295af67507ab78b6524b553d))  by @alfrunes




- *(useradm)* Mask private fields from user creation endpoint
([MEN-9249](https://northerntech.atlassian.net/browse/MEN-9249)) ([9ae3ef1](https://github.com/mendersoftware/mender-server-enterprise/commit/9ae3ef1429d85fc88486825bae4da1db98f31475))  by @alfrunes





  Constraints the create user input to the properties defined in the API
  specification. Masking `login_ts`, `tfa_enabled` and `verified` from the
  user creation API endpoint.

- *(useradm)* Prevent invalid security email about disabled two-factor
([MEN-9281](https://northerntech.atlassian.net/browse/MEN-9281)) ([be114f5](https://github.com/mendersoftware/mender-server-enterprise/commit/be114f573d90645f70dff03f09ba6788e4c34722))  by @alfrunes





  When changing email address and two-factor was already disabled, do not
  send an additional security email about disabling two-factor.

- *(useradm)* Stop sending emails to all admin users when PAT changes
([MEN-9244](https://northerntech.atlassian.net/browse/MEN-9244)) ([bf887fc](https://github.com/mendersoftware/mender-server-enterprise/commit/bf887fcd1cad4c2d5877be043d9318773cbc5a16))  by @bahaa-ghazal





  Only the user who owns the PAT should receive the email.

- *(useradm)* Use "send_pat_changed_email" workflow to send emails about PAT changes
 ([8ff784f](https://github.com/mendersoftware/mender-server-enterprise/commit/8ff784fb4195ab91ebf11db2c1271f97ae838dee))  by @bahaa-ghazal



- *(useradm)* Bind oauth2 login to browser session
 ([51d5ea7](https://github.com/mendersoftware/mender-server-enterprise/commit/51d5ea70dc03bb7a991024301d9c318455df8a3e))  by @alfrunes




  Sets a session cookie when initiating the redirect to the identity
  provider and validates the session ID on return.

- *(useradm)* Use RBAC middleware with legacy API
 ([b45e011](https://github.com/mendersoftware/mender-server-enterprise/commit/b45e01154ab107acb11510962467c26a1dec4f8e))  by @kjaskiewiczz



- *(useradm)* Absolute path for created user
 ([7618cce](https://github.com/mendersoftware/mender-server-enterprise/commit/7618cceae051dd242ddea06b1ce112e9c79648a8))  by @alfrunes




  The relative location resolves to a non-existing API path.

- *(useradm)* Use base URL from configuration for OpenID callback URL
([MEN-9374](https://northerntech.atlassian.net/browse/MEN-9374)) ([3d934a3](https://github.com/mendersoftware/mender-server-enterprise/commit/3d934a3d61f4c2b315e873d44c632fb2d4f2ff57))  by @alfrunes





  Instead of parsing `X-Forwarded-Host`, use the constant base URL from
  configuration.

- *(workflows)* Restrict which binary can be executed by workers
([QA-903](https://northerntech.atlassian.net/browse/QA-903)) ([3012e6a](https://github.com/mendersoftware/mender-server-enterprise/commit/3012e6a16b8dc7da50a16ce1c87b0da4191231ca))  by @bahaa-ghazal





  This is done to satisfy gosec G204.

- *(workflows)* Update verify email template to context neutral message
([MEN-9183](https://northerntech.atlassian.net/browse/MEN-9183)) ([4ad9327](https://github.com/mendersoftware/mender-server-enterprise/commit/4ad932776ae610b42476a2633fcdaec30a0fcc32))  by @alfrunes




- *(workflows)* Re-introduce retries in workflows for setting inventory data
([MEN-9176](https://northerntech.atlassian.net/browse/MEN-9176)) ([84a19bb](https://github.com/mendersoftware/mender-server-enterprise/commit/84a19bbc4a733d153be095b4a66b3ee0b1108bc3))  by @kjaskiewiczz




- Remove the unlimited limits when testing SP and child tenants
 ([24c267a](https://github.com/mendersoftware/mender-server-enterprise/commit/24c267a1da3f624fa64a5713caf964d5e8c665db))  by @bahaa-ghazal






### Documentation


- *(deviceauth)* Updated description of unlimited limits in api docs
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([7e7dc5a](https://github.com/mendersoftware/mender-server-enterprise/commit/7e7dc5a5bfc5b52ab2d7fa83ae332b1e8a739ad8))  by @frodeha




- *(inventory)* Aligned the attribute type used by the patch endpoint
([MEN-9143](https://northerntech.atlassian.net/browse/MEN-9143)) ([29d0954](https://github.com/mendersoftware/mender-server-enterprise/commit/29d09547ee4c32e33499ec2f1872cdf376f12bf5))  by @merlin-northern






- *(tenantadm)* GET /billing/products
([MEN-8561](https://northerntech.atlassian.net/browse/MEN-8561)) ([3207f42](https://github.com/mendersoftware/mender-server-enterprise/commit/3207f428fcec4fe934d06ec04f0662489c829cc2))  by @merlin-northern






- *(tenantadm)* Clarified relationship between product references in api docs
 ([029b9ac](https://github.com/mendersoftware/mender-server-enterprise/commit/029b9ac7d2b766d09c89ed49e6bd2caea7fc3541))  by @mzedel



- *(useradm)* Fix invalid property name for EmailVerificationComplete
 ([0bd12fe](https://github.com/mendersoftware/mender-server-enterprise/commit/0bd12fe1d44cc16349dedca5cbec45f1fd91a063))  by @alfrunes



- *(workflows)* Fix wrong path for health check API
 ([ec490e3](https://github.com/mendersoftware/mender-server-enterprise/commit/ec490e334545b305059215d9f7f65c6ceb2f0c57))  by @alfrunes



- Clarify release workflow
 ([469a048](https://github.com/mendersoftware/mender-server-enterprise/commit/469a04862498a5188ada7997ae8502ae6c3fc3f3))  by @oldgiova




  And remove the checklist, which is maintained in the Jira tickets only.
- Required fix for the OpenAPI3 specs
([QA-1097](https://northerntech.atlassian.net/browse/QA-1097)) ([625964b](https://github.com/mendersoftware/mender-server-enterprise/commit/625964bd5d19e67155b27f9155659ad40890aed3))  by @merlin-northern





- /api/internal/v1/devauth/tenant/{tid}/limits does not return tenant_id
([MEN-8571](https://northerntech.atlassian.net/browse/MEN-8571)) ([452d5f0](https://github.com/mendersoftware/mender-server-enterprise/commit/452d5f0084a047d4976a4d4a486f9cf72394c251))  by @merlin-northern









### Features


- *(deployments)* New configuration: `aws.literal_bucket_uri`
 ([27ac487](https://github.com/mendersoftware/mender-server-enterprise/commit/27ac487b2b43170c70f55abe2d645f3634f04af6))  by @alfrunes




  The configuration, if set, will treat the `aws.uri` and
  `aws.external_uri` as absolute URLs to the bucket without decorating the
  host name with the bucket name and region.

- *(deviceauth)* Added migration to make unlimited limits consistent
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([0ec5e62](https://github.com/mendersoftware/mender-server-enterprise/commit/0ec5e62aeca3b3d5a83c2a25cd42694d0d20b770))  by @frodeha




- *(deviceauth)* Removed support for `0` as unlimited in max_devices
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([2467601](https://github.com/mendersoftware/mender-server-enterprise/commit/2467601ac7f65adfcbb53b689fb02360a0a29991))  by @frodeha




- *(deviceauth)* Ensured consistent handling of missing max_devices limits
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([46d7b1e](https://github.com/mendersoftware/mender-server-enterprise/commit/46d7b1e70dfd3d10c24c6a48a0a48af1e1d6fa60))  by @frodeha




- *(gui)* Ensured log analysis insights can benefit entire userbase by default
 ([54dda92](https://github.com/mendersoftware/mender-server-enterprise/commit/54dda92a14c29e1c888440af88871fc170780bd6))  by @mzedel



- *(gui)* Enabled updated theme for everyone by default
 ([5377ae1](https://github.com/mendersoftware/mender-server-enterprise/commit/5377ae18412fd40e94f9618e3f81578951286201))  by @mzedel




  - disabling is still possible via feature flag

- *(gui)* Added tier support to subscription page
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([7060a08](https://github.com/mendersoftware/mender-server-enterprise/commit/7060a084e31a9d0fdb68aa6e3047ff8fe35a89d7))  by @mineralsfree




- *(gui)* Auto-select enabled tier based on current usage
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([5ee75bd](https://github.com/mendersoftware/mender-server-enterprise/commit/5ee75bd5fab66c8a4f56a1c84c76b6724646a348))  by @mineralsfree




- *(gui)* Adjusted add-on selection input for tiers
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([c584b2e](https://github.com/mendersoftware/mender-server-enterprise/commit/c584b2e40ff54de0a4cfeb09f8fab97618c027f8))  by @mineralsfree




- *(gui)* Adjusted subscription summary for tiers supports
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([f054b5e](https://github.com/mendersoftware/mender-server-enterprise/commit/f054b5e4bd16283dba02e624d25de4aaa91edafb))  by @mineralsfree




- *(gui)* Adjusted subscription drawer for tiers supports
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([49ff2f5](https://github.com/mendersoftware/mender-server-enterprise/commit/49ff2f5a9e3b2be1fca27484af14abd4b2dfd590))  by @mineralsfree




- *(gui)* Adjusted subscription confirmation for tiers supports
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([8993b7e](https://github.com/mendersoftware/mender-server-enterprise/commit/8993b7eeb9f1d9e4dfa81d96be07defcba297387))  by @mineralsfree




- *(gui)* Adjusted billing page to support tiers
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([878518f](https://github.com/mendersoftware/mender-server-enterprise/commit/878518f103c6e6fac23a4d306be90c139823021f))  by @mineralsfree




- *(gui)* Added tiers tooltips
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([3fcdbab](https://github.com/mendersoftware/mender-server-enterprise/commit/3fcdbab516909acd1666083ddbd813fe1b58e4a6))  by @mineralsfree





  + prevent default to stop event propagation when clicked

- *(gui)* Hidden MCU in subscription via feature flag
([MEN-9205](https://northerntech.atlassian.net/browse/MEN-9205)) ([20b58d3](https://github.com/mendersoftware/mender-server-enterprise/commit/20b58d300b4e2acb7e94cb3e8fbb53f4b187a8d6))  by @mineralsfree




- *(gui)* Added unlimited devices handling to billing page
([MEN-8878](https://northerntech.atlassian.net/browse/MEN-8878)) ([27db50b](https://github.com/mendersoftware/mender-server-enterprise/commit/27db50b145b2baacbd1db34b1f09a8ef8c3024df))  by @mineralsfree




- *(gui)* Added user warn about PAT invalidation after upgrade
([MEN-8885](https://northerntech.atlassian.net/browse/MEN-8885)) ([74bca85](https://github.com/mendersoftware/mender-server-enterprise/commit/74bca85a098ba56d853581e30cf4e55d5f318642))  by @mineralsfree




- *(gui)* Refactored device inventory display to more structured table like format
 ([bc0a980](https://github.com/mendersoftware/mender-server-enterprise/commit/bc0a98001ce6d0f1549f5a850cdcc9eeaa8beba2))  by @mzedel



- *(gui)* Added data display sync functionality to align multiple instances across one view
 ([fcaa9ff](https://github.com/mendersoftware/mender-server-enterprise/commit/fcaa9ffd7da281e029b6c6802cdacf6aaf4a749e))  by @mzedel



- *(gui)* Ensured multiple data display instances align in appropriate views
 ([684fcf7](https://github.com/mendersoftware/mender-server-enterprise/commit/684fcf7773b0ef5740783702109074a5caca25a0))  by @mzedel



- *(gui)* Added device tier limits to header
([MEN-8879](https://northerntech.atlassian.net/browse/MEN-8879)) ([8031e08](https://github.com/mendersoftware/mender-server-enterprise/commit/8031e088d34d8c54cf68edb702ff0c7ddd0c6491))  by @mineralsfree




- *(gui)* Added support for unlimited devices
([MEN-8879](https://northerntech.atlassian.net/browse/MEN-8879)) ([9f800ac](https://github.com/mendersoftware/mender-server-enterprise/commit/9f800ac81a7a8a410e780e396ec80afcab2bdffb))  by @mineralsfree




- *(gui)* Added compact device limit property
([MEN-8882](https://northerntech.atlassian.net/browse/MEN-8882)) ([2bcb91f](https://github.com/mendersoftware/mender-server-enterprise/commit/2bcb91fa793c3b30c0a0df6220f4fab83b534163))  by @mineralsfree




- *(gui)* Added tiers support to accepted device dashboard widget
([MEN-8882](https://northerntech.atlassian.net/browse/MEN-8882)) ([13b77ed](https://github.com/mendersoftware/mender-server-enterprise/commit/13b77ed66703ae5fffece5e2e9b9e5df616d587d))  by @mineralsfree




- *(gui)* Added security notification to the dashboard
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([8685508](https://github.com/mendersoftware/mender-server-enterprise/commit/8685508d4ed9e7711fbeb43487a171f69f9ee30f))  by @mineralsfree




- *(gui)* Aligned the email verification flow with new design
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([48ad7a3](https://github.com/mendersoftware/mender-server-enterprise/commit/48ad7a3eb80a1a9938048c49324c57e9ad394f83))  by @mineralsfree




- *(gui)* Show verify email confirmation instead of expanding 2fa
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([74f9f62](https://github.com/mendersoftware/mender-server-enterprise/commit/74f9f624fda0f4d6279393a3e99d90166a466eaa))  by @mineralsfree




- *(gui)* Added confirm button customization prop for confirm modal
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([afc1a1b](https://github.com/mendersoftware/mender-server-enterprise/commit/afc1a1bc55121f4c44b1a89aabe9c73935b2533f))  by @mineralsfree





  + made type input optional

- *(gui)* Adjusted 2fa setup to a new design and flow
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([21fc003](https://github.com/mendersoftware/mender-server-enterprise/commit/21fc0038f3190ff01ce8a1079e840e590822e6d9))  by @mineralsfree




- *(gui)* Adjusted profile page to include alerts & aligned with design
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([1b7fffc](https://github.com/mendersoftware/mender-server-enterprise/commit/1b7fffcdb1ce4397ff199cce89acb213b8a19f79))  by @mineralsfree




- *(gui)* Adjusted 2fa form to align with new design
([MEN-9095](https://northerntech.atlassian.net/browse/MEN-9095)) ([d46851d](https://github.com/mendersoftware/mender-server-enterprise/commit/d46851d9376a85d9af7831dd450a3eb8a9da6ae1))  by @mineralsfree




- *(gui)* Disable add/edit user functionality for unverified users
([MEN-8965](https://northerntech.atlassian.net/browse/MEN-8965)) ([418571e](https://github.com/mendersoftware/mender-server-enterprise/commit/418571ec60aa4e2f493037b887f48bdbe74b0b42))  by @mineralsfree




- *(gui)* Let device attributes be shown in a more useful order, prioritizing recent usage
 ([edddc47](https://github.com/mendersoftware/mender-server-enterprise/commit/edddc472b8923e84ea76fcc8122d9b34456c7a5c))  by @mzedel



- *(gui)* Added reset adornment icon for search input
([MEN-9248](https://northerntech.atlassian.net/browse/MEN-9248)) ([221ea1b](https://github.com/mendersoftware/mender-server-enterprise/commit/221ea1beee47ccc1545f136c22e9ce81e4e17d64))  by @mineralsfree




- *(gui)* Added alert for RBAC not available in non-enterprise plans
([MEN-8610](https://northerntech.atlassian.net/browse/MEN-8610)) ([52be372](https://github.com/mendersoftware/mender-server-enterprise/commit/52be37238b9117fadbac721f4e45a79a032441f9))  by @mineralsfree




- *(gui)* Defer render until products loaded
([MEN-9277](https://northerntech.atlassian.net/browse/MEN-9277)) ([3ac968d](https://github.com/mendersoftware/mender-server-enterprise/commit/3ac968da366aea1972b5cf4471e83de574f42c7e))  by @mineralsfree




- *(gui)* Integrated dynamic tiers from backend API
([MEN-9277](https://northerntech.atlassian.net/browse/MEN-9277)) ([69e44c2](https://github.com/mendersoftware/mender-server-enterprise/commit/69e44c274bd0c26e60db38e8a53647a7bb33d86f))  by @mineralsfree




- *(gui)* Added support for addons in tiers for summary
([MEN-9277](https://northerntech.atlassian.net/browse/MEN-9277)) ([82a6f33](https://github.com/mendersoftware/mender-server-enterprise/commit/82a6f3324e1109c0ed7c9d9eb93b5a33cb5ae971))  by @mineralsfree




- *(tenantadm)* GET /billing/products static endpoint
([MEN-8561](https://northerntech.atlassian.net/browse/MEN-8561)) ([352959d](https://github.com/mendersoftware/mender-server-enterprise/commit/352959d6cd78c04fcb3f7bfeaca4f7710fdb6664))  by @merlin-northern






- *(tenantadm)* Set default max_micro_devices for trial tenants to 10
([MEN-8572](https://northerntech.atlassian.net/browse/MEN-8572)) ([ce0086d](https://github.com/mendersoftware/mender-server-enterprise/commit/ce0086dd3af91c0f61c6c50ec9aa07b6afd6eb9e))  by @frodeha




- *(tenantadm)* Changed enterprise default max_devices to `-1`
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([b6d4d30](https://github.com/mendersoftware/mender-server-enterprise/commit/b6d4d30a2db793c9b239812a8f1109a2a3857a64))  by @frodeha





  Changed the default max_devices limit for enterprise plans from 0
  (unlimited) to -1 (also unlimited) as part standardizing on the value
  -1 as the definition of an unlimited limit.

- *(tenantadm)* Changed `update-tenant` command to use `-1` as unlimited
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([c62189f](https://github.com/mendersoftware/mender-server-enterprise/commit/c62189f1f38fce91c76be5529c90dcb115fe10c5))  by @frodeha




- *(useradm)* New configuration: `insecure_disable_email_verification`
([MEN-8966](https://northerntech.atlassian.net/browse/MEN-8966)) ([82bbfab](https://github.com/mendersoftware/mender-server-enterprise/commit/82bbfabc86c7ee42245ea631dd733fa077ec91da))  by @alfrunes





  The configuration option disable email verification for account
  administration APIs.

- *(useradm)* Require email verification for creating or modifying user email
([MEN-8966](https://northerntech.atlassian.net/browse/MEN-8966)) ([7dca408](https://github.com/mendersoftware/mender-server-enterprise/commit/7dca408d19e7fc0ce8e5ac20b29ec4e2c23933bf))  by @alfrunes





  If configuration `insecure_disable_email_verification` is not set, creating
  or modifying other users email require the subject email to be verified.

- *(useradm)* New flag for command create-user: --email-verified
 ([c75e8c1](https://github.com/mendersoftware/mender-server-enterprise/commit/c75e8c15a3966e745735b251842542cdfe656f49))  by @alfrunes




  The flag marks the user as a trusted email without explicitly having to
  verify the email.

- *(workflows)* Updated default max_devices in create_tenant workflow
([MEN-9180](https://northerntech.atlassian.net/browse/MEN-9180)) ([d75e4e6](https://github.com/mendersoftware/mender-server-enterprise/commit/d75e4e65dd6d16b08cc1feefb39577405c2095b2))  by @frodeha




- *(workflows)* Add a workflow for sending email when PAT changes
 ([03df0f0](https://github.com/mendersoftware/mender-server-enterprise/commit/03df0f0548ead5f4c958bb3106ea1c0f874bca98))  by @bahaa-ghazal







### Refactor


- *(deviceconfig)* Migrate mongo-driver to v2
([QA-1448](https://northerntech.atlassian.net/browse/QA-1448)) ([38620fb](https://github.com/mendersoftware/mender-server-enterprise/commit/38620fb27d5b94910d04c62a519e250efee8b197))  by @bahaa-ghazal




- *(gui)* Streamlined data displays for small amounts of data + simplified component structure
 ([0af7b2a](https://github.com/mendersoftware/mender-server-enterprise/commit/0af7b2a957635b4a5b27301bfb5556965cfb00c7))  by @mzedel



- *(gui)* Replaced the device limit stats selector
([MEN-8882](https://northerntech.atlassian.net/browse/MEN-8882)) ([6eef456](https://github.com/mendersoftware/mender-server-enterprise/commit/6eef45655fa511d4d6df7a4ff6f042109f4304d5))  by @mineralsfree




- *(tenantadm)* Use same convention when retrieving unknown values
 ([c7ed296](https://github.com/mendersoftware/mender-server-enterprise/commit/c7ed296dede7f149855c73b73d1a27d8024c3b12))  by @bahaa-ghazal



- *(tenantadm)* Make ChangeSubscription preconditions tier aware
 ([687302b](https://github.com/mendersoftware/mender-server-enterprise/commit/687302ba50a040f4f425c81127dbfe8446360046))  by @alfrunes




- *(tenantadm)* Properly enforce required tenantadm CLI flags
 ([b3dda33](https://github.com/mendersoftware/mender-server-enterprise/commit/b3dda33f2369b8a69b56565bff717edf5a27a4e3))  by @LudvigAnderson





  Previously, the tenantadm commands did not have required flags marked as such. If missing multiple flags, the user would only be notified of one. Now, all mising flags will be shown immediately to the user.

- *(useradm)* Change OAuth2.CreateLoginURL to take entire State as arg
 ([ae586ef](https://github.com/mendersoftware/mender-server-enterprise/commit/ae586ef5701bd89706d47c5033eb5237b9e0ed2f))  by @alfrunes



- *(useradm)* Lower cyclo complexity for UserAdmApiHandlers.OpenIdConnectLogin
 ([b35ce6c](https://github.com/mendersoftware/mender-server-enterprise/commit/b35ce6c433ffaae14adeaa78fa5380472b015ebf))  by @alfrunes



- *(useradm)* Properly enforce required useradm CLI flags
 ([d6a11e8](https://github.com/mendersoftware/mender-server-enterprise/commit/d6a11e8321a118f6090f5c7340c0594d15aadba6))  by @LudvigAnderson





  Previously, the useradm commands did not have required flags marked as such. If missing multiple flags, the user would only be notified of one. Now, all mising flags will be shown immediately to the user.

- *(workflows)* Extend `JobProcessor` to include all job processing logic
 ([d16b893](https://github.com/mendersoftware/mender-server-enterprise/commit/d16b893649fe3356b153d042132cec2cdf9a2497))  by @bahaa-ghazal




  Move all job processing logic to the processor folder, and make them methods to
  the struct `JobProcessor`.

- *(workflows)* Move google sheets processing logic to processor
 ([86fb5bd](https://github.com/mendersoftware/mender-server-enterprise/commit/86fb5bdb9fb6450e7bd29e6d0221682f63486dd4))  by @bahaa-ghazal



- Restructure (flatten) integration test pytest module tree
 ([9d30541](https://github.com/mendersoftware/mender-server-enterprise/commit/9d305419d07f22e44918c2f1cdde851761d4ad60))  by @alfrunes




  Will make it easier to reuse the generated openapi client and test
  utilities with other pytest environments.
- Move tenant utils from pkg/store to pkg/mongo
 ([da34190](https://github.com/mendersoftware/mender-server-enterprise/commit/da34190f4176ff856ecf4bb786c63fc0017bea03))  by @bahaa-ghazal


- Ues the tenant utils from pkg/mongo instead of pkg/store
 ([b593cfa](https://github.com/mendersoftware/mender-server-enterprise/commit/b593cfa1fdb9f434301d1cd4e137f27d59a54a74))  by @bahaa-ghazal






### Security


- Bump integration-tester container tag
 ([7993c77](https://github.com/mendersoftware/mender-server-enterprise/commit/7993c7723e6da99354bb260f94968bfb1ce125b7))  by @alfrunes




  To force a rebuild on local runs.
- Bump lodash from 4.17.21 to 4.17.23 in /frontend
 ([c56ee37](https://github.com/mendersoftware/mender-server-enterprise/commit/c56ee37a1cd90bb7aa9bbf84d4b2de7f623848da))  by @dependabot[bot]




  Bumps [lodash](https://github.com/lodash/lodash) from 4.17.21 to 4.17.23.
  - [Release notes](https://github.com/lodash/lodash/releases)
  - [Commits](https://github.com/lodash/lodash/compare/4.17.21...4.17.23)
  
  ---
  updated-dependencies:
  - dependency-name: lodash
    dependency-version: 4.17.23
    dependency-type: indirect
  ...
- Bump github.com/aws/aws-sdk-go-v2/service/bedrockruntime@v1.48.0
 ([215bf05](https://github.com/mendersoftware/mender-server-enterprise/commit/215bf056283ff97e2afec048fe75a35b182423a4))  by @alfrunes


- Bump golang.org/x/oauth2 v0.34.0
 ([24b12f6](https://github.com/mendersoftware/mender-server-enterprise/commit/24b12f6846f2b4cc8f1988429cf9f7f611bca863))  by @alfrunes


- Bump google.golang.org/api@v0.264.0
 ([6151fd8](https://github.com/mendersoftware/mender-server-enterprise/commit/6151fd8d5065ed83b33af995e9824daa24e8a687))  by @alfrunes








## 4.2.0-saas.1 - 2026-01-20


### Bug fixes


- *(auditlogs)* Change default audit log retention time to 365 days
([ME-612](https://northerntech.atlassian.net/browse/ME-612)) ([7f90b25](https://github.com/mendersoftware/mender-server-enterprise/commit/7f90b2555c4c1907fb081a9a01862d201dc043f6))  by @alfrunes




- *(deployments)* Validate phases after populating devices in a deployment
 ([adfc2b5](https://github.com/mendersoftware/mender-server-enterprise/commit/adfc2b5aed7ef254bc5afcd419db02649414fe26))  by @bahaa-ghazal



- *(deployments)* Do not reassign phase to device deployment
([MEN-9196](https://northerntech.atlassian.net/browse/MEN-9196)) ([3fb1f7a](https://github.com/mendersoftware/mender-server-enterprise/commit/3fb1f7aedd7edff5fcb7e0e41e8ebee6370c27c8))  by @kjaskiewiczz





  If the device deployment has been already assing to particular
  deployment phase, do not reassing it and do not check if it can be part
  of the deployment phase.

- *(deviceauth)* Prevent multiple accepted AuthSets when calling AutoAuth
([MEN-9058](https://northerntech.atlassian.net/browse/MEN-9058)) ([97ca348](https://github.com/mendersoftware/mender-server-enterprise/commit/97ca3483b837bcbe83113f4d7fa9e69e724e67e0))  by @alfrunes




- *(deviceauth)* Make sure redis logic execute in correct order
([MEN-9074](https://northerntech.atlassian.net/browse/MEN-9074)) ([3adbea7](https://github.com/mendersoftware/mender-server-enterprise/commit/3adbea7ca12551dbe914ea4e73bc84ffb4703bba))  by @bahaa-ghazal




- *(deviceauth)* Missing error handling when accepting in auto-auth
 ([342987c](https://github.com/mendersoftware/mender-server-enterprise/commit/342987ced5c3a60357272921b0c393f3e509fdc8))  by @alfrunes




  When rejecting old auth sets in the auto-auth endpoint, the endpoint
  misbehaves if no auth sets were rejected.

- *(deviceauth)* Auto-auth immediately rejecting auth set
 ([49f4782](https://github.com/mendersoftware/mender-server-enterprise/commit/49f47826cbf7d16087502540cdee3748b5b78164))  by @alfrunes



- *(deviceconnect)* Do not send close frame already received from peer
 ([9969b7b](https://github.com/mendersoftware/mender-server-enterprise/commit/9969b7b6a9803ef432794736c4f01c4e436196da))  by @alfrunes



- *(deviceconnect)* Race condition sending websocket error to peer
([QA-1445](https://northerntech.atlassian.net/browse/QA-1445)) ([608f839](https://github.com/mendersoftware/mender-server-enterprise/commit/608f839fd2cf81f6858af41be283c86f63b38212))  by @alfrunes





  A race condition occur when the websocket handler terminates where it
  will sometimes close too soon, resulting in an unexpected EOF error
  observed from the writing go routine. This commit makes the writer the
  main go routine to ensure the writer always terminates before returning
  and closing the connection.

- *(gui)* Increased feedback form delay time
([MEN-9177](https://northerntech.atlassian.net/browse/MEN-9177)) ([ac2b83a](https://github.com/mendersoftware/mender-server-enterprise/commit/ac2b83af45a17fe0b1769b380fa27d9548c719e9))  by @mineralsfree




- *(gui)* Trigger save and postponement when closing feedback dialog
([MEN-9177](https://northerntech.atlassian.net/browse/MEN-9177)) ([3a95fed](https://github.com/mendersoftware/mender-server-enterprise/commit/3a95feda568244725bfbb2331cc2ee54e5f65c69))  by @mineralsfree




- *(inventory)* Limit `per_page` to 500 for the endpoint `/filters/search`
([MEN-7155](https://northerntech.atlassian.net/browse/MEN-7155)) ([555e4bf](https://github.com/mendersoftware/mender-server-enterprise/commit/555e4bf232c405ecb79130b8d063843573df89e5))  by @bahaa-ghazal




- *(useradm)* Allow children tenants to modify writable SSO configuration
 ([e132b94](https://github.com/mendersoftware/mender-server-enterprise/commit/e132b9466987774e7ad65833ccd9cb7096816497))  by @alfrunes



- Adjusted wording in PAT security notification emails to avoid confusion
([MEN-9244](https://northerntech.atlassian.net/browse/MEN-9244)) ([aa0de34](https://github.com/mendersoftware/mender-server-enterprise/commit/aa0de34b3744adbf5bea7c055a6ae597af28f869))  by @olehermanse








### Features


- *(deployments)* Accept exact device count in phased rollout
([MEN-9004](https://northerntech.atlassian.net/browse/MEN-9004)) ([eced34c](https://github.com/mendersoftware/mender-server-enterprise/commit/eced34c838b96adb1e5449e2aec3c3083ce9d2b0))  by @bahaa-ghazal






- *(deployments)* Expose phase id with device deployment object
 ([43128ac](https://github.com/mendersoftware/mender-server-enterprise/commit/43128acff0c2dd2cbfde4043186807082f6d34b2))  by @kjaskiewiczz




  In case of phased deployment we store phase identifier with device
  deployment object, but we were not exposing it through our APIs.
  With this change, the information will be exposed.

- *(deviceauth)* Propagate tier to inventory
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([9467f07](https://github.com/mendersoftware/mender-server-enterprise/commit/9467f07ba50402825cdc6b38b41a03c12cff99e0))  by @merlin-northern






- *(deviceauth)* Propagate tier to inventory on change
([MEN-9226](https://northerntech.atlassian.net/browse/MEN-9226)) ([e8d87b4](https://github.com/mendersoftware/mender-server-enterprise/commit/e8d87b4553e2bc555a500945081ae6dcff2a9a79))  by @merlin-northern






- *(deviceauth)* GetAuthSetByIdDataHashKey tier support
([MEN-9226](https://northerntech.atlassian.net/browse/MEN-9226)) ([8385ec6](https://github.com/mendersoftware/mender-server-enterprise/commit/8385ec6dd5b772d5bbc3760d8c9e55020b443fea))  by @merlin-northern






- *(gui)* Added zephyr mcu onboarding option
 ([f3d404d](https://github.com/mendersoftware/mender-server-enterprise/commit/f3d404d6748a88db2bb20ae140942f0a52c013e8))  by @mineralsfree



- *(gui)* Adjusted onboarding tips in accordance with the design
 ([5a1e4b8](https://github.com/mendersoftware/mender-server-enterprise/commit/5a1e4b8942a7c997123c1335ae048c988f3e91b4))  by @mineralsfree



- *(gui)* Added release artifact filters
([MEN-8669](https://northerntech.atlassian.net/browse/MEN-8669)) ([e7abe44](https://github.com/mendersoftware/mender-server-enterprise/commit/e7abe447b05493559f028dbe2c8c628baf6ca231))  by @mineralsfree




- *(gui)* Moved zephyr onboarding guide behind feature flag
([MEN-9205](https://northerntech.atlassian.net/browse/MEN-9205)) ([b2a4c65](https://github.com/mendersoftware/mender-server-enterprise/commit/b2a4c65b424453ba05be058836c7ca9b6fa4058b))  by @mineralsfree




- *(workflows)* Default value for input variables and gojsonq fix
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([4908390](https://github.com/mendersoftware/mender-server-enterprise/commit/4908390d9b906e908d1dc1969e795e44c96bad7f))  by @merlin-northern






  With this change you can use the following syntax
  to set a default value for an empty input variable:
  
  ${workflow.input.device.jsonInput.tier|standard}
  
  There is also a required in some environments
  fix for proper querying of the fields via jsonInput.

- *(workflows)* Tiers propagation support
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([5968d01](https://github.com/mendersoftware/mender-server-enterprise/commit/5968d01e6d5c3951628a10590771281014e74cef))  by @merlin-northern










### Refactor


- *(deployments)* Simplify signature for building tenant query
 ([e477c2b](https://github.com/mendersoftware/mender-server-enterprise/commit/e477c2bc7fc61ab983d374fbfa908787845f8478))  by @alfrunes



- *(deviceauth)* Extend RejectAuthSetsForDevice to exclude AuthSets
 ([5b84744](https://github.com/mendersoftware/mender-server-enterprise/commit/5b8474413d1f9016259d5ffdc6f2eb6a9a7a0a79))  by @alfrunes



- *(tenantadm)* Remove store.GetExpiredTenants / extend tenant filter
 ([ddb0aee](https://github.com/mendersoftware/mender-server-enterprise/commit/ddb0aee1ac222c221de8e9d899824707dcb69914))  by @alfrunes




  Added filtering capabilities on suspension timestamps to be able to
  filter future suspensions.





### Security


- Bump filelock from 3.20.0 to 3.20.1 in /backend/tests
 ([9453aae](https://github.com/mendersoftware/mender-server-enterprise/commit/9453aaeea44e6431cbef76e375e06504a6b7ae9d))  by @dependabot[bot]




  Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.20.0 to 3.20.1.
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.20.0...3.20.1)
  
  ---
  updated-dependencies:
  - dependency-name: filelock
    dependency-version: 3.20.1
    dependency-type: direct:production
  ...
- Bump storybook from 10.0.6 to 10.1.10 in /frontend
 ([a13013f](https://github.com/mendersoftware/mender-server-enterprise/commit/a13013fdba29a521140201742817be6fdcffcb06))  by @dependabot[bot]




  Bumps [storybook](https://github.com/storybookjs/storybook/tree/HEAD/code/core) from 10.0.6 to 10.1.10.
  - [Release notes](https://github.com/storybookjs/storybook/releases)
  - [Changelog](https://github.com/storybookjs/storybook/blob/next/CHANGELOG.md)
  - [Commits](https://github.com/storybookjs/storybook/commits/v10.1.10/code/core)
  
  ---
  updated-dependencies:
  - dependency-name: storybook
    dependency-version: 10.1.10
    dependency-type: indirect
  ...
- Bump the backend-docker-compose-dependencies group across 2 directories with 3 updates
 ([3013211](https://github.com/mendersoftware/mender-server-enterprise/commit/3013211c371b1a2b07931cf214b46400d16ffac2))  by @dependabot[bot]




  Bumps the backend-docker-compose-dependencies group with 1 update in the / directory: traefik.
  Bumps the backend-docker-compose-dependencies group with 2 updates in the /compose directory: redis and chrislusf/seaweedfs.
  
  
  Updates `traefik` from 3.6.2 to 3.6.6
  
  Updates `redis` from 8.2 to 8.4
  
  Updates `chrislusf/seaweedfs` from 4.00 to 4.04
  
  ---
  updated-dependencies:
  - dependency-name: traefik
    dependency-version: 3.6.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: redis
    dependency-version: '8.4'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '4.04'
    dependency-type: direct:production
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([2dbbfdc](https://github.com/mendersoftware/mender-server-enterprise/commit/2dbbfdc0b3d225f1e9a1778999cb3c2d26803333))  by @dependabot[bot]




  Bumps the backend-golang-dependencies group in /backend with 13 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.40.0` | `1.41.0` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.32.2` | `1.32.6` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.19.2` | `1.19.6` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.13` | `1.72.0` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.14` | `1.32.16` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.92.1` | `1.95.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.12.2` | `2.12.3` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.47.0` | `1.48.0` |
  | [github.com/spf13/cobra](https://github.com/spf13/cobra) | `1.10.1` | `1.10.2` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.45.0` | `0.46.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.47.0` | `0.48.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.38.0` | `0.39.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.37.0` | `0.38.0` |
  
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.40.0 to 1.41.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.40.0...v1.41.0)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.32.2 to 1.32.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.2...v1.32.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.19.2 to 1.19.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/m2/v1.19.2...service/m2/v1.19.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.13 to 1.72.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.13...service/s3/v1.72.0)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.14 to 1.32.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/mgn/v1.32.14...service/mgn/v1.32.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.92.1 to 1.95.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.92.1...service/s3/v1.95.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.12.2 to 2.12.3
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.12.2...v2.12.3)
  
  Updates `github.com/nats-io/nats.go` from 1.47.0 to 1.48.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.47.0...v1.48.0)
  
  Updates `github.com/spf13/cobra` from 1.10.1 to 1.10.2
  - [Release notes](https://github.com/spf13/cobra/releases)
  - [Commits](https://github.com/spf13/cobra/compare/v1.10.1...v1.10.2)
  
  Updates `golang.org/x/crypto` from 0.45.0 to 0.46.0
  - [Commits](https://github.com/golang/crypto/compare/v0.45.0...v0.46.0)
  
  Updates `golang.org/x/net` from 0.47.0 to 0.48.0
  - [Commits](https://github.com/golang/net/compare/v0.47.0...v0.48.0)
  
  Updates `golang.org/x/sys` from 0.38.0 to 0.39.0
  - [Commits](https://github.com/golang/sys/compare/v0.38.0...v0.39.0)
  
  Updates `golang.org/x/term` from 0.37.0 to 0.38.0
  - [Commits](https://github.com/golang/term/compare/v0.37.0...v0.38.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.41.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.32.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.19.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.72.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.95.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.48.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/cobra
    dependency-version: 1.10.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.46.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.48.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.39.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.38.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump github.com/quic-go/quic-go from 0.54.1 to 0.57.0 in /backend
 ([028888d](https://github.com/mendersoftware/mender-server-enterprise/commit/028888dac409185f013db077d0ce9d2855ece459))  by @dependabot[bot]




  Bumps [github.com/quic-go/quic-go](https://github.com/quic-go/quic-go) from 0.54.1 to 0.57.0.
  - [Release notes](https://github.com/quic-go/quic-go/releases)
  - [Commits](https://github.com/quic-go/quic-go/compare/v0.54.1...v0.57.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/quic-go/quic-go
    dependency-version: 0.57.0
    dependency-type: indirect
  ...
- Bump nginxinc/nginx-unprivileged in /frontend
 ([b55cd80](https://github.com/mendersoftware/mender-server-enterprise/commit/b55cd801eb6ec648843fb6e2364412affc73f92f))  by @dependabot[bot]




  Bumps nginxinc/nginx-unprivileged from 1.29.2-alpine3.22-slim to 1.29.3-alpine3.22-slim.
  
  ---
  updated-dependencies:
  - dependency-name: nginxinc/nginx-unprivileged
    dependency-version: 1.29.3-alpine3.22-slim
    dependency-type: direct:production
    update-type: version-update:semver-patch
  ...
- Bump alpine
 ([5bd98a2](https://github.com/mendersoftware/mender-server-enterprise/commit/5bd98a2457758a5ba86a31cc140e76de4c993dc0))  by @dependabot[bot]




  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/create-artifact-worker directory: alpine.
  
  
  Updates `alpine` from 3.22.2 to 3.23.2
  
  ---
  updated-dependencies:
  - dependency-name: alpine
    dependency-version: 3.23.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-dependencies
  ...
- Bump the e2e-test-dependencies group
 ([db41c17](https://github.com/mendersoftware/mender-server-enterprise/commit/db41c179805e9f1dbe5ace58e1d1fef6c90e5ba2))  by @dependabot[bot]




  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 2 updates: [inquirer](https://github.com/SBoudrias/Inquirer.js) and [validator](https://github.com/validatorjs/validator.js).
  
  
  Updates `inquirer` from 13.0.1 to 13.1.0
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@13.0.1...inquirer@13.1.0)
  
  Updates `validator` from 13.15.23 to 13.15.26
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.23...13.15.26)
  
  ---
  updated-dependencies:
  - dependency-name: inquirer
    dependency-version: 13.1.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  - dependency-name: validator
    dependency-version: 13.15.26
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  ...
- Bump qs and express in /frontend
 ([0d65926](https://github.com/mendersoftware/mender-server-enterprise/commit/0d659265a0a07c37dea04127d9599fca8d502784))  by @dependabot[bot]




  Bumps [qs](https://github.com/ljharb/qs) and [express](https://github.com/expressjs/express). These dependencies needed to be updated together.
  
  Updates `qs` from 6.13.0 to 6.14.1
  - [Changelog](https://github.com/ljharb/qs/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/ljharb/qs/compare/v6.13.0...v6.14.1)
  
  Updates `express` from 4.21.2 to 4.22.1
  - [Release notes](https://github.com/expressjs/express/releases)
  - [Changelog](https://github.com/expressjs/express/blob/v4.22.1/History.md)
  - [Commits](https://github.com/expressjs/express/compare/4.21.2...v4.22.1)
  
  ---
  updated-dependencies:
  - dependency-name: qs
    dependency-version: 6.14.1
    dependency-type: indirect
  - dependency-name: express
    dependency-version: 4.22.1
    dependency-type: indirect
  ...
- Bump the development-dependencies group
 ([8d421a3](https://github.com/mendersoftware/mender-server-enterprise/commit/8d421a3d9504b434f514a8e2769cd88aff14eefe))  by @dependabot[bot]




  Bumps the development-dependencies group in /frontend with 15 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.6.6` | `1.7.0` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.6.6` | `1.7.0` |
  | [@testing-library/react](https://github.com/testing-library/react-testing-library) | `16.3.0` | `16.3.1` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.10.1` | `25.0.3` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.1.1` | `5.1.2` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `4.0.15` | `4.0.16` |
  | [autoprefixer](https://github.com/postcss/autoprefixer) | `10.4.22` | `10.4.23` |
  | [esbuild-loader](https://github.com/privatenumber/esbuild-loader) | `4.4.0` | `4.4.2` |
  | [eslint](https://github.com/eslint/eslint) | `9.39.1` | `9.39.2` |
  | [eslint-rspack-plugin](https://github.com/rspack-contrib/eslint-rspack-plugin) | `4.2.1` | `4.3.0` |
  | [globals](https://github.com/sindresorhus/globals) | `16.5.0` | `17.0.0` |
  | [jsdom](https://github.com/jsdom/jsdom) | `27.2.0` | `27.4.0` |
  | [msw](https://github.com/mswjs/msw) | `2.12.3` | `2.12.7` |
  | [vite-tsconfig-paths](https://github.com/aleclarson/vite-tsconfig-paths) | `5.1.4` | `6.0.3` |
  | [vitest](https://github.com/vitest-dev/vitest/tree/HEAD/packages/vitest) | `4.0.15` | `4.0.16` |
  
  
  Updates `@rspack/cli` from 1.6.6 to 1.7.0
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.7.0/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.6.6 to 1.7.0
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.7.0/packages/rspack)
  
  Updates `@testing-library/react` from 16.3.0 to 16.3.1
  - [Release notes](https://github.com/testing-library/react-testing-library/releases)
  - [Changelog](https://github.com/testing-library/react-testing-library/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/react-testing-library/compare/v16.3.0...v16.3.1)
  
  Updates `@types/node` from 24.10.1 to 25.0.3
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@vitejs/plugin-react` from 5.1.1 to 5.1.2
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.1.2/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 4.0.15 to 4.0.16
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.16/packages/coverage-v8)
  
  Updates `autoprefixer` from 10.4.22 to 10.4.23
  - [Release notes](https://github.com/postcss/autoprefixer/releases)
  - [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/postcss/autoprefixer/compare/10.4.22...10.4.23)
  
  Updates `esbuild-loader` from 4.4.0 to 4.4.2
  - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
  - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v4.4.0...v4.4.2)
  
  Updates `eslint` from 9.39.1 to 9.39.2
  - [Release notes](https://github.com/eslint/eslint/releases)
  - [Commits](https://github.com/eslint/eslint/compare/v9.39.1...v9.39.2)
  
  Updates `eslint-rspack-plugin` from 4.2.1 to 4.3.0
  - [Release notes](https://github.com/rspack-contrib/eslint-rspack-plugin/releases)
  - [Changelog](https://github.com/rstackjs/eslint-rspack-plugin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/rspack-contrib/eslint-rspack-plugin/compare/v4.2.1...v4.3.0)
  
  Updates `globals` from 16.5.0 to 17.0.0
  - [Release notes](https://github.com/sindresorhus/globals/releases)
  - [Commits](https://github.com/sindresorhus/globals/compare/v16.5.0...v17.0.0)
  
  Updates `jsdom` from 27.2.0 to 27.4.0
  - [Release notes](https://github.com/jsdom/jsdom/releases)
  - [Changelog](https://github.com/jsdom/jsdom/blob/main/Changelog.md)
  - [Commits](https://github.com/jsdom/jsdom/compare/27.2.0...27.4.0)
  
  Updates `msw` from 2.12.3 to 2.12.7
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.12.3...v2.12.7)
  
  Updates `vite-tsconfig-paths` from 5.1.4 to 6.0.3
  - [Release notes](https://github.com/aleclarson/vite-tsconfig-paths/releases)
  - [Commits](https://github.com/aleclarson/vite-tsconfig-paths/compare/v5.1.4...v6.0.3)
  
  Updates `vitest` from 4.0.15 to 4.0.16
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.16/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/react"
    dependency-version: 16.3.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 25.0.3
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.1.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 4.0.16
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: autoprefixer
    dependency-version: 10.4.23
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: esbuild-loader
    dependency-version: 4.4.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: eslint
    dependency-version: 9.39.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: eslint-rspack-plugin
    dependency-version: 4.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: globals
    dependency-version: 17.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: jsdom
    dependency-version: 27.4.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.12.7
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: vite-tsconfig-paths
    dependency-version: 6.0.3
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 4.0.16
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([e3426da](https://github.com/mendersoftware/mender-server-enterprise/commit/e3426da819eada9568aa4b133291c978745cad97))  by @dependabot[bot]




  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.5 to 7.3.6
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.6/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.5 to 7.3.6
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.6/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.19.0 to 8.23.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.23.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.23.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([467b309](https://github.com/mendersoftware/mender-server-enterprise/commit/467b309a61d246ff13a169ee7e45807832290e11))  by @dependabot[bot]




  Bumps the production-dependencies group in /frontend with 14 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.11.0` | `2.11.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `10.28.0` | `10.32.1` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `8.5.3` | `8.6.0` |
  | [@xterm/addon-fit](https://github.com/xtermjs/xterm.js) | `0.10.0` | `0.11.0` |
  | [@xterm/addon-search](https://github.com/xtermjs/xterm.js) | `0.15.0` | `0.16.0` |
  | [@xterm/addon-web-links](https://github.com/xtermjs/xterm.js) | `0.11.0` | `0.12.0` |
  | [@xterm/xterm](https://github.com/xtermjs/xterm.js) | `5.5.0` | `6.0.0` |
  | [mui-markdown](https://github.com/HPouyanmehr/mui-markdown) | `2.0.3` | `2.1.0` |
  | [react](https://github.com/facebook/react/tree/HEAD/packages/react) | `19.2.0` | `19.2.3` |
  | [react-dom](https://github.com/facebook/react/tree/HEAD/packages/react-dom) | `19.2.0` | `19.2.3` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.67.0` | `7.69.0` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.10.0` | `7.11.0` |
  | [tss-react](https://github.com/garronej/tss-react) | `4.9.19` | `4.9.20` |
  | [validator](https://github.com/validatorjs/validator.js) | `13.15.23` | `13.15.26` |
  
  
  Updates `@reduxjs/toolkit` from 2.11.0 to 2.11.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.11.0...v2.11.2)
  
  Updates `@sentry/react` from 10.28.0 to 10.32.1
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/10.28.0...10.32.1)
  
  Updates `@stripe/stripe-js` from 8.5.3 to 8.6.0
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v8.5.3...v8.6.0)
  
  Updates `@xterm/addon-fit` from 0.10.0 to 0.11.0
  - [Release notes](https://github.com/xtermjs/xterm.js/releases)
  - [Commits](https://github.com/xtermjs/xterm.js/compare/0.10...0.11)
  
  Updates `@xterm/addon-search` from 0.15.0 to 0.16.0
  - [Release notes](https://github.com/xtermjs/xterm.js/releases)
  - [Commits](https://github.com/xtermjs/xterm.js/compare/0.15...0.16)
  
  Updates `@xterm/addon-web-links` from 0.11.0 to 0.12.0
  - [Release notes](https://github.com/xtermjs/xterm.js/releases)
  - [Commits](https://github.com/xtermjs/xterm.js/compare/0.11...0.12)
  
  Updates `@xterm/xterm` from 5.5.0 to 6.0.0
  - [Release notes](https://github.com/xtermjs/xterm.js/releases)
  - [Commits](https://github.com/xtermjs/xterm.js/compare/5.5.0...6.0.0)
  
  Updates `mui-markdown` from 2.0.3 to 2.1.0
  - [Release notes](https://github.com/HPouyanmehr/mui-markdown/releases)
  - [Commits](https://github.com/HPouyanmehr/mui-markdown/compare/v2.0.3...v2.1.0)
  
  Updates `react` from 19.2.0 to 19.2.3
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.3/packages/react)
  
  Updates `react-dom` from 19.2.0 to 19.2.3
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.3/packages/react-dom)
  
  Updates `react-hook-form` from 7.67.0 to 7.69.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.67.0...v7.69.0)
  
  Updates `react-router-dom` from 7.10.0 to 7.11.0
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.11.0/packages/react-router-dom)
  
  Updates `tss-react` from 4.9.19 to 4.9.20
  - [Release notes](https://github.com/garronej/tss-react/releases)
  - [Commits](https://github.com/garronej/tss-react/compare/v4.9.19...v4.9.20)
  
  Updates `validator` from 13.15.23 to 13.15.26
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.23...13.15.26)
  
  ---
  updated-dependencies:
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.11.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 10.32.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 8.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@xterm/addon-fit"
    dependency-version: 0.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@xterm/addon-search"
    dependency-version: 0.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@xterm/addon-web-links"
    dependency-version: 0.12.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@xterm/xterm"
    dependency-version: 6.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: mui-markdown
    dependency-version: 2.1.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react
    dependency-version: 19.2.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-dom
    dependency-version: 19.2.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.69.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: tss-react
    dependency-version: 4.9.20
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: validator
    dependency-version: 13.15.26
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump react-router and react-router-dom in /frontend
 ([1343a7f](https://github.com/mendersoftware/mender-server-enterprise/commit/1343a7f758d8073200b3b094378c70634df1c4fe))  by @dependabot[bot]




  Bumps [react-router](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router) to 7.12.0 and updates ancestor dependency [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom). These dependencies need to be updated together.
  
  
  Updates `react-router` from 7.11.0 to 7.12.0
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router@7.12.0/packages/react-router)
  
  Updates `react-router-dom` from 7.11.0 to 7.12.0
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.12.0/packages/react-router-dom)
  
  ---
  updated-dependencies:
  - dependency-name: react-router
    dependency-version: 7.12.0
    dependency-type: indirect
  - dependency-name: react-router-dom
    dependency-version: 7.12.0
    dependency-type: direct:production
  ...
- Bump filelock from 3.20.1 to 3.20.3 in /backend/tests
 ([89dcdad](https://github.com/mendersoftware/mender-server-enterprise/commit/89dcdad0b7b1d8718060b70b9984a704f1c3afce))  by @dependabot[bot]




  Bumps [filelock](https://github.com/tox-dev/py-filelock) from 3.20.1 to 3.20.3.
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.20.1...3.20.3)
  
  ---
  updated-dependencies:
  - dependency-name: filelock
    dependency-version: 3.20.3
    dependency-type: direct:production
  ...





## v4.1.0-saas.23 - 2025-12-18


### Bug fixes


- *(deployments)* Only show delta size in details once finished
([MEN-9152](https://northerntech.atlassian.net/browse/MEN-9152)) ([8840f3c](https://github.com/mendersoftware/mender-server-enterprise/commit/8840f3c39152ecd0f3a59b5e8b6302cd7112fd07))  by @alfrunes





  The endpoint getting the delta job details tried to retrieve target
  artifact size without considering the existence of the artifact. Now,
  the size details is only available once the artifact is generated.

- *(deployments)* Prevent race condition re-caching invalid value
([MEN-9071](https://northerntech.atlassian.net/browse/MEN-9071)) ([e657a4d](https://github.com/mendersoftware/mender-server-enterprise/commit/e657a4dd3c46c5e7fb8ce5b5a87aae141894b8ce))  by @bahaa-ghazal




- *(pkg)* `bytesprocessed` field not present for public APIs
 ([d044021](https://github.com/mendersoftware/mender-server-enterprise/commit/d044021dd6e0dfe7f1bcfa4ea5b5ff8c296f2dad))  by @alfrunes




  Public facing endpoints wraps the body with a io.LimitReader which
  causes the bytesprocessed field to be omitted. This PR ensures that the
  field is always present for all accesslogs.

- *(tenantadm)* Wait for `create_tenant` workflow to complete
([MEN-9041](https://northerntech.atlassian.net/browse/MEN-9041)) ([5e9488c](https://github.com/mendersoftware/mender-server-enterprise/commit/5e9488c06bcccc882e74728743725155c37e0f52))  by @bahaa-ghazal




- *(tenantadm)* Prevent child tenant creation from exceeding parent device limit
([MEN-9041](https://northerntech.atlassian.net/browse/MEN-9041)) ([fd53899](https://github.com/mendersoftware/mender-server-enterprise/commit/fd53899cefc190a000b9f9ef2b5335109bd21cf4))  by @bahaa-ghazal








### Documentation


- *(inventory)* Tenants/{tenant_id}/device/{device_id}/attributes intenral spec
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([052eb13](https://github.com/mendersoftware/mender-server-enterprise/commit/052eb137969d10dce0e78a6263d629b65134b1d2))  by @merlin-northern






- *(inventory)* Added inventory statistics api documentation
([MEN-9082](https://northerntech.atlassian.net/browse/MEN-9082)) ([235d57a](https://github.com/mendersoftware/mender-server-enterprise/commit/235d57a761bd893feb28669d99bf857132497da6))  by @frodeha








### Features


- *(inventory)* Internal patch /tenants/:tenant_id/device/:device_id/attributes
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([eddc85e](https://github.com/mendersoftware/mender-server-enterprise/commit/eddc85e4355a29be622847359fab0d3918bcf297))  by @merlin-northern






  The new endpoint PATCH /tenants/:tenant_id/device/:device_id/attributes
  works exactly like /tenants/:tenant_id/device/:device_id/attribute/scope/:scope
  with the exception that it does not override the given attributes scope.
  In other words: what you give in the body will maintain the scope.

- *(inventory)* Added endpoint for retrieving device statistics
([MEN-9082](https://northerntech.atlassian.net/browse/MEN-9082)) ([15fec13](https://github.com/mendersoftware/mender-server-enterprise/commit/15fec13fab1c94a5e4920a429bfdcc2c80dd2c8a))  by @frodeha




- *(tenantadm)* Add billing support for micro device tiers
 ([958f3a0](https://github.com/mendersoftware/mender-server-enterprise/commit/958f3a01e9ca613386ec2c92f3781a7a689fe38d))  by @alfrunes




  Tied the business logic to changing device limit on subscription change
  events when a `mender_micro` product is purchased.

- *(workflows)* Support for accessing data from objects via json
([MEN-9096](https://northerntech.atlassian.net/browse/MEN-9096)) ([e4532de](https://github.com/mendersoftware/mender-server-enterprise/commit/e4532de552438807b3ae64b2167a41efceffb4fc))  by @merlin-northern






  With this change the input parameters that are objects with json
  representation can be referenced via `identifier.jsonInput.field` syntax.
  For instance: in a device is passed as an input parameter, then
  anywhere you use `device.jsonInput.tier` you will refer to the Device.Tier
  field, since it is decoreated with json `tier`.





### Refactor


- *(gui)* Aligned statistics based device count retrieval
 ([231e982](https://github.com/mendersoftware/mender-server-enterprise/commit/231e982ba57537e4fb097e12af850d12844a3d86))  by @mzedel



- *(inventory)* Shared device status definitions
([MEN-9082](https://northerntech.atlassian.net/browse/MEN-9082)) ([be02d28](https://github.com/mendersoftware/mender-server-enterprise/commit/be02d287fcecb8ab03cdd567544ff6b237bacd86))  by @frodeha





[MEN-9152]: https://northerntech.atlassian.net/browse/MEN-9152?atlOrigin=eyJpIjoiNWRkNTljNzYxNjVmNDY3MDlhMDU5Y2ZhYzA5YTRkZjUiLCJwIjoiZ2l0aHViLWNvbS1KU1cifQ
[MEN-9071]: https://northerntech.atlassian.net/browse/MEN-9071?atlOrigin=eyJpIjoiNWRkNTljNzYxNjVmNDY3MDlhMDU5Y2ZhYzA5YTRkZjUiLCJwIjoiZ2l0aHViLWNvbS1KU1cifQ
[MEN-9041]: https://northerntech.atlassian.net/browse/MEN-9041?atlOrigin=eyJpIjoiNWRkNTljNzYxNjVmNDY3MDlhMDU5Y2ZhYzA5YTRkZjUiLCJwIjoiZ2l0aHViLWNvbS1KU1cifQ





## 4.1.0-saas.22 - 2025-12-15


### Bug fixes


- *(deployments)* Allow releases of finished deployments to be deleted
([MEN-8923](https://northerntech.atlassian.net/browse/MEN-8923)) ([d4ad1cb](https://github.com/mendersoftware/mender-server-enterprise/commit/d4ad1cb9bb38083fcaaae91ab43907e38c6b5cfa))  by @frodeha





  Only consider active deployments when we check if a release is "in use"
  before deleting it.

- *(deployments)* Add missing delta generation status fields
([MEN-9064](https://northerntech.atlassian.net/browse/MEN-9064)) ([2396356](https://github.com/mendersoftware/mender-server-enterprise/commit/23963560684c567c0e4df933078973798ab8b49b))  by @alfrunes





  Populate the fields for when the delta generation job transitions to
  finished, and compute the total time from start to finish.

- *(deviceauth)* Fixes for hitting the cached limits
 ([8a95a55](https://github.com/mendersoftware/mender-server-enterprise/commit/8a95a55740c6b2dcf2bf77ced4f4c6152e913fa6))  by @merlin-northern






- *(deviceauth)* Do not drop the old index for 2.0.1 migration
([MEN-8995](https://northerntech.atlassian.net/browse/MEN-8995)) ([ca27ee9](https://github.com/mendersoftware/mender-server-enterprise/commit/ca27ee9ba21eb510c33f734e735d1911f2835699))  by @merlin-northern






- *(deviceauth)* Use mongo's error code to check for record duplication in AddDevice
 ([52e8023](https://github.com/mendersoftware/mender-server-enterprise/commit/52e8023a2573ca9db060f90bdadb71c3db15a398))  by @OlliMartin



- *(deviceauth)* Handle empty id data in maintenance sync command
 ([1aa101c](https://github.com/mendersoftware/mender-server-enterprise/commit/1aa101c1f94f99e1ccfcc868d5fa3c742995ef05))  by @alfrunes



- *(deviceauth)* Maintenance sync stringfy incompatible inventory data
 ([d8f2039](https://github.com/mendersoftware/mender-server-enterprise/commit/d8f20390e2dfcaca748a0c91cca5bc89380567c5))  by @alfrunes



- *(deviceauth)* Aligned api response w/ current common format
 ([e081aad](https://github.com/mendersoftware/mender-server-enterprise/commit/e081aadf1e47a8ae38b7b36aac13feb240d6e3ec))  by @mzedel



- *(deviceauth)* Return 503 when redis is unavailabe
([MEN-9079](https://northerntech.atlassian.net/browse/MEN-9079)) ([6277610](https://github.com/mendersoftware/mender-server-enterprise/commit/6277610d78022db1254a15a94969a6dc3e4e95d4))  by @bahaa-ghazal




- *(deviceauth)* Prevent race condition re-caching invalid value
([MEN-9071](https://northerntech.atlassian.net/browse/MEN-9071)) ([16ab568](https://github.com/mendersoftware/mender-server-enterprise/commit/16ab5689a623f3305aae9b52b7f26bd6905cee39))  by @bahaa-ghazal




- *(deviceconnect)* Device ping/pong handler causes timeouts
([MEN-9029](https://northerntech.atlassian.net/browse/MEN-9029)) ([9b318f8](https://github.com/mendersoftware/mender-server-enterprise/commit/9b318f82587bab341e15b96a2843d61012505881))  by @alfrunes





  When there's traffic on the websocket connection, the ping/pong handler
  is never called and therefore SetReadDeadline is never called which in
  turn causes the connection to terminate.
  This PR removes the calls to Conn.SetReadDeadline to rely on TCP
  keep-alive instead.

- *(gui)* Ensured we always try to get the billing profiles - even when there might not be one yet
 ([b42932d](https://github.com/mendersoftware/mender-server-enterprise/commit/b42932d946926543a4ab3b2d5ee27546f9c34969))  by @mzedel




  - this is to allow user with an unfinished signup process to proceed

- *(gui)* Fixed an issue that would prevent sorting the list of ∆ artifact generations
 ([a13b3b9](https://github.com/mendersoftware/mender-server-enterprise/commit/a13b3b96d77eb9e0eddf4d1e78ea068fa77eabe5))  by @mzedel



- *(gui)* Made use of additional backend info about delta jobs
 ([e4be1aa](https://github.com/mendersoftware/mender-server-enterprise/commit/e4be1aa36675a05f01d4bfe7c4e4a5f2978d082d))  by @mzedel



- *(gui)* Fixed an issue that prevented trial users from short feedback loops during onboarding
 ([fbf60fd](https://github.com/mendersoftware/mender-server-enterprise/commit/fbf60fdbc59fc6099c5c90619565d7a82e02c17f))  by @mzedel




  - the shorter device intervals would not be shown in the device configuration snippet

- *(tenantadm)* Let checking billing profiles  existence not cause an error when uninitialized
 ([913dd70](https://github.com/mendersoftware/mender-server-enterprise/commit/913dd70550d8dc1fbfccb1daa63315f10e5a9646))  by @mzedel



- *(tenantadm)* Check only standard tier when going to service provider
 ([9ef6d1c](https://github.com/mendersoftware/mender-server-enterprise/commit/9ef6d1c069ad070a3d8e1abc1324226779bacadc))  by @merlin-northern





  After recent changes we return all the tiers set to 0 from deviceauth.
  With this fix we only verify the standard tier when we upgrade
  to SP tenant.

- Invalid Go template comment for send sso notification
 ([ae31b06](https://github.com/mendersoftware/mender-server-enterprise/commit/ae31b06f7b302120f766e6e5c6d1ec4aef75e503))  by @alfrunes


- Check if ratelimits is enabled without redis
([MEN-8863](https://northerntech.atlassian.net/browse/MEN-8863)) ([a896ebf](https://github.com/mendersoftware/mender-server-enterprise/commit/a896ebfb3373ee518fe98e1a5dbcb9bb3064779f))  by @bahaa-ghazal



- Fixed another set of api spec inconsistencies
 ([88352b4](https://github.com/mendersoftware/mender-server-enterprise/commit/88352b406136fbaa89da0b24f7ef44623b514572))  by @mzedel






### Documentation


- *(deployments)* Updated spec for internal get and put limit endpoints
([MEN-8848](https://northerntech.atlassian.net/browse/MEN-8848)) ([4d64fdf](https://github.com/mendersoftware/mender-server-enterprise/commit/4d64fdfc4f5b5227222ccb3f3ca088ae44d807eb))  by @frodeha





  Updated the existing API specification to be usable for limits other
  than only "storage". Also adjusted the request and response definitions
  to match the reality of the server endpoints.

- *(deployments)* Update delta objects to reflect consolidated objects
 ([40e7451](https://github.com/mendersoftware/mender-server-enterprise/commit/40e74510ade457b212e88d7ae87f2b296b568e08))  by @alfrunes




  Now DeltaJobDetails inherits the list item to reflect the actual
  response from the API.

- *(devicemonitor)* Remove required constraints on config models
 ([798e8ad](https://github.com/mendersoftware/mender-server-enterprise/commit/798e8ad31d9b04d9cf7032e08c6ec9f7c5fb7889))  by @alfrunes




  The tests reveal that the properties are not required.

- *(tenantadm)* Support for device tiers
([MEN-8907](https://northerntech.atlassian.net/browse/MEN-8907)) ([a8ea0e5](https://github.com/mendersoftware/mender-server-enterprise/commit/a8ea0e5059d5d773cb14a9102418af855926d377))  by @merlin-northern






- Regenerate OpenAPI specs for distribution
 ([c225d83](https://github.com/mendersoftware/mender-server-enterprise/commit/c225d83209a76858cd5fa0946583b6fda8b7fd09))  by @alfrunes






### Features


- *(deployments)* Added internal get and put limit endpoints
([MEN-8848](https://northerntech.atlassian.net/browse/MEN-8848)) ([7fef6ae](https://github.com/mendersoftware/mender-server-enterprise/commit/7fef6ae4b637848a387ab61ab39939b372680f97))  by @frodeha




- *(deployments)* Added support for -1 (unlimited) limits
([MEN-8848](https://northerntech.atlassian.net/browse/MEN-8848)) ([248635e](https://github.com/mendersoftware/mender-server-enterprise/commit/248635ecd12bf262553824e1a8988eef32465fda))  by @frodeha




- *(devicemonitor)* Send security notifications on email toggle
([MEN-9101](https://northerntech.atlassian.net/browse/MEN-9101)) ([588ac34](https://github.com/mendersoftware/mender-server-enterprise/commit/588ac34867b5eb75146f2627439c5ce1bc87be85))  by @merlin-northern






- *(gui)* Added a warning when trying to deploy too large artifacts to mcu devices
 ([f171dde](https://github.com/mendersoftware/mender-server-enterprise/commit/f171dded412e4010a579648a679e1769d9dd4575))  by @mzedel



- *(gui)* Delayed feedback form for 3h after first login
([MEN-8896](https://northerntech.atlassian.net/browse/MEN-8896)) ([4ec610b](https://github.com/mendersoftware/mender-server-enterprise/commit/4ec610bc922e19c68a2e0b76da9b85d39d53ace4))  by @mineralsfree




- *(pkg)* OpenAPI3 generated client for deviceauth internal API
([MEN-8907](https://northerntech.atlassian.net/browse/MEN-8907)) ([fffc55f](https://github.com/mendersoftware/mender-server-enterprise/commit/fffc55f30394eb3dc6c6497df8c47080584b254f))  by @merlin-northern






- *(tenantadm)* Support for device tiers
([MEN-8907](https://northerntech.atlassian.net/browse/MEN-8907)) ([4a13e8c](https://github.com/mendersoftware/mender-server-enterprise/commit/4a13e8cb9a4ad300172fe883f3fe2269b3f1d277))  by @merlin-northern






- *(useradm)* Send an email on PAT management events
([MEN-8969](https://northerntech.atlassian.net/browse/MEN-8969)) ([57e5810](https://github.com/mendersoftware/mender-server-enterprise/commit/57e5810534e451fbffff49c169c9b6500e76e396))  by @merlin-northern






- *(workflows)* Send security notifications: email_notification workflow
([MEN-9101](https://northerntech.atlassian.net/browse/MEN-9101)) ([c9f2ad8](https://github.com/mendersoftware/mender-server-enterprise/commit/c9f2ad830e8b3763fb00b5dd11e69bedadd3bcdc))  by @merlin-northern






- Add `bytesprocessed` field to accesslog entries
 ([11c11d5](https://github.com/mendersoftware/mender-server-enterprise/commit/11c11d54a55c721aa23c44ed88b30fedd6084e40))  by @alfrunes




  The `bytesprocessed` field reflects the number of bytes consumed from
  the request body.




### Refactor


- *(deployments)* Rename GetDeploymentIDsByArtifactNames
([MEN-8923](https://northerntech.atlassian.net/browse/MEN-8923)) ([fd9137e](https://github.com/mendersoftware/mender-server-enterprise/commit/fd9137eee0e63c2a52ebf13bdc9864ec7b3388fe))  by @frodeha





  Rename GetDeploymentIDsByArtifactNames to GetActiveDeploymentIDsByArtifactNames to
  better reflect that only artifact names of active deployments are
  searched.

- *(deployments)* Consolidate generate delta jobs and details
 ([885f9b1](https://github.com/mendersoftware/mender-server-enterprise/commit/885f9b11cc7037946ee619112b9f70fd61cb9d88))  by @alfrunes







### Security


- Bump node-forge from 1.3.1 to 1.3.2 in /frontend
 ([02a2734](https://github.com/mendersoftware/mender-server-enterprise/commit/02a27346cabf1e936f8f82362da106729b4c4ec4))  by @dependabot[bot]




  Bumps [node-forge](https://github.com/digitalbazaar/forge) from 1.3.1 to 1.3.2.
  - [Changelog](https://github.com/digitalbazaar/forge/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/digitalbazaar/forge/compare/v1.3.1...v1.3.2)
  
  
  updated-dependencies:
  - dependency-name: node-forge
    dependency-version: 1.3.2
    dependency-type: indirect
  ...
- Bump the mui group in /frontend with 3 updates
 ([b6520f9](https://github.com/mendersoftware/mender-server-enterprise/commit/b6520f9d9ca70dec8dbfcc7f1677fb1b2626dd17))  by @dependabot[bot]




  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.4 to 7.3.5
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.5/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.4 to 7.3.5
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.5/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.16.0 to 8.19.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.19.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.19.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump @playwright/test
 ([d37c563](https://github.com/mendersoftware/mender-server-enterprise/commit/d37c563978cd065db93f82756d43b172726df9f8))  by @dependabot[bot]




  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.56.1 to 1.57.0
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.56.1...v1.57.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.57.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump the e2e-test-dependencies group
 ([79ce5c0](https://github.com/mendersoftware/mender-server-enterprise/commit/79ce5c06ee2c8b64b2d653246b6b2c171580977c))  by @dependabot[bot]




  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 3 updates: [inquirer](https://github.com/SBoudrias/Inquirer.js), [validator](https://github.com/validatorjs/validator.js) and [yaml](https://github.com/eemeli/yaml).
  
  
  Updates `inquirer` from 12.10.0 to 13.0.1
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@12.10.0...inquirer@13.0.1)
  
  Updates `validator` from 13.15.20 to 13.15.23
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.20...13.15.23)
  
  Updates `yaml` from 2.8.1 to 2.8.2
  - [Release notes](https://github.com/eemeli/yaml/releases)
  - [Commits](https://github.com/eemeli/yaml/compare/v2.8.1...v2.8.2)
  
  ---
  updated-dependencies:
  - dependency-name: inquirer
    dependency-version: 13.0.1
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: e2e-test-dependencies
  - dependency-name: validator
    dependency-version: 13.15.23
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: yaml
    dependency-version: 2.8.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  ...
- Bump node in /frontend
 ([7d80f97](https://github.com/mendersoftware/mender-server-enterprise/commit/7d80f9750af574d2109b8986fa9cfa31107e7f4e))  by @dependabot[bot]




  Bumps node from 24.11.0-alpine3.22 to 25.2.1-alpine3.22.
  
  ---
  updated-dependencies:
  - dependency-name: node
    dependency-version: 25.2.1-alpine3.22
    dependency-type: direct:production
    update-type: version-update:semver-major
  ...
- Bump express from 4.21.1 to 4.22.1 in /frontend/tests/e2e_tests
 ([fccca78](https://github.com/mendersoftware/mender-server-enterprise/commit/fccca78112f5c374984403e814666faffd440bf2))  by @dependabot[bot]




  Bumps [express](https://github.com/expressjs/express) from 4.21.1 to 4.22.1.
  - [Release notes](https://github.com/expressjs/express/releases)
  - [Changelog](https://github.com/expressjs/express/blob/v4.22.1/History.md)
  - [Commits](https://github.com/expressjs/express/compare/4.21.1...v4.22.1)
  
  ---
  updated-dependencies:
  - dependency-name: express
    dependency-version: 4.22.1
    dependency-type: indirect
  ...
- Bump validator from 13.15.20 to 13.15.23 in /frontend
 ([358ea27](https://github.com/mendersoftware/mender-server-enterprise/commit/358ea27f761edb79f22e190ae63f7736b196f955))  by @dependabot[bot]




  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.20 to 13.15.23.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.20...13.15.23)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.23
    dependency-type: direct:production
  ...
- Bump the production-dependencies group across 1 directory with 7 updates
 ([a78af2c](https://github.com/mendersoftware/mender-server-enterprise/commit/a78af2c90dde238613c205b8c56111f6de40defd))  by @dependabot[bot]




  Bumps the production-dependencies group with 7 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.9.2` | `2.11.0` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `10.22.0` | `10.28.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `5.3.0` | `5.4.1` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `8.2.0` | `8.5.3` |
  | [axios](https://github.com/axios/axios) | `1.13.1` | `1.13.2` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.66.0` | `7.67.0` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.9.5` | `7.10.0` |
  
  
  
  Updates `@reduxjs/toolkit` from 2.9.2 to 2.11.0
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.9.2...v2.11.0)
  
  Updates `@sentry/react` from 10.22.0 to 10.28.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/10.28.0/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/10.22.0...10.28.0)
  
  Updates `@stripe/react-stripe-js` from 5.3.0 to 5.4.1
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v5.3.0...v5.4.1)
  
  Updates `@stripe/stripe-js` from 8.2.0 to 8.5.3
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v8.2.0...v8.5.3)
  
  Updates `axios` from 1.13.1 to 1.13.2
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.13.1...v1.13.2)
  
  Updates `react-hook-form` from 7.66.0 to 7.67.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.66.0...v7.67.0)
  
  Updates `react-router-dom` from 7.9.5 to 7.10.0
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.10.0/packages/react-router-dom)
  
  ---
  updated-dependencies:
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 10.28.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 5.4.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 8.5.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.13.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.67.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.10.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  ...
- Bump the development-dependencies group across 1 directory with 15 updates
 ([68ed960](https://github.com/mendersoftware/mender-server-enterprise/commit/68ed96028a4e8ab33d18b6cca3c3bc5ed93af079))  by @dependabot[bot]




  Bumps the development-dependencies group with 14 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.6.0` | `1.6.6` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.6.1` | `1.6.6` |
  | [@rspack/plugin-react-refresh](https://github.com/rspack-contrib/rspack-plugin-react-refresh) | `1.5.2` | `1.5.3` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `4.6.0` | `4.6.1` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.10.0` | `24.10.1` |
  | [@types/react](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/react) | `19.2.2` | `19.2.7` |
  | [@types/react-dom](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/react-dom) | `19.2.2` | `19.2.3` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.1.0` | `5.1.1` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `4.0.12` | `4.0.15` |
  | [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) | `3.46.0` | `3.47.0` |
  | [jsdom](https://github.com/jsdom/jsdom) | `27.0.0` | `27.2.0` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `16.2.6` | `16.2.7` |
  | [msw](https://github.com/mswjs/msw) | `2.12.1` | `2.12.3` |
  | [prettier](https://github.com/prettier/prettier) | `3.6.2` | `3.7.4` |
  
  
  
  Updates `@rspack/cli` from 1.6.0 to 1.6.6
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.6.6/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.6.1 to 1.6.6
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.6.6/packages/rspack)
  
  Updates `@rspack/plugin-react-refresh` from 1.5.2 to 1.5.3
  - [Release notes](https://github.com/rspack-contrib/rspack-plugin-react-refresh/releases)
  - [Commits](https://github.com/rspack-contrib/rspack-plugin-react-refresh/compare/v1.5.2...v1.5.3)
  
  Updates `@sentry/webpack-plugin` from 4.6.0 to 4.6.1
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/4.6.0...4.6.1)
  
  Updates `@types/node` from 24.10.0 to 24.10.1
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@types/react` from 19.2.2 to 19.2.7
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/react)
  
  Updates `@types/react-dom` from 19.2.2 to 19.2.3
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/react-dom)
  
  Updates `@vitejs/plugin-react` from 5.1.0 to 5.1.1
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.1.1/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 4.0.12 to 4.0.15
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.15/packages/coverage-v8)
  
  Updates `core-js` from 3.46.0 to 3.47.0
  - [Release notes](https://github.com/zloirock/core-js/releases)
  - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/zloirock/core-js/commits/v3.47.0/packages/core-js)
  
  Updates `jsdom` from 27.0.0 to 27.2.0
  - [Release notes](https://github.com/jsdom/jsdom/releases)
  - [Changelog](https://github.com/jsdom/jsdom/blob/main/Changelog.md)
  - [Commits](https://github.com/jsdom/jsdom/compare/27.0.0...27.2.0)
  
  Updates `lint-staged` from 16.2.6 to 16.2.7
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v16.2.6...v16.2.7)
  
  Updates `msw` from 2.12.1 to 2.12.3
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.12.1...v2.12.3)
  
  Updates `prettier` from 3.6.2 to 3.7.4
  - [Release notes](https://github.com/prettier/prettier/releases)
  - [Changelog](https://github.com/prettier/prettier/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/prettier/prettier/compare/3.6.2...3.7.4)
  
  Updates `vitest` from 4.0.12 to 4.0.15
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.15/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.6.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.6.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/plugin-react-refresh"
    dependency-version: 1.5.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.6.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.10.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/react"
    dependency-version: 19.2.7
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/react-dom"
    dependency-version: 19.2.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.1.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 4.0.15
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.47.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: jsdom
    dependency-version: 27.2.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.2.7
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.12.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: prettier
    dependency-version: 3.7.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 4.0.15
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([b2ac870](https://github.com/mendersoftware/mender-server-enterprise/commit/b2ac870e0f1fac66a78b717330362db6ddda5195))  by @dependabot[bot]




  Bumps the backend-golang-dependencies group in /backend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.19.1` | `1.20.0` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.39.5` | `1.40.0` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.16` | `1.32.2` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.18.20` | `1.19.2` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.8` | `1.69.13` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.9` | `1.32.14` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.89.1` | `1.92.1` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.12.1` | `2.12.2` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.16.0` | `9.17.2` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.19.1 to 1.20.0
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.19.1...sdk/azcore/v1.20.0)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.39.5 to 1.40.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.39.5...v1.40.0)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.16 to 1.32.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.16...v1.32.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.20 to 1.19.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.20...service/m2/v1.19.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.8 to 1.69.13
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.8...service/iot/v1.69.13)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.9 to 1.32.14
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/mgn/v1.32.9...service/mgn/v1.32.14)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.89.1 to 1.92.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.89.1...service/s3/v1.92.1)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.12.1 to 2.12.2
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.12.1...v2.12.2)
  
  Updates `github.com/redis/go-redis/v9` from 9.16.0 to 9.17.2
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/v9.17.2/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.16.0...v9.17.2)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.20.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.32.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.19.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.13
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.14
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.92.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.17.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bumped openapi-generator version
 ([bb7fe70](https://github.com/mendersoftware/mender-server-enterprise/commit/bb7fe704af1634ba9164816014ab4cec09944dc1))  by @mzedel


- Bump the backend-tests-python-dependencies group across 1 directory with 9 updates
 ([be7ba09](https://github.com/mendersoftware/mender-server-enterprise/commit/be7ba09f4ae0a56451264226ab2374bb26208b59))  by @dependabot[bot]




  Bumps the backend-tests-python-dependencies group with 9 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [pytest](https://github.com/pytest-dev/pytest) | `8.4.2` | `9.0.1` |
  | [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.15.3` | `4.15.4` |
  | [certifi](https://github.com/certifi/python-certifi) | `2025.10.5` | `2025.11.12` |
  | [urllib3](https://github.com/urllib3/urllib3) | `2.3.0` | `2.5.0` |
  | [boto3](https://github.com/boto/boto3) | `1.40.64` | `1.42.0` |
  | [execnet](https://github.com/pytest-dev/execnet) | `2.1.1` | `2.1.2` |
  | [stripe](https://github.com/stripe/stripe-python) | `13.1.1` | `14.0.1` |
  | [redis](https://github.com/redis/redis-py) | `7.0.1` | `7.1.0` |
  | [pydantic](https://github.com/pydantic/pydantic) | `2.12.3` | `2.12.5` |
  
  
  
  Updates `pytest` from 8.4.2 to 9.0.1
  - [Release notes](https://github.com/pytest-dev/pytest/releases)
  - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest/compare/8.4.2...9.0.1)
  
  Updates `pymongo` from 4.15.3 to 4.15.4
  - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
  - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
  - [Commits](https://github.com/mongodb/mongo-python-driver/compare/4.15.3...4.15.4)
  
  Updates `certifi` from 2025.10.5 to 2025.11.12
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.10.05...2025.11.12)
  
  Updates `urllib3` from 2.3.0 to 2.5.0
  - [Release notes](https://github.com/urllib3/urllib3/releases)
  - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
  - [Commits](https://github.com/urllib3/urllib3/compare/2.3.0...2.5.0)
  
  Updates `boto3` from 1.40.64 to 1.42.0
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.64...1.42.0)
  
  Updates `execnet` from 2.1.1 to 2.1.2
  - [Changelog](https://github.com/pytest-dev/execnet/blob/master/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/execnet/compare/v2.1.1...v2.1.2)
  
  Updates `stripe` from 13.1.1 to 14.0.1
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v13.1.1...v14.0.1)
  
  Updates `redis` from 7.0.1 to 7.1.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v7.0.1...v7.1.0)
  
  Updates `pydantic` from 2.12.3 to 2.12.5
  - [Release notes](https://github.com/pydantic/pydantic/releases)
  - [Changelog](https://github.com/pydantic/pydantic/blob/main/HISTORY.md)
  - [Commits](https://github.com/pydantic/pydantic/compare/v2.12.3...v2.12.5)
  
  ---
  updated-dependencies:
  - dependency-name: pytest
    dependency-version: 9.0.1
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.15.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.11.12
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: urllib3
    dependency-version: 2.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: execnet
    dependency-version: 2.1.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 14.0.1
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 7.1.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pydantic
    dependency-version: 2.12.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump golang container image to 1.25.5
 ([7f700b7](https://github.com/mendersoftware/mender-server-enterprise/commit/7f700b7c20381232299f848285eaac4c78b5ecb3))  by @alfrunes






### Revert


- Feat(pkg): added request content length to access logs
 ([5ef9bbd](https://github.com/mendersoftware/mender-server-enterprise/commit/5ef9bbd626a09b35f1879f1292511d3938f2efbe))  by @alfrunes




  Reverting in favor of logging the number of bytes processed.
  
  This reverts commit 137da33ab3056aa80eca0dc4226dddd24b84e7bc.





## v4.1.0-saas.21 - 2025-11-27


### Bug fixes

* **tenantadm:** fix default device limits for enterprise plan ([28b8980](https://github.com/mendersoftware/mender-server-enterprise/commit/28b89803c2573ea60de2abd9ef51ee51de245444))
* **tenantadm:** fix default device limits for enterprise plan ([e83f368](https://github.com/mendersoftware/mender-server-enterprise/commit/e83f368fd657e2b9a87b472c68978544130385ec))

- *(tenantadm)* Fix default device limits for enterprise plan
([MEN-9049](https://northerntech.atlassian.net/browse/MEN-9049)) ([e83f368](https://github.com/mendersoftware/mender-server-enterprise/commit/e83f368fd657e2b9a87b472c68978544130385ec)) 


  There is no support for `-1` as device limit in the UI yet, so we should
  use 0 (which means no limit, same as -1) as a default limit for standard
  devices.
 
- *(deployments)* Replace counters with queues to solve consistency errors
([MEN-7704](https://northerntech.atlassian.net/browse/MEN-7704)) ([3d65fa2](https://github.com/mendersoftware/mender-server-enterprise/commit/3d65fa2985b3c66f4b178ce9106d9e27856487a6))  by @alfrunes


  There are a number of race conditions and errors that could lead to
  permanent errors in the counters. By replacing the counters with queues,
  we should be able to resolve inconsistencies by handling stale jobs
  reliably.

- *(deployments)* Add staleness check to delta jobs for checkUpdate
 ([7fdb493](https://github.com/mendersoftware/mender-server-enterprise/commit/7fdb493cfdb7105a178c0b21e9aa2bd6ac6de421))  by @alfrunes

- *(deployments)* Try to schedule stale jobs when jobs finish
 ([9bf0ce2](https://github.com/mendersoftware/mender-server-enterprise/commit/9bf0ce2bc41f5aa9938e5b69f1a8fc33579786cb))  by @alfrunes

- *(deployments)* Remove delta job TTL to prevent disappearing status
([MEN-8981](https://northerntech.atlassian.net/browse/MEN-8981)) ([bc4c823](https://github.com/mendersoftware/mender-server-enterprise/commit/bc4c8231eb926e73540096669606e7fd7256348a))  by @alfrunes

- *(gui)* Fixed pagination in device search results
([MEN-8196](https://northerntech.atlassian.net/browse/MEN-8196)) ([62c4de2](https://github.com/mendersoftware/mender-server-enterprise/commit/62c4de2b2a73c22bac716a368e6b70701fa5b652))  by @mineralsfree

- *(useradm)* Handle tenant not found in login endpoints
 ([cc35fac](https://github.com/mendersoftware/mender-server-enterprise/commit/cc35fac4a77bd74bff1e84667c11b5d6ec9c1156)) 

- *(useradm)* Migration ensuring unique read-only SSO configuration
([MEN-8938](https://northerntech.atlassian.net/browse/MEN-8938)) ([1f59cd3](https://github.com/mendersoftware/mender-server-enterprise/commit/1f59cd32ff17699016cee00056fa87c84d5a6e6c)) 


  The migration builds on top of 2416a39b6610183c712a11b9b5918e0d0069ac22
  ensuring that tenants that inherit SSO configuration cannot create a new
  SSO configuration.

- Introduce docker-compose healthcheck for mongo, nats and traefik
 ([e3aea0b](https://github.com/mendersoftware/mender-server-enterprise/commit/e3aea0bd890ac71c18ba08be9e80dd59b4ad3da5))  by @joelguittet


  Introducing healthcheck allow to monitor services.
  This permits a better dependency when mender services are starting,
  waiting for mongo, nats, traefik to be heatlhy before starting.
- Increase docker-compose restart
 ([d687f66](https://github.com/mendersoftware/mender-server-enterprise/commit/d687f664183da924d5be642c6ced14ebe0e5dfd5))  by @joelguittet


  Some services still fails after the introduction of the healthcheck on
  slow machines. Increase the number restarts allowed to solve it, no
  better mechanisms found.
- Service provider children properly inherits sso configuration
 ([1f1d731](https://github.com/mendersoftware/mender-server-enterprise/commit/1f1d731efff47e958455ecbeac6c5b422b4574e2)) 


  By setting the `source_tenant_id` parameter when creating a new tenant
  from a service provider, makes the created tenant properly inherit the
  SSO configuration from the parent. The SSO configuration can only be
  modified by the service provider, rendering the
  `restrict_to_parent_tenant` parameter practically always `true`.


### Documentation


- *(deployments)* Aligned update meta_data example with schema definition
 ([bf16c73](https://github.com/mendersoftware/mender-server-enterprise/commit/bf16c73192800aae538348d752f824b3771e7db1))  by @mzedel

- *(deployments)* Aligned artifact_too_big schema w/ rest of docs
 ([db35fca](https://github.com/mendersoftware/mender-server-enterprise/commit/db35fca1333e3f4e8305dc9d554c5339333ed2e3))  by @mzedel

- *(deployments)* Add artifact_too_big device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([da06093](https://github.com/mendersoftware/mender-server-enterprise/commit/da0609333b510e508047e330207e9b9c4c552c13)) 

- *(useradm)* Fixed an issue that prevented generating a user information response example
 ([79650ca](https://github.com/mendersoftware/mender-server-enterprise/commit/79650ca4a1f4aac8ea6a1b7a39776c1a61cc3756))  by @mzedel

- *(useradm)* Update documentation for creating tenant
([MEN-8938](https://northerntech.atlassian.net/browse/MEN-8938)) ([cb94161](https://github.com/mendersoftware/mender-server-enterprise/commit/cb941619696a6fdd1de32145fb425a57035d1aca)) 

  - the schema types in the allOf need to be the same for this to apply
  - removed ineffective `restrict_to_parent_sso` parameter and updated the
  description for `sso`

- Add documentation that `retries` is restricted to professional and enterprise plans
 ([02e404a](https://github.com/mendersoftware/mender-server-enterprise/commit/02e404a7e1754c02450bf762ef268d69b9ca52a2))  by @nickanderson




### Features


- *(deployments)* Limit max deployment artifact size for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([54a4f0d](https://github.com/mendersoftware/mender-server-enterprise/commit/54a4f0da572e0499a8f62cdc693e7877b1afa471)) 

- *(deployments)* Rate limit new device deployments globally
([MEN-8943](https://northerntech.atlassian.net/browse/MEN-8943)) ([4a5f1f2](https://github.com/mendersoftware/mender-server-enterprise/commit/4a5f1f27a4d318099cf74f69342783d6852de5fd))  by @frodeha

- *(pkg)* Added request content length to access logs
([MEN-8935](https://northerntech.atlassian.net/browse/MEN-8935)) ([137da33](https://github.com/mendersoftware/mender-server-enterprise/commit/137da33ab3056aa80eca0dc4226dddd24b84e7bc))  by @frodeha

- *(deviceauth)* Internal endpoints for device limits
([MEN-8904](https://northerntech.atlassian.net/browse/MEN-8904)) ([66f2a77](https://github.com/mendersoftware/mender-server-enterprise/commit/66f2a778b8793bd9eb3855b14902fee76a099756)) 

- *(tenantadm)* Configure default device limits for tiers in plans
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([2af153d](https://github.com/mendersoftware/mender-server-enterprise/commit/2af153dc98b44d72fc2b578084ca6fdfa811400b))  by @frodeha

  Support for all device tiers for set, get, delete operations.

- *(tenantadm)* Set limits for all tiers when creating organization
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([7d4d760](https://github.com/mendersoftware/mender-server-enterprise/commit/7d4d760a37c584b64716d04a79a3cf43873d78cc))  by @frodeha

- *(tenantadm)* Override device tier limits in create organization cli
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([fe60c4b](https://github.com/mendersoftware/mender-server-enterprise/commit/fe60c4b5f952024f6d8dc430de572f947c6d4a44))  by @frodeha

- *(deviceauth)* Adjusted rate limits to account for device tier
 ([6e6c73f](https://github.com/mendersoftware/mender-server-enterprise/commit/6e6c73f18ee750444864f20167030868abb7b847)) 


  The new device tier for standard devices are:
   - 15 requests/minute for checkUpdate
   - 15 requests/minute for submitInventory
   - 30 requests/minute for all other operations
  
   For micro device tier the ratelimits are:
   - 1 request/day for checkUpdate
   - 1 requests/14days for submitInventory
   - 30 requests/day for all other operations

- *(pkg)* Added request content length to access logs
([MEN-8935](https://northerntech.atlassian.net/browse/MEN-8935)) ([137da33](https://github.com/mendersoftware/mender-server-enterprise/commit/137da33ab3056aa80eca0dc4226dddd24b84e7bc)) 

- *(tenantadm)* Device tier limits support for create_organization workflow
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([00996c8](https://github.com/mendersoftware/mender-server-enterprise/commit/00996c8a8e385fd9bca7763aa82e88cccc994c7c)) 

- *(useradm)* Send audit email to all admin on SSO configuration change
([MEN-8971](https://northerntech.atlassian.net/browse/MEN-8971)) ([fc6be43](https://github.com/mendersoftware/mender-server-enterprise/commit/fc6be43363ca8300fd541a50c2bd6ef694871fee))  by @alfrunes


  When a user updates the single sign-on configuration for their account,
  a security notification is sent to all admin user emails.

- *(workflows)* Add device tier limits to create_organization workflows
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([fd4d469](https://github.com/mendersoftware/mender-server-enterprise/commit/fd4d469e9f896e6f90a95da47862000b6dbabb29)) 

- New flag `--tenant-token` for `create-org` CLI command
([MEN-7901](https://northerntech.atlassian.net/browse/MEN-7901)) ([5df75ff](https://github.com/mendersoftware/mender-server-enterprise/commit/5df75ff970d27326d7507402e233af61262463d4)) 


  The new flag sets the tenant-token to a given string.
  Primarily useful in tests.

- Update traefik version
 ([106f570](https://github.com/mendersoftware/mender-server-enterprise/commit/106f570bc67613071f276bb69dad42ba47d83d07))  by @joelguittet


  Update of traefik version to support Docker 29.x with API >= 1.44.




### Refactor


- *(tenantadm)* Make trial filter parameter explicitly bool
 ([6ddb347](https://github.com/mendersoftware/mender-server-enterprise/commit/6ddb34756faab816c286b5354c1807adfb7d821d))  by @alfrunes

- *(tenantadm)* Add Stripe status filter to list subscriptions
 ([e835f1c](https://github.com/mendersoftware/mender-server-enterprise/commit/e835f1c33ba87eb1b32bae3a25ea3ab9ba9d61ed))  by @alfrunes

- *(useradm)* Consolidate SSO metadata API handlers
 ([2bf2446](https://github.com/mendersoftware/mender-server-enterprise/commit/2bf2446972716708c45410cfa42f5f5279718677))  by @alfrunes





### Security


- Bump the development-dependencies group
 ([8106551](https://github.com/mendersoftware/mender-server-enterprise/commit/8106551ac73545156cffb71a22a8bd168551fb26))  by @dependabot[bot]


  Bumps the development-dependencies group in /frontend with 17 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/types](https://github.com/NorthernTechHQ/nt-gui) | `0.2.1` | `0.2.2` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.5.8` | `1.6.0` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.5.8` | `1.6.0` |
  | [@rspack/plugin-react-refresh](https://github.com/rspack-contrib/rspack-plugin-react-refresh) | `1.5.1` | `1.5.2` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `4.3.0` | `4.6.0` |
  | [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) | `6.9.0` | `6.9.1` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.6.1` | `24.9.2` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.0.4` | `5.1.0` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `3.2.4` | `4.0.6` |
  | [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) | `3.45.1` | `3.46.0` |
  | [esbuild-loader](https://github.com/privatenumber/esbuild-loader) | `4.3.0` | `4.4.0` |
  | [eslint](https://github.com/eslint/eslint) | `9.36.0` | `9.39.0` |
  | [globals](https://github.com/sindresorhus/globals) | `16.4.0` | `16.5.0` |
  | [jsdom](https://github.com/jsdom/jsdom) | `27.0.0` | `27.1.0` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `16.2.3` | `16.2.6` |
  | [msw](https://github.com/mswjs/msw) | `2.11.3` | `2.11.6` |
  | [vitest](https://github.com/vitest-dev/vitest/tree/HEAD/packages/vitest) | `3.2.4` | `4.0.6` |
  
  Updates `@northern.tech/types` from 0.2.1 to 0.2.2
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/types-0.2.1...@northern.tech/types-0.2.2)
  
  Updates `@rspack/cli` from 1.5.8 to 1.6.0
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.6.0/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.5.8 to 1.6.0
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.6.0/packages/rspack)
  
  Updates `@rspack/plugin-react-refresh` from 1.5.1 to 1.5.2
  - [Release notes](https://github.com/rspack-contrib/rspack-plugin-react-refresh/releases)
  - [Commits](https://github.com/rspack-contrib/rspack-plugin-react-refresh/compare/v1.5.1...v1.5.2)
  
  Updates `@sentry/webpack-plugin` from 4.3.0 to 4.6.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/4.3.0...4.6.0)
  
  Updates `@testing-library/jest-dom` from 6.9.0 to 6.9.1
  - [Release notes](https://github.com/testing-library/jest-dom/releases)
  - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/jest-dom/compare/v6.9.0...v6.9.1)
  
  Updates `@types/node` from 24.6.1 to 24.9.2
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@vitejs/plugin-react` from 5.0.4 to 5.1.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.1.0/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 3.2.4 to 4.0.6
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.6/packages/coverage-v8)
  
  Updates `core-js` from 3.45.1 to 3.46.0
  - [Release notes](https://github.com/zloirock/core-js/releases)
  - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/zloirock/core-js/commits/v3.46.0/packages/core-js)
  
  Updates `esbuild-loader` from 4.3.0 to 4.4.0
  - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
  - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v4.3.0...v4.4.0)
  
  Updates `eslint` from 9.36.0 to 9.39.0
  - [Release notes](https://github.com/eslint/eslint/releases)
  - [Commits](https://github.com/eslint/eslint/compare/v9.36.0...v9.39.0)
  
  Updates `globals` from 16.4.0 to 16.5.0
  - [Release notes](https://github.com/sindresorhus/globals/releases)
  - [Commits](https://github.com/sindresorhus/globals/compare/v16.4.0...v16.5.0)
  
  Updates `jsdom` from 27.0.0 to 27.1.0
  - [Release notes](https://github.com/jsdom/jsdom/releases)
  - [Changelog](https://github.com/jsdom/jsdom/blob/main/Changelog.md)
  - [Commits](https://github.com/jsdom/jsdom/compare/27.0.0...27.1.0)
  
  Updates `lint-staged` from 16.2.3 to 16.2.6
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v16.2.3...v16.2.6)
  
  Updates `msw` from 2.11.3 to 2.11.6
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.11.3...v2.11.6)
  
  Updates `vitest` from 3.2.4 to 4.0.6
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v4.0.6/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/types"
    dependency-version: 0.2.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.6.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.6.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/plugin-react-refresh"
    dependency-version: 1.5.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.6.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/jest-dom"
    dependency-version: 6.9.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.9.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.1.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 4.0.6
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.46.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: esbuild-loader
    dependency-version: 4.4.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: eslint
    dependency-version: 9.39.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: globals
    dependency-version: 16.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: jsdom
    dependency-version: 27.1.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.2.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.11.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 4.0.6
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  ...
- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([26854ec](https://github.com/mendersoftware/mender-server-enterprise/commit/26854ec71cfb181948696f1bbb0d5505114306c9))  by @dependabot[bot]


  Bumps the backend-docker-dependencies group with 2 updates in the /backend/services/create-artifact-worker directory: golang and alpine.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `alpine` from 3.22.1 to 3.22.2
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 17 updates
 ([2cae646](https://github.com/mendersoftware/mender-server-enterprise/commit/2cae6466e34d2928760bcb6a55df3f351b63d33b))  by @dependabot[bot]


  Bumps the backend-tests-python-dependencies group with 17 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [attrs](https://github.com/sponsors/hynek) | `25.3.0` | `25.4.0` |
  | [boto3](https://github.com/boto/boto3) | `1.40.24` | `1.40.58` |
  | [certifi](https://github.com/certifi/python-certifi) | `2025.8.3` | `2025.10.5` |
  | [cffi](https://github.com/python-cffi/cffi) | `1.17.1` | `2.0.0` |
  | [cryptography](https://github.com/pyca/cryptography) | `45.0.7` | `46.0.3` |
  | [filelock](https://github.com/tox-dev/py-filelock) | `3.19.1` | `3.20.0` |
  | [idna](https://github.com/kjd/idna) | `3.10` | `3.11` |
  | [iniconfig](https://github.com/pytest-dev/iniconfig) | `2.1.0` | `2.3.0` |
  | [kubernetes](https://github.com/kubernetes-client/python) | `33.1.0` | `34.1.0` |
  | [pillow](https://github.com/python-pillow/Pillow) | `11.3.0` | `12.0.0` |
  | [pycparser](https://github.com/eliben/pycparser) | `2.22` | `2.23` |
  | [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.14.1` | `4.15.3` |
  | [pyparsing](https://github.com/pyparsing/pyparsing) | `3.2.3` | `3.2.5` |
  | [pyyaml](https://github.com/yaml/pyyaml) | `6.0.2` | `6.0.3` |
  | [stripe](https://github.com/stripe/stripe-python) | `12.5.0` | `13.0.1` |
  | [redis](https://github.com/redis/redis-py) | `6.4.0` | `7.0.0` |
  | [pydantic](https://github.com/pydantic/pydantic) | `2.11.7` | `2.12.3` |
  
  
  
  Updates `attrs` from 25.3.0 to 25.4.0
  - [Commits](https://github.com/sponsors/hynek/commits)
  
  Updates `boto3` from 1.40.24 to 1.40.58
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.24...1.40.58)
  
  Updates `certifi` from 2025.8.3 to 2025.10.5
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.08.03...2025.10.05)
  
  Updates `cffi` from 1.17.1 to 2.0.0
  - [Release notes](https://github.com/python-cffi/cffi/releases)
  - [Commits](https://github.com/python-cffi/cffi/compare/v1.17.1...v2.0.0)
  
  Updates `cryptography` from 45.0.7 to 46.0.3
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.7...46.0.3)
  
  Updates `filelock` from 3.19.1 to 3.20.0
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.19.1...3.20.0)
  
  Updates `idna` from 3.10 to 3.11
  - [Release notes](https://github.com/kjd/idna/releases)
  - [Changelog](https://github.com/kjd/idna/blob/master/HISTORY.rst)
  - [Commits](https://github.com/kjd/idna/compare/v3.10...v3.11)
  
  Updates `iniconfig` from 2.1.0 to 2.3.0
  - [Release notes](https://github.com/pytest-dev/iniconfig/releases)
  - [Changelog](https://github.com/pytest-dev/iniconfig/blob/main/CHANGELOG)
  - [Commits](https://github.com/pytest-dev/iniconfig/compare/v2.1.0...v2.3.0)
  
  Updates `kubernetes` from 33.1.0 to 34.1.0
  - [Release notes](https://github.com/kubernetes-client/python/releases)
  - [Changelog](https://github.com/kubernetes-client/python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/kubernetes-client/python/compare/v33.1.0...v34.1.0)
  
  Updates `pillow` from 11.3.0 to 12.0.0
  - [Release notes](https://github.com/python-pillow/Pillow/releases)
  - [Changelog](https://github.com/python-pillow/Pillow/blob/main/CHANGES.rst)
  - [Commits](https://github.com/python-pillow/Pillow/compare/11.3.0...12.0.0)
  
  Updates `pycparser` from 2.22 to 2.23
  - [Release notes](https://github.com/eliben/pycparser/releases)
  - [Changelog](https://github.com/eliben/pycparser/blob/main/CHANGES)
  - [Commits](https://github.com/eliben/pycparser/compare/release_v2.22...release_v2.23)
  
  Updates `pymongo` from 4.14.1 to 4.15.3
  - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
  - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
  - [Commits](https://github.com/mongodb/mongo-python-driver/compare/4.14.1...4.15.3)
  
  Updates `pyparsing` from 3.2.3 to 3.2.5
  - [Release notes](https://github.com/pyparsing/pyparsing/releases)
  - [Changelog](https://github.com/pyparsing/pyparsing/blob/master/CHANGES)
  - [Commits](https://github.com/pyparsing/pyparsing/compare/3.2.3...3.2.5)
  
  Updates `pyyaml` from 6.0.2 to 6.0.3
  - [Release notes](https://github.com/yaml/pyyaml/releases)
  - [Changelog](https://github.com/yaml/pyyaml/blob/6.0.3/CHANGES)
  - [Commits](https://github.com/yaml/pyyaml/compare/6.0.2...6.0.3)
  
  Updates `stripe` from 12.5.0 to 13.0.1
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.5.0...v13.0.1)
  
  Updates `redis` from 6.4.0 to 7.0.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v6.4.0...v7.0.0)
  
  Updates `pydantic` from 2.11.7 to 2.12.3
  - [Release notes](https://github.com/pydantic/pydantic/releases)
  - [Changelog](https://github.com/pydantic/pydantic/blob/main/HISTORY.md)
  - [Commits](https://github.com/pydantic/pydantic/compare/v2.11.7...v2.12.3)
  
  ---
  updated-dependencies:
  - dependency-name: attrs
    dependency-version: 25.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.58
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.10.5
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cffi
    dependency-version: 2.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 46.0.3
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: filelock
    dependency-version: 3.20.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: idna
    dependency-version: '3.11'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: iniconfig
    dependency-version: 2.3.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: kubernetes
    dependency-version: 34.1.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pillow
    dependency-version: 12.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pycparser
    dependency-version: '2.23'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.15.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pyparsing
    dependency-version: 3.2.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pyyaml
    dependency-version: 6.0.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 13.0.1
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 7.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pydantic
    dependency-version: 2.12.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump js-yaml from 4.1.0 to 4.1.1 in /frontend
 ([b0b6165](https://github.com/mendersoftware/mender-server-enterprise/commit/b0b6165551dce4310f78b63d6081ca0ae35f8d5f))  by @dependabot[bot]


  Bumps [js-yaml](https://github.com/nodeca/js-yaml) from 4.1.0 to 4.1.1.
  - [Changelog](https://github.com/nodeca/js-yaml/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/nodeca/js-yaml/compare/4.1.0...4.1.1)
  
  ---
  updated-dependencies:
  - dependency-name: js-yaml
    dependency-version: 4.1.1
    dependency-type: indirect
  ...
- Bump golang.org/x/crypto from 0.43.0 to 0.45.0 in /backend
 ([8981e10](https://github.com/mendersoftware/mender-server-enterprise/commit/8981e10742a4e097df46534fe5c314bc11ea2de7))  by @dependabot[bot]


  Bumps [golang.org/x/crypto](https://github.com/golang/crypto) from 0.43.0 to 0.45.0.
  - [Commits](https://github.com/golang/crypto/compare/v0.43.0...v0.45.0)
  
  ---
  updated-dependencies:
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.45.0
    dependency-type: direct:production
  ...






## 4.1.0-saas.19 - 2025-11-12


### Bug fixes


- *(gui)* Increased reliance on theme defined button colors to align more w/ updated theme
 ([28cd0fd](https://github.com/mendersoftware/mender-server-enterprise/commit/28cd0fd1a2e5c976d16769a25daff75125748035))  by @mzedel

- *(useradm)* Handle tenant not found in login endpoints
 ([cc35fac](https://github.com/mendersoftware/mender-server-enterprise/commit/cc35fac4a77bd74bff1e84667c11b5d6ec9c1156))  by @alfrunes

- Validate rate limit config when setting up redis
([MEN-8864](https://northerntech.atlassian.net/browse/MEN-8864)) ([39b60a7](https://github.com/mendersoftware/mender-server-enterprise/commit/39b60a7a28133ed621c8f72a0e0e9fa15e9252e4))  by @bahaa-ghazal




### Documentation


- *(deployments)* Add artifact_too_big device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([da06093](https://github.com/mendersoftware/mender-server-enterprise/commit/da0609333b510e508047e330207e9b9c4c552c13))  by @frodeha

- *(deployments)* Document 'sort' option in the internal endpoint for getting deployments
([MEN-8914](https://northerntech.atlassian.net/browse/MEN-8914)) ([7165f58](https://github.com/mendersoftware/mender-server-enterprise/commit/7165f58eec679b36e0a83f5a4d4b71595c62aa30))  by @kjaskiewiczz





### Features


- *(deployments)* Add 'artifact too big' device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([d4a2115](https://github.com/mendersoftware/mender-server-enterprise/commit/d4a21156026382d54d4d8cf6d9d0bb22e3551d7a))  by @frodeha

- *(deployments)* Add max artifact size limit for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([91a6788](https://github.com/mendersoftware/mender-server-enterprise/commit/91a678800810bea55596e0b547e3fbfe7b0ab33d))  by @frodeha

- *(deployments)* Limit max deployment artifact size for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([54a4f0d](https://github.com/mendersoftware/mender-server-enterprise/commit/54a4f0da572e0499a8f62cdc693e7877b1afa471))  by @frodeha

- *(deviceauth)* Internal endpoints for device limits
([MEN-8904](https://northerntech.atlassian.net/browse/MEN-8904)) ([66f2a77](https://github.com/mendersoftware/mender-server-enterprise/commit/66f2a778b8793bd9eb3855b14902fee76a099756))  by @merlin-northern


  Support for all device tiers for set, get, delete operations.

- *(deviceauth)* Rate limit deployments/next for micro tier devices
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([346acec](https://github.com/mendersoftware/mender-server-enterprise/commit/346acec4857be4ee659f8add445655e91b0d9b9f)) 

- *(deviceauth)* Adjusted rate limits to account for device tier
 ([6e6c73f](https://github.com/mendersoftware/mender-server-enterprise/commit/6e6c73f18ee750444864f20167030868abb7b847))  by @alfrunes


  The new device tier for standard devices are:
   - 15 requests/minute for checkUpdate
   - 15 requests/minute for submitInventory
   - 30 requests/minute for all other operations
  
   For micro device tier the ratelimits are:
   - 1 request/day for checkUpdate
   - 1 requests/14days for submitInventory
   - 30 requests/day for all other operations

- *(pkg)* Add device tier to identity
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([de321eb](https://github.com/mendersoftware/mender-server-enterprise/commit/de321ebdb4235bd1bed6d749fe5e774781137dbd)) 

- *(tenantadm)* Device tier limits support for create_organization workflow
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([00996c8](https://github.com/mendersoftware/mender-server-enterprise/commit/00996c8a8e385fd9bca7763aa82e88cccc994c7c))  by @frodeha

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([64ca71f](https://github.com/mendersoftware/mender-server-enterprise/commit/64ca71f162901bb4dce096f14da416a23495dfbc))  by @alfrunes


  Added the following configuration parameters:
  ```yaml
  rate_limits:
    # auth configures rate limits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # reject_unmatched rejects requests that does not resolve to a
      # rate limit group. That is, if either there's no api_pattern matching
      # the request or if the group_expression does not match a group.
      # Defaults to false - disable rate limiting for unmatched requests.
      reject_unmatched: false
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups:
          # name defines the name of the group. The name is used in
          # match.group_expression to match an api_pattern with a group.
        - name: default
          # interval is the time interval when the rate limiter resets.
          interval: 1m
          # quota is the number of requests allowed in an interval.
          quota: 300
          # event_expression is a go template for grouping requests.
          # The following attributes are available in the context:
          # Identity - contains a subset of the JWT claims:
          # .Subject  (jwt:"sub")          string
          # .Tenant   (jwt:"mender.tenant") string
          # .Plan     (jwt:"mender.plan")   string
          # .Addons   (jwt:"mender.addons") []struct{Enabled bool; Name string}
          # .IsUser   (jwt:"mender.user")   bool
          # .IsDevice (jwt:"mender.device") bool
          # .Trial    (jwt:"mender.trial")  bool
          event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
      match:
          # api_pattern specifies an API path pattern as defined by http.ServeMux
          # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
        - api_pattern: /
          # group_expression defines  the group for this matching expression.
          # A group can be selected dynamically using Go templates or statically
          # with a literal string.
          # See group.event_expression for template context attributes.
          group_expression: "default"
          # More example match rules:
  ```

- *(workflows)* Add device tier limits to create_organization workflows
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([fd4d469](https://github.com/mendersoftware/mender-server-enterprise/commit/fd4d469e9f896e6f90a95da47862000b6dbabb29))  by @frodeha





### Refactor


- *(ratelimits)* Move ratelimits default configs to service config
 ([f5af7f3](https://github.com/mendersoftware/mender-server-enterprise/commit/f5af7f30fdd67235a0532c0989617db9505bdc61))  by @alfrunes


  The defaults will differ so we need to decentralize them.







## 4.1.0-saas.18 - 2025-11-04


### Bug fixes


- *(gui)* Fixed an issue that prevented updating existing sso configs
 ([d022d1a](https://github.com/mendersoftware/mender-server-enterprise/commit/d022d1a78ba2f2b60cc1670b0015451c01c5734e))  by @mzedel







## 4.1.0-saas.17 - 2025-11-03


### Bug fixes


- *(deployments)* Fixed faulty delta artifact generation specs that lead to faulty client generation
 ([8aa15fd](https://github.com/mendersoftware/mender-server-enterprise/commit/8aa15fd7166403eb640d231d373832ef5def029f))  by @mzedel

- *(deployments)* Backwards compatible artifact metadata
 ([MEN-8941](https://northerntech.atlassian.net/browse/MEN-8941)) ([8110c52](https://github.com/mendersoftware/mender-server-enterprise/commit/8110c5251b1025bc00a9b7c56e42500715c477d0))  by @frodeha

- *(deployments)* Panic on database errors on DELETE /artifacts
 ([f3c9bda](https://github.com/mendersoftware/mender-server-enterprise/commit/f3c9bda8eb050ceb744f0ce7f45c58c44934c861))  by @alfrunes

- *(generate-delta-worker)* Do not expose signed url in description
 ([6538a53](https://github.com/mendersoftware/mender-server-enterprise/commit/6538a5351acf73575b2ac1c19659f1af9e70feb6)) 


  Extracts the artifact ID in the URL to avoid printing the signed URL to
  the source artifact.

- *(gui)* Fixed an issue that left notch in outlined w/o a background
 ([1673cff](https://github.com/mendersoftware/mender-server-enterprise/commit/1673cff934be78a379d9123f93317336ee83bfe0))  by @mzedel

- *(gui)* Fixed an issue that prevented closing details view of an ongoing delta generation
 ([0770333](https://github.com/mendersoftware/mender-server-enterprise/commit/07703338737f7b400198b6b58da55895d9dc2a06))  by @mzedel

- *(gui)* Removed error messages shown when subscribing or showing billing info as trial user
 ([231d4e3](https://github.com/mendersoftware/mender-server-enterprise/commit/231d4e34a0d376a2b963e4e01a4a393a975f2668))  by @mzedel


  - NB: this lets the frontend rely on trial signups to always provide a new billing profile when signing up

- *(tenantadm)* Ignore Stripe subscriptions not managed by this service
([MEN-8708](https://northerntech.atlassian.net/browse/MEN-8708)) ([4e8c712](https://github.com/mendersoftware/mender-server-enterprise/commit/4e8c71200c16210da4349667c6b6003d6ca69f05)) 


  Instead of correlating events with customer ID, we correlate with
  subscription IDs. This is mostly to address a transient issue in the
  transition phase where a multi-subscription customer will have the
  subscriptions consolidated, but it also eliminates the need for
  additional database indexing to cover fast customer lookups.

- *(useradm)* Add orchestrator client to command for getting user stats
 ([19bfb5b](https://github.com/mendersoftware/mender-server-enterprise/commit/19bfb5b4e3e4dd10aac27d961fb82d6f0e9b7578))  by @kjaskiewiczz


  Without the orchestrator client, stats will not be exported to google
  spreadsheet.

- *(useradm)* Invalidate cache when deleting PAT token
([MEN-7285](https://northerntech.atlassian.net/browse/MEN-7285)) ([e05e898](https://github.com/mendersoftware/mender-server-enterprise/commit/e05e898b7056c79aefad095b9e22f359dcfd1174)) 

- *(useradm)* Prevent race condition recaching revoked PAT token
 ([1564ec6](https://github.com/mendersoftware/mender-server-enterprise/commit/1564ec6a452c366af2ea4069340e9173669aa4db)) 





### Documentation


- *(deployments)* Mark release meta_data as deprecated
 ([33563c6](https://github.com/mendersoftware/mender-server-enterprise/commit/33563c6ac639c4fdba1471eb0c1e65e66e2e4f80))  by @frodeha

- *(deployments)* Use array type for deprecated meta_data attribute
 ([0135305](https://github.com/mendersoftware/mender-server-enterprise/commit/0135305d78d95038ff7c3bfadcdd8d34d7a8a8df))  by @alfrunes

- *(devicemonitor)* Added internal delete device endpoint to api docs
 ([85e5570](https://github.com/mendersoftware/mender-server-enterprise/commit/85e557004ec26e1ad32e3e1b296d2391ba5c9a51)) 

- *(tenantad)* Document new "updated_at" field of tenant object
([MEN-8859](https://northerntech.atlassian.net/browse/MEN-8859)) ([5266b1d](https://github.com/mendersoftware/mender-server-enterprise/commit/5266b1da670276875a44429c66647b04191fc5eb))  by @kjaskiewiczz

- *(useradm)* API documentation for user feedback endpoint
 ([6bc4c29](https://github.com/mendersoftware/mender-server-enterprise/commit/6bc4c298931e0b746ace659b6b3d375fb59c085c)) 





### Features


- *(deployments)* Added support for anthropic analysis backend
 ([0e71550](https://github.com/mendersoftware/mender-server-enterprise/commit/0e715506bb4b23b5115a56ef7d5ad5d75a057847)) 

- *(deviceauth)* Rate limit deployments/next for micro tier devices
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([346acec](https://github.com/mendersoftware/mender-server-enterprise/commit/346acec4857be4ee659f8add445655e91b0d9b9f))  by @frodeha

- *(devicemonitor)* Added internal delete device endpoint
 ([2cc83f6](https://github.com/mendersoftware/mender-server-enterprise/commit/2cc83f6883c22b092139513105c08a91e66c4484)) 

- *(gui)* Let ai request cool down time reflect reality when rate limited
 ([92e8864](https://github.com/mendersoftware/mender-server-enterprise/commit/92e8864a8c9d95991d17ad562877bc6e114ec727)) 

- *(gui)* Added execution feedback to troubleshooting device interactions
([MEN-8632](https://northerntech.atlassian.net/browse/MEN-8632)) ([e1e4074](https://github.com/mendersoftware/mender-server-enterprise/commit/e1e4074581b787e9a7bf43943aba68cf9a4a4407)) 

- *(gui)* Let tenant sso setting inheritance conditions be more explicit
([MEN-8672](https://northerntech.atlassian.net/browse/MEN-8672)) ([76d4db9](https://github.com/mendersoftware/mender-server-enterprise/commit/76d4db9a219758e21d357f487435cf106bbc62c6)) 

- *(gui)* Made it possible for tenants to allow improving ai functionality in the future
([MEN-8719](https://northerntech.atlassian.net/browse/MEN-8719)) ([c2dd114](https://github.com/mendersoftware/mender-server-enterprise/commit/c2dd114e1ec2d2eeb8b33dc300d04de04d3861cd)) 

- *(gui)* Ensured progress gets updated when monitoring a delta generation job
 ([7487d8f](https://github.com/mendersoftware/mender-server-enterprise/commit/7487d8f0dc6b921ede11ddac6ab3bae392a1ffff))  by @mzedel

- *(pkg)* Add device tier to identity
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([de321eb](https://github.com/mendersoftware/mender-server-enterprise/commit/de321ebdb4235bd1bed6d749fe5e774781137dbd))  by @frodeha

- *(tenantadm)* Register timestamp of last modification with tenant object
([MEN-8859](https://northerntech.atlassian.net/browse/MEN-8859)) ([52c3884](https://github.com/mendersoftware/mender-server-enterprise/commit/52c38840850fbf0785ac3f89d4ff6d5c0da0b579))  by @kjaskiewiczz

- *(useradm)* Email notifications on two-factor authentication changes
([MEN-8903](https://northerntech.atlassian.net/browse/MEN-8903)) ([f41f382](https://github.com/mendersoftware/mender-server-enterprise/commit/f41f3822f6cc0cf91c753c9d1d6c1f0a44f36a7a))  by @alfrunes


  An email notification is sent to the user email when the user enables or
  disables two-factor authentication.

- *(useradm)* Require consent to enable AI features
([MEN-8677](https://northerntech.atlassian.net/browse/MEN-8677)) ([909a9bd](https://github.com/mendersoftware/mender-server-enterprise/commit/909a9bd0b1c47b692014353599021d201e29a561)) 


  There is an explicit option for enabling AI features in the global
  settings (`aiFeatures.enabled`), requiring admin access to allow
  using the feature.

- *(useradm)* New endpoint for submitting user feedback
([MEN-7603](https://northerntech.atlassian.net/browse/MEN-7603)) ([2f73a24](https://github.com/mendersoftware/mender-server-enterprise/commit/2f73a24cb9217d8cea65561bb4f3bdeff786f80b)) 


  POST /api/management/v2/useradm/support/feedback/:form_id
  
  The new endpoint accepts a form response with user feedback. There are
  currently two `form_id` defined: "product" and "feat.ai" for general
  product feedback and feedback specific to the experimental AI feature.

- *(useradm)* Require consent to enable AI features
([MEN-8677](https://northerntech.atlassian.net/browse/MEN-8677)) ([909a9bd](https://github.com/mendersoftware/mender-server-enterprise/commit/909a9bd0b1c47b692014353599021d201e29a561)) 


  There is an explicit option for enabling AI features in the global
  settings (`aiFeatures.enabled`), requiring admin access to allow
  using the feature.

- *(useradm)* New endpoint for submitting user feedback
([MEN-7603](https://northerntech.atlassian.net/browse/MEN-7603)) ([2f73a24](https://github.com/mendersoftware/mender-server-enterprise/commit/2f73a24cb9217d8cea65561bb4f3bdeff786f80b)) 


  POST /api/management/v2/useradm/support/feedback/:form_id
  
  The new endpoint accepts a form response with user feedback. There are
  currently two `form_id` defined: "product" and "feat.ai" for general
  product feedback and feedback specific to the experimental AI feature.

- *(workflows)* Workflow for sending Two-factor status change email
 ([fc21640](https://github.com/mendersoftware/mender-server-enterprise/commit/fc21640e5dd8ec5d9862fb4af9111cb2a0b76e42))  by @alfrunes

- *(workflows)* Delete devicemonitor device when decommissioning devices
 ([6a25915](https://github.com/mendersoftware/mender-server-enterprise/commit/6a25915ecac07346111c9f30af0d4cd12e5d03a9)) 

- New flag `--tenant-token` for `create-org` CLI command
([MEN-7901](https://northerntech.atlassian.net/browse/MEN-7901)) ([5df75ff](https://github.com/mendersoftware/mender-server-enterprise/commit/5df75ff970d27326d7507402e233af61262463d4))  by @alfrunes


  The new flag sets the tenant-token to a given string.
  Primarily useful in tests.




### Refactor


- *(gui)* Refactored subscription form to be a RHF form & reduce faulty billing calls
 ([5938972](https://github.com/mendersoftware/mender-server-enterprise/commit/59389724fd85802e50dc6ce951814a5d8d4beeb0))  by @mzedel

- *(useradm)* Move two-factor status constants to model package
 ([9ebc052](https://github.com/mendersoftware/mender-server-enterprise/commit/9ebc052fa2a86bce00080fd72466af7bbde2a73b))  by @alfrunes

- *(useradm)* Share workflows client code for starting workflow
 ([2d6eae6](https://github.com/mendersoftware/mender-server-enterprise/commit/2d6eae6d9dc7f0e9023c89f14c509be2b814c3fa))  by @alfrunes





### Security


- Bump validator in /frontend/tests/e2e_tests
 ([f9d5dd6](https://github.com/mendersoftware/mender-server-enterprise/commit/f9d5dd641b6fbb7ebf24049de8cd20d541b3bc84))  by @dependabot[bot]


  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.15 to 13.15.20.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.15...13.15.20)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.20
    dependency-type: direct:development
  ...
- Bump validator from 13.15.15 to 13.15.20 in /frontend
 ([94a0d8a](https://github.com/mendersoftware/mender-server-enterprise/commit/94a0d8ad6f672f011e922ce1813632887499a301))  by @dependabot[bot]


  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.15 to 13.15.20.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.15...13.15.20)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.20
    dependency-type: direct:production
  ...
- Bump chrislusf/seaweedfs
 ([7bcb49b](https://github.com/mendersoftware/mender-server-enterprise/commit/7bcb49b2bef8b6dd098d32040d8ca4ecf4f308e0))  by @dependabot[bot]


  Bumps the backend-docker-compose-dependencies group with 1 update in the /compose directory: chrislusf/seaweedfs.
  
  
  Updates `chrislusf/seaweedfs` from 3.97 to 3.99
  
  ---
  updated-dependencies:
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '3.99'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([fcfe670](https://github.com/mendersoftware/mender-server-enterprise/commit/fcfe67062b3287b2dfec568940babd9c7e555ef2))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/storage/azblob](https://github.com/Azure/azure-sdk-for-go) | `1.6.2` | `1.6.3` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.39.2` | `1.39.5` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.12` | `1.31.16` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.18.16` | `1.18.20` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.5` | `1.69.8` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.6` | `1.32.9` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.88.4` | `1.89.1` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.12.0` | `2.12.1` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.46.1` | `1.47.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.14.0` | `9.16.0` |
  | [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) | `1.17.4` | `1.17.6` |
  | [golang.org/x/time](https://github.com/golang/time) | `0.13.0` | `0.14.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/storage/azblob` from 1.6.2 to 1.6.3
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/storage/azblob/v1.6.2...sdk/storage/azblob/v1.6.3)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.39.2 to 1.39.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.39.2...v1.39.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.12 to 1.31.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.12...config/v1.31.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.16 to 1.18.20
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/config/v1.18.20/CHANGELOG.md)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.16...config/v1.18.20)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.5 to 1.69.8
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.5...service/iot/v1.69.8)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.6 to 1.32.9
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.6...service/mgn/v1.32.9)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.88.4 to 1.89.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.88.4...service/s3/v1.89.1)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.12.0 to 2.12.1
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.12.0...v2.12.1)
  
  Updates `github.com/nats-io/nats.go` from 1.46.1 to 1.47.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.46.1...v1.47.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.14.0 to 9.16.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.14.0...v9.16.0)
  
  Updates `go.mongodb.org/mongo-driver` from 1.17.4 to 1.17.6
  - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
  - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.17.4...v1.17.6)
  
  Updates `golang.org/x/time` from 0.13.0 to 0.14.0
  - [Commits](https://github.com/golang/time/compare/v0.13.0...v0.14.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/storage/azblob
    dependency-version: 1.6.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.39.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.20
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.8
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.9
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.89.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.47.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: go.mongodb.org/mongo-driver
    dependency-version: 1.17.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/time
    dependency-version: 0.14.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump @playwright/test
 ([28a4805](https://github.com/mendersoftware/mender-server-enterprise/commit/28a48056a49a56847807b947dec81661d1f29dee))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.55.1 to 1.56.1
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.55.1...v1.56.1)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.56.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump the e2e-test-dependencies group
 ([d8d93f9](https://github.com/mendersoftware/mender-server-enterprise/commit/d8d93f9b8edf2193fd78fa5541712bf613a9c28a))  by @dependabot[bot]


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 3 updates: [commander](https://github.com/tj/commander.js), [dayjs](https://github.com/iamkun/dayjs) and [inquirer](https://github.com/SBoudrias/Inquirer.js).
  
  
  Updates `commander` from 14.0.1 to 14.0.2
  - [Release notes](https://github.com/tj/commander.js/releases)
  - [Changelog](https://github.com/tj/commander.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/tj/commander.js/compare/v14.0.1...v14.0.2)
  
  Updates `dayjs` from 1.11.18 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.18...v1.11.19)
  
  Updates `inquirer` from 12.9.6 to 12.10.0
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@12.9.6...inquirer@12.10.0)
  
  ---
  updated-dependencies:
  - dependency-name: commander
    dependency-version: 14.0.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: inquirer
    dependency-version: 12.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([13fccec](https://github.com/mendersoftware/mender-server-enterprise/commit/13fccec266e96898aaed7723cec06278ffceaa9d))  by @dependabot[bot]


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.12.0 to 8.16.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.16.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([49e08c8](https://github.com/mendersoftware/mender-server-enterprise/commit/49e08c8f076748a6cc90eee4f0e2f004ed6663ab))  by @dependabot[bot]


  Bumps the production-dependencies group in /frontend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/store](https://github.com/NorthernTechHQ/nt-gui) | `0.7.0` | `0.8.0` |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.8.2` | `2.9.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `10.17.0` | `10.22.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.9.0` | `5.3.0` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.8.0` | `8.2.0` |
  | [axios](https://github.com/axios/axios) | `1.12.0` | `1.13.1` |
  | [dayjs](https://github.com/iamkun/dayjs) | `1.11.13` | `1.11.19` |
  | [react](https://github.com/facebook/react/tree/HEAD/packages/react) | `19.1.1` | `19.2.0` |
  | [react-dom](https://github.com/facebook/react/tree/HEAD/packages/react-dom) | `19.1.1` | `19.2.0` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.62.0` | `7.66.0` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.8.1` | `7.9.5` |
  | [uuid](https://github.com/uuidjs/uuid) | `11.1.0` | `13.0.0` |
  
  
  Updates `@northern.tech/store` from 0.7.0 to 0.8.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/store-0.7.0...@northern.tech/store-0.8.0)
  
  Updates `@reduxjs/toolkit` from 2.8.2 to 2.9.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.8.2...v2.9.2)
  
  Updates `@sentry/react` from 10.17.0 to 10.22.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/10.17.0...10.22.0)
  
  Updates `@stripe/react-stripe-js` from 3.9.0 to 5.3.0
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.9.0...v5.3.0)
  
  Updates `@stripe/stripe-js` from 7.8.0 to 8.2.0
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.8.0...v8.2.0)
  
  Updates `axios` from 1.12.0 to 1.13.1
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.12.0...v1.13.1)
  
  Updates `dayjs` from 1.11.13 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.13...v1.11.19)
  
  Updates `react` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react)
  
  Updates `react-dom` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react-dom)
  
  Updates `react-hook-form` from 7.62.0 to 7.66.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.62.0...v7.66.0)
  
  Updates `react-router-dom` from 7.8.1 to 7.9.5
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.9.5/packages/react-router-dom)
  
  Updates `uuid` from 11.1.0 to 13.0.0
  - [Release notes](https://github.com/uuidjs/uuid/releases)
  - [Changelog](https://github.com/uuidjs/uuid/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/uuidjs/uuid/compare/v11.1.0...v13.0.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/store"
    dependency-version: 0.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.9.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 10.22.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 5.3.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 8.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.13.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-dom
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.66.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.9.5
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: uuid
    dependency-version: 13.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  ...




### Revert


- "chore(iot-manager): replace deprecated cipher NewCFBDecrypter and NewCFBEncrypter (...)"
 ([b9f3810](https://github.com/mendersoftware/mender-server-enterprise/commit/b9f38101319e9e118d724c0d1d18a6c4db7a5111))  by @kjaskiewiczz


  This reverts commit 8baa94e909df4b39f55e8ac31653d5b490cf918c.






## 4.1.0-saas.16 - 2025-10-23


### Bug fixes


- *(tenantadm)* Make subscription parameters required for preview recurring invoice
([MEN-8835](https://northerntech.atlassian.net/browse/MEN-8835)) ([3bfa95c](https://github.com/mendersoftware/mender-server-enterprise/commit/3bfa95c74ef3e515487913ea1bebe59eb50d2b98))  by @alfrunes


  The recurring preview mode does not work in some edge cases. Since the
  request is always sent from the UI with a subscription request we'll
  enforce this requirement and remove the dependency on the subscription
  when doing the upstream request.


- *(deployments)* Throw error when `per_page` exceeds maximum allowed value
([MEN-8841](https://northerntech.atlassian.net/browse/MEN-8841)) ([e7c966c](https://github.com/mendersoftware/mender-server-enterprise/commit/e7c966cb9311b2866b13570a97efa3e54c06ad9c))  by @bahaa-ghazal

- *(deployments)* Aligned update metadata understanding w/ mender-artifact
 ([33fae57](https://github.com/mendersoftware/mender-server-enterprise/commit/33fae571932e14ca5b16afd26bc8e410b5c2a92b))  by @mzedel


  - api responses represented the content as a list, whereas the proper representation is the object

- *(deviceauth)* Count current devices for max_devices limit
([MEN-8767](https://northerntech.atlassian.net/browse/MEN-8767)) ([3041965](https://github.com/mendersoftware/mender-server-enterprise/commit/3041965d6788744c8484f35498c9c0854ad9d6bd))  by @frodeha

- *(deviceauth)* Always exit with non-zero exit code on error
 ([c486a45](https://github.com/mendersoftware/mender-server-enterprise/commit/c486a4520bdfdd4402134a2cdfe4ac6a4a206d7a))  by @alfrunes

- *(deviceauth)* Tier in authreq for devices with external id
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([2de6766](https://github.com/mendersoftware/mender-server-enterprise/commit/2de67665323269be3d5afc3632b8d3aafc45b169))  by @frodeha

- *(deviceconnect)* SetReadDeadline when setting up ping handler
([MEN-8843](https://northerntech.atlassian.net/browse/MEN-8843)) ([b10a3a8](https://github.com/mendersoftware/mender-server-enterprise/commit/b10a3a8dd0b1b4c85c6b33184b9f9ed6b5fa8b86))  by @kjaskiewiczz

- *(gui)* Fixed an issue that prevented showing billing errors
 ([06f0cec](https://github.com/mendersoftware/mender-server-enterprise/commit/06f0cecd067917479b8249b362d5edfa317b89e4)) 

- *(gui)* Let theme switch also be reflected via external style definitions
 ([2485bf1](https://github.com/mendersoftware/mender-server-enterprise/commit/2485bf1a8c00b2060797b0977284980fd420fd63)) 

- *(gui)* Fixed contact descriptions
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([a013a00](https://github.com/mendersoftware/mender-server-enterprise/commit/a013a0074da904d19d1ca01c9ad8dfef0382d083)) 

- *(gui)* Fall back to delta job count while pagination total isn't available
 ([79360cc](https://github.com/mendersoftware/mender-server-enterprise/commit/79360cc0e91249c86e867eb766b9216dcd3f2fa9)) 

- *(gui)* Fixed an issue that could cause the deployment device limit to be ignored
([ME-568](https://northerntech.atlassian.net/browse/ME-568)) ([64974ec](https://github.com/mendersoftware/mender-server-enterprise/commit/64974ec50a534fc690c9ce0ea91c80dbb3407607))  by @mzedel

- *(gui)* Reduce situations deployments to specific devices won't find releases
 ([bd4e361](https://github.com/mendersoftware/mender-server-enterprise/commit/bd4e361f8e0fa34f7d479237f3b17a1d24de6675))  by @mzedel

- *(gui)* Limited chances a set deployment device limit gets changed unintended
 ([1f12d38](https://github.com/mendersoftware/mender-server-enterprise/commit/1f12d38249ac4bba72bbbc7ebb92ffdcf4fe9b09))  by @mzedel

- *(gui)* Fixed an issue that could prevent the billing overview from working
 ([4d1f0f3](https://github.com/mendersoftware/mender-server-enterprise/commit/4d1f0f3f41ece22b75310d76f2015ff7576f4a8c))  by @mzedel

- *(gui)* Fixed an issue that prevented editing SSO configurations
 ([3005bea](https://github.com/mendersoftware/mender-server-enterprise/commit/3005beaad9511b5c4768eff7438fc009fd8b567f))  by @mzedel

- *(gui)* Fixed faulty check to see if user settings info can be relied on
 ([9251747](https://github.com/mendersoftware/mender-server-enterprise/commit/92517472e60c29c5025ea4b948525aeb45d04599))  by @mzedel

- *(tenantadm)* Proxy invalid user error from useradm
([MEN-8857](https://northerntech.atlassian.net/browse/MEN-8857)) ([050bd72](https://github.com/mendersoftware/mender-server-enterprise/commit/050bd72961194684fe2e924636cba63b9427520a))  by @frodeha

- *(tenantadm)* Properly handle duplicate Stripe webhook events
 ([90e88c7](https://github.com/mendersoftware/mender-server-enterprise/commit/90e88c7e7dd093ac629454089b640f8ff9403ac4))  by @alfrunes

- *(useradm)* Fix command for collecting user stats
([MEN-8862](https://northerntech.atlassian.net/browse/MEN-8862)) ([e1c70d4](https://github.com/mendersoftware/mender-server-enterprise/commit/e1c70d45d45e5fbe7de7874e96c28cc790500493))  by @kjaskiewiczz

- *(workflows)* Remove Retries
 ([3e5b281](https://github.com/mendersoftware/mender-server-enterprise/commit/3e5b281e26b98c7d5cf9cf7c05bf1d56abe515be))  by @oldgiova


  This retry mechanism has no automatic Delay, so the retries are made in
  sequence, and this is useless and detrimental to the load.
  
  Removing the retries, while waiting for a more robust approach, like
  retries with delays and workflows autoscaling.

- *(workflows)* Expose Jetstream `replicas` parameter
([MEN-7164](https://northerntech.atlassian.net/browse/MEN-7164)) ([b87100e](https://github.com/mendersoftware/mender-server-enterprise/commit/b87100eb5aa12fec6ac83dd59329e1742a6fbfa9))  by @bahaa-ghazal

- Adjusted burst limiting to work w/ updated miniredis
 ([8158efa](https://github.com/mendersoftware/mender-server-enterprise/commit/8158efa8a1a814cc0b31051cd77bdf8bf8960801))  by @mzedel


  - prior it was "every request extends the window" => now: "first request wins the window"
- Validate rate limit config when setting up redis
([MEN-8864](https://northerntech.atlassian.net/browse/MEN-8864)) ([186f750](https://github.com/mendersoftware/mender-server-enterprise/commit/186f7505048c8404fdf646b6a669ad02b27b8aea))  by @bahaa-ghazal
- Check release tags when fetching a release by name
([MEN-8422](https://northerntech.atlassian.net/browse/MEN-8422)) ([cf4a45b](https://github.com/mendersoftware/mender-server-enterprise/commit/cf4a45b4affc4d583fb6d2bf13c9607000661a02))  by @bahaa-ghazal




### Documentation


- *(deviceauth)* Update and deprecate /limits/max_devices endpoints
([MEN-8570](https://northerntech.atlassian.net/browse/MEN-8570)) ([a70bcda](https://github.com/mendersoftware/mender-server-enterprise/commit/a70bcdae3485615d31d7b999c2d9023e73136bd7))  by @kjaskiewiczz

- *(deviceauth)* Add missing spec for limits/devices to backend docs
 ([2212874](https://github.com/mendersoftware/mender-server-enterprise/commit/22128746d51cadd01da6942426c16ba7737d59f1))  by @kjaskiewiczz

- *(deviceauth)* Document unlimited limits in API docs
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([fff5975](https://github.com/mendersoftware/mender-server-enterprise/commit/fff5975d3a1163fa31d97f34412eef8ffa50c40e))  by @frodeha

- *(api)* Made operationIds unique across API specs
 ([8e45186](https://github.com/mendersoftware/mender-server-enterprise/commit/8e451863d4dae2caafe2ad2331bece31d5367f6b))  by @mzedel

- *(api)* Unified path structure + servers across specs
 ([2a73980](https://github.com/mendersoftware/mender-server-enterprise/commit/2a739800ae8694fa5d210365fceac50413696f44))  by @mzedel

- *(api)* Deduplicated schema definitions across service specs
 ([a7f31cb](https://github.com/mendersoftware/mender-server-enterprise/commit/a7f31cbd2e9c48bd28a23bc624297d628fd7b145))  by @mzedel

- *(deployments)* Aligned docs based specs w/ services based specs
 ([f84f39b](https://github.com/mendersoftware/mender-server-enterprise/commit/f84f39b702a6ba3301ca475b7c5914ee350d09fa))  by @mzedel


  - to also publish delta job endpoints

- *(deployments)* Clarify V2 `/artifacts` endpoint usage
([MEN-8842](https://northerntech.atlassian.net/browse/MEN-8842)) ([d5a1a0f](https://github.com/mendersoftware/mender-server-enterprise/commit/d5a1a0f471fd51fc82d07fcf41082abd74b42b9c))  by @bahaa-ghazal

- *(inventory)* Add clarity to list devices api docs
 ([c460380](https://github.com/mendersoftware/mender-server-enterprise/commit/c46038013ba60510d2a45fcea66917be29642976)) 

- *(useradm)* Make API specs more consistent with enterprise
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([1022949](https://github.com/mendersoftware/mender-server-enterprise/commit/1022949e7df31ccb90b624d1c6ba411950c98634)) 

- Let docs rely on common error + security definitions
 ([d9fe72b](https://github.com/mendersoftware/mender-server-enterprise/commit/d9fe72b035450aea8079c84cec954281dda44397))  by @mzedel
- Let api docs rely on common internal error response
 ([286c453](https://github.com/mendersoftware/mender-server-enterprise/commit/286c4535a0dedb85d8dd7ea12a5275a5e83e8931))  by @mzedel
- Let api docs rely on common 404 response
 ([9225d00](https://github.com/mendersoftware/mender-server-enterprise/commit/9225d00670ae7e2d4163638d02f07e6d6aac5ece))  by @mzedel
- Aligned enterprise only services w/ file naming scheme + structure
 ([b9c4ccd](https://github.com/mendersoftware/mender-server-enterprise/commit/b9c4ccd07abaf8921332b0e1e16660647c61118c)) 
- Aligned more error responses w/ existing shared response definitions
 ([d5596d5](https://github.com/mendersoftware/mender-server-enterprise/commit/d5596d572c1a0621e87b973549fc86d4542d5b69))  by @mzedel
- Aligned unauthorized errors definitions w/ shared definition
 ([9d26fd7](https://github.com/mendersoftware/mender-server-enterprise/commit/9d26fd700a572600bba631291102eb1dc34baba3))  by @mzedel
- Fix paths in remaining service specs
 ([a452ff7](https://github.com/mendersoftware/mender-server-enterprise/commit/a452ff7dcd6babc8ef9f001c2cc4249f6b59cd59))  by @mzedel
- Use common schemas and unique operationIds
 ([72ee78b](https://github.com/mendersoftware/mender-server-enterprise/commit/72ee78bfbdef8e60ded346b929d25ed9187696a3))  by @mzedel
- Deduplicate schemas across newly moved service specs
 ([e6f75e2](https://github.com/mendersoftware/mender-server-enterprise/commit/e6f75e29c185ed07c9c9e50235b880d431b82d46))  by @mzedel
- Aligned enterprise only services w/ file naming scheme + structure
 ([b9c4ccd](https://github.com/mendersoftware/mender-server-enterprise/commit/b9c4ccd07abaf8921332b0e1e16660647c61118c))  by @mzedel
- Aligned update metadata w/ defined type to allow parsing
 ([f306fac](https://github.com/mendersoftware/mender-server-enterprise/commit/f306fac4caac94f14daed287def36f0b375d1069))  by @mzedel




### Features


- *(deviceauth)* Support unlimited device tier limits
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([0e17a1f](https://github.com/mendersoftware/mender-server-enterprise/commit/0e17a1f4f196b905b478624eced1edecb3776f88))  by @frodeha

- *(deviceauth)* DEVICEAUTH_ENABLE_TIERS to enable device tiers support
 ([b3bffb4](https://github.com/mendersoftware/mender-server-enterprise/commit/b3bffb4c75da6d57841bbe99b4ec63ab0f0e71c2))  by @merlin-northern

- *(deployments)* Rate limit new device deployments per tenant
([MEN-8840](https://northerntech.atlassian.net/browse/MEN-8840)) ([1ab79a5](https://github.com/mendersoftware/mender-server-enterprise/commit/1ab79a5e810bca03354ae5ceb5085b2e05ad2183))  by @frodeha


  Introduce a rate limiter that can be configured to only allow a certain
  number of new device deployments to be created within a specific time
  interval.

- *(deployments)* Configure new device deployments rate limiter
([MEN-8840](https://northerntech.atlassian.net/browse/MEN-8840)) ([70211e7](https://github.com/mendersoftware/mender-server-enterprise/commit/70211e7e2b8c2a4e8cf917c97b0343222d1e6bd2))  by @frodeha

- *(deviceauth)* Added command to propagate identity to inventory
([MEN-8733](https://northerntech.atlassian.net/browse/MEN-8733)) ([ee7c84b](https://github.com/mendersoftware/mender-server-enterprise/commit/ee7c84bb9e48ad0f28966838929d9a9cfe00cefb))  by @alfrunes


  Created a new command `deviceauth maintenance propagate-inventory` which
  propagates data from deviceauth (id_data and status) to inventory
  service.

- *(deviceauth)* Support for device tier parameter in the authset
([MEN-8558](https://northerntech.atlassian.net/browse/MEN-8558)) ([fa03730](https://github.com/mendersoftware/mender-server-enterprise/commit/fa037303fe5be4a822fd6d5315aa4f4440f61807))  by @merlin-northern


  We introduce a new [authset](https://docs.mender.io/overview/device-authentication)
  parameter: device tier: a string of letters describing a device kind.
  Currently supported values: micro, system, standard.

- *(deviceauth)* Check device tier limit when accepting device
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([8bb262f](https://github.com/mendersoftware/mender-server-enterprise/commit/8bb262f02fb5f3e9e6a2b3546b4eca61de619cd3))  by @frodeha

- *(deviceauth)* Maintain device tier from auth set
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([6390f63](https://github.com/mendersoftware/mender-server-enterprise/commit/6390f63ba4e567c3193b02292cb4e44dcdbca86a))  by @frodeha


  Maintain the tier of a device based on the latest accepted auth

- *(deviceauth)* Count tenant device limits by tier
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([4084a26](https://github.com/mendersoftware/mender-server-enterprise/commit/4084a26c21caf51e6244bae4bf94b53c6af55d63))  by @frodeha

- *(deviceauth)* Management api to get device limit per tier
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([5e9c2e2](https://github.com/mendersoftware/mender-server-enterprise/commit/5e9c2e2786a6c3499d09f02ff2e3f7c578b9abfb))  by @frodeha

- *(generate-delta-worker)* GENERATE_DELTA_USE_FIFOS env var control the named pipes usage
([MEN-8762](https://northerntech.atlassian.net/browse/MEN-8762)) ([71dbd6e](https://github.com/mendersoftware/mender-server-enterprise/commit/71dbd6e411b88c0a794d38d38a5a68573704b03c))  by @merlin-northern


  A new setting via an environment variable GENERATE_DELTA_USE_FIFOS
  is introduced to control the use of named pipes in the binary delta
  generation on the server side via generate-delta-worker. This setting
  should be set to false for enviornments where the resources permit
  safe usage of regular files for the delta generation. By defaut it is set
  to false.

- *(gui)* Let device deployments history access our log viewer as well
([MEN-8727](https://northerntech.atlassian.net/browse/MEN-8727)) ([f1753f7](https://github.com/mendersoftware/mender-server-enterprise/commit/f1753f74d684e448176f062dc1d93b0258b2b68d))  by @mzedel

- *(gui)* Let timeframe filter elements also show context dependent notifications
 ([59cac13](https://github.com/mendersoftware/mender-server-enterprise/commit/59cac137acd21daf69ea8f54dddb6f1fde0da7b2))  by @mzedel

- *(gui)* Added notification about auditlog retention time to explain missing entries
([MEN-8153](https://northerntech.atlassian.net/browse/MEN-8153)) ([51c8fa1](https://github.com/mendersoftware/mender-server-enterprise/commit/51c8fa1fa4ba9e020a0a385272c4e531216bfd8e))  by @mzedel

- *(inventory)* Add If-Modified-Since to internal Update Device Attributes
 ([55ae1a1](https://github.com/mendersoftware/mender-server-enterprise/commit/55ae1a111efbd1202cbe0f31c60f50508d011925))  by @alfrunes


  Adds precondition header `If-Modified-Since` to the internal API for
  updating attributes within a scope.





### Refactor


- *(deviceauth)* Remove unused limits function and fix comment
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([347ddc7](https://github.com/mendersoftware/mender-server-enterprise/commit/347ddc71d5d09ad09238f90167eebd29ce66d62d))  by @frodeha

- *(deviceauth)* Rename MaxDevicesCount constant
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([05775fd](https://github.com/mendersoftware/mender-server-enterprise/commit/05775fdca4e8dea754defd8864b9774231f8562d))  by @frodeha

- *(deviceauth)* Remove tenantadm related code from OS
([MEN-8649](https://northerntech.atlassian.net/browse/MEN-8649)) ([31b9d2b](https://github.com/mendersoftware/mender-server-enterprise/commit/31b9d2beeb60a4485449f620ca58df580ba1cae9)) 

- *(gui)* Made use of store + testing package in codebase
 ([2d90e96](https://github.com/mendersoftware/mender-server-enterprise/commit/2d90e9682eeaf53f45612b7c13b70c2abcc580ed))  by @mzedel

- *(gui)* Made use of testing package & utils in tests
 ([f416d68](https://github.com/mendersoftware/mender-server-enterprise/commit/f416d68d89986df4b446f6bca9955c392cee8d34))  by @mzedel

- *(gui)* Aligned thunk spying w/ updated store package format
 ([ab1ee33](https://github.com/mendersoftware/mender-server-enterprise/commit/ab1ee331199ec1bab9183d9ebb0568a2a2ffa136))  by @mzedel

- *(gui)* Let email check be done in thunk to align msw handler location
 ([eaae614](https://github.com/mendersoftware/mender-server-enterprise/commit/eaae614b8ae7b9b4ed46a9f5fd630ff54e8c746e))  by @mzedel





### Security


- Bump typescript
 ([d7650b8](https://github.com/mendersoftware/mender-server-enterprise/commit/d7650b82aa14c558cb78b171b34852fc91ef633f))  by @dependabot[bot]


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 1 update: [typescript](https://github.com/microsoft/TypeScript).
  
  
  Updates `typescript` from 5.9.2 to 5.9.3
  - [Release notes](https://github.com/microsoft/TypeScript/releases)
  - [Changelog](https://github.com/microsoft/TypeScript/blob/main/azure-pipelines.release-publish.yml)
  - [Commits](https://github.com/microsoft/TypeScript/compare/v5.9.2...v5.9.3)
  
  ---
  updated-dependencies:
  - dependency-name: typescript
    dependency-version: 5.9.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  ...
- Bump the development-dependencies group
 ([728b146](https://github.com/mendersoftware/mender-server-enterprise/commit/728b14669983cb29c4b41852a40cef2601010ead))  by @dependabot[bot]


  Bumps the development-dependencies group in /frontend with 7 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.5.6` | `1.5.8` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.5.6` | `1.5.8` |
  | [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) | `6.8.0` | `6.9.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.5.2` | `24.6.1` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.0.3` | `5.0.4` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `16.2.0` | `16.2.3` |
  | [typescript](https://github.com/microsoft/TypeScript) | `5.9.2` | `5.9.3` |
  
  
  Updates `@rspack/cli` from 1.5.6 to 1.5.8
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.8/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.5.6 to 1.5.8
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.8/packages/rspack)
  
  Updates `@testing-library/jest-dom` from 6.8.0 to 6.9.0
  - [Release notes](https://github.com/testing-library/jest-dom/releases)
  - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/jest-dom/compare/v6.8.0...v6.9.0)
  
  Updates `@types/node` from 24.5.2 to 24.6.1
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@vitejs/plugin-react` from 5.0.3 to 5.0.4
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.0.4/packages/plugin-react)
  
  Updates `lint-staged` from 16.2.0 to 16.2.3
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v16.2.0...v16.2.3)
  
  Updates `typescript` from 5.9.2 to 5.9.3
  - [Release notes](https://github.com/microsoft/TypeScript/releases)
  - [Changelog](https://github.com/microsoft/TypeScript/blob/main/azure-pipelines.release-publish.yml)
  - [Commits](https://github.com/microsoft/TypeScript/compare/v5.9.2...v5.9.3)
  
  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.5.8
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.5.8
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/jest-dom"
    dependency-version: 6.9.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.6.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.0.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.2.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: typescript
    dependency-version: 5.9.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump @playwright/test
 ([7489159](https://github.com/mendersoftware/mender-server-enterprise/commit/748915946dc8b598ce2918fa65df8fdbc8fc945c))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.55.0 to 1.55.1
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.55.0...v1.55.1)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.55.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: playwright
  ...
- Bump the mui group in /frontend with 3 updates
 ([cfa0203](https://github.com/mendersoftware/mender-server-enterprise/commit/cfa02034048f443cc10c5523eff378161576a001))  by @dependabot[bot]


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.2 to 7.3.3
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.3/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.2 to 7.3.3
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.3/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.11.3 to 8.12.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.12.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.12.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump nats
 ([6ef8f84](https://github.com/mendersoftware/mender-server-enterprise/commit/6ef8f840f0b80bddfcaf20b5a3a13bf112873d68))  by @dependabot[bot]


  Bumps the backend-docker-compose-dependencies group with 1 update in the / directory: nats.
  
  
  Updates `nats` from 2.11 to 2.12
  
  ---
  updated-dependencies:
  - dependency-name: nats
    dependency-version: '2.12'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group across 1 directory with 17 updates
 ([9e22c80](https://github.com/mendersoftware/mender-server-enterprise/commit/9e22c80c9521fb3d9e782f7922e97610f6e361f5))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group with 12 updates in the /backend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.19.0` | `1.19.1` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.38.3` | `1.39.2` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.6` | `1.31.12` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.1` | `1.69.5` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.2` | `1.32.6` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.87.3` | `1.88.3` |
  | [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) | `1.10.1` | `1.11.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.8` | `2.12.0` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.45.0` | `1.46.1` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.13.0` | `9.14.0` |
  | [github.com/spf13/viper](https://github.com/spf13/viper) | `1.20.1` | `1.21.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.43.0` | `0.44.0` |
  
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.19.0 to 1.19.1
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/sdk-breaking-changes-guide-migration.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.19.0...sdk/azcore/v1.19.1)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.38.3 to 1.39.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.38.3...v1.39.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.6 to 1.31.12
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.6...config/v1.31.12)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.10 to 1.18.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.10...config/v1.18.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.1 to 1.69.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.1...service/iot/v1.69.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.2 to 1.32.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.2...v1.32.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.87.3 to 1.88.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.87.3...service/s3/v1.88.3)
  
  Updates `github.com/gin-gonic/gin` from 1.10.1 to 1.11.0
  - [Release notes](https://github.com/gin-gonic/gin/releases)
  - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/gin-gonic/gin/compare/v1.10.1...v1.11.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.8 to 2.12.0
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.8...v2.12.0)
  
  Updates `github.com/nats-io/nats.go` from 1.45.0 to 1.46.1
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.45.0...v1.46.1)
  
  Updates `github.com/redis/go-redis/v9` from 9.13.0 to 9.14.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.13.0...v9.14.0)
  
  Updates `github.com/spf13/viper` from 1.20.1 to 1.21.0
  - [Release notes](https://github.com/spf13/viper/releases)
  - [Commits](https://github.com/spf13/viper/compare/v1.20.1...v1.21.0)
  
  Updates `golang.org/x/crypto` from 0.41.0 to 0.42.0
  - [Commits](https://github.com/golang/crypto/compare/v0.41.0...v0.42.0)
  
  Updates `golang.org/x/net` from 0.43.0 to 0.44.0
  - [Commits](https://github.com/golang/net/compare/v0.43.0...v0.44.0)
  
  Updates `golang.org/x/sys` from 0.35.0 to 0.36.0
  - [Commits](https://github.com/golang/sys/compare/v0.35.0...v0.36.0)
  
  Updates `golang.org/x/term` from 0.34.0 to 0.35.0
  - [Commits](https://github.com/golang/term/compare/v0.34.0...v0.35.0)
  
  Updates `golang.org/x/time` from 0.12.0 to 0.13.0
  - [Commits](https://github.com/golang/time/compare/v0.12.0...v0.13.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.19.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.39.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.12
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.88.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/gin-gonic/gin
    dependency-version: 1.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.46.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.14.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/viper
    dependency-version: 1.21.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.44.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.36.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.35.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/time
    dependency-version: 0.13.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump github.com/quic-go/quic-go from 0.54.0 to 0.54.1 in /backend
 ([27df7d6](https://github.com/mendersoftware/mender-server-enterprise/commit/27df7d6bee416bec25b8fda09c445ad0740bca6a))  by @dependabot[bot]


  Bumps [github.com/quic-go/quic-go](https://github.com/quic-go/quic-go) from 0.54.0 to 0.54.1.
  - [Release notes](https://github.com/quic-go/quic-go/releases)
  - [Commits](https://github.com/quic-go/quic-go/compare/v0.54.0...v0.54.1)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/quic-go/quic-go
    dependency-version: 0.54.1
    dependency-type: indirect
  ...
- Bump vite from 7.1.5 to 7.1.11 in /frontend
 ([0839758](https://github.com/mendersoftware/mender-server-enterprise/commit/08397583bcd1c3e9df9efdc054a05137bec9f9bc))  by @dependabot[bot]


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 7.1.5 to 7.1.11.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v7.1.11/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 7.1.11
    dependency-type: indirect
  ...






## 4.1.0-saas.14 - 2025-09-30


### Bug fixes


- *(deployments)* Disallow changing timeout for binary delta generation
([MEN-8264](https://northerntech.atlassian.net/browse/MEN-8264)) ([154d802](https://github.com/mendersoftware/mender-server-enterprise/commit/154d8029b0e14d5f32e4c25c2e56c36d6142ddf1))  by @merlin-northern

- *(deployments)* Preset number of pending devices in deployments statistics
([MEN-8522](https://northerntech.atlassian.net/browse/MEN-8522)) ([e442a50](https://github.com/mendersoftware/mender-server-enterprise/commit/e442a509eda03d67f0e72679c8920050e30eb467))  by @kjaskiewiczz

- *(deployments)* Lower size limit for single file uploads
 ([07f5c61](https://github.com/mendersoftware/mender-server-enterprise/commit/07f5c618e9e1c5e37499b35446e0925dc0b6968e))  by @frodeha

- *(deployments)* Limit `name`, `type` and `device types compatible` length
 ([6f612d4](https://github.com/mendersoftware/mender-server-enterprise/commit/6f612d4c2d8ecb9e3d4f1246cd0755d77cdda11f))  by @frodeha


  Limit the max length of `name` (aka `Release name` in the gui),
  `type` and `device types compatible` fields in `MultipartGenerateImageMsg`
  (used by single file uploads) to 256 characters.
  
  There has been introduced a limit of 256 characters to the corresponding
  fields in mender-artifact:
      https://github.com/mendersoftware/mender-artifact/commit/ddd821f8a5150fb8a3186b337525f17b2757599c
  causing uploads that do not abide by this limit to fail silently in the
  background when being processed by the workflow worker.
  
  With this input validation we provide an explicit error to the user in
  this case.

- *(deployments)* Limit delta artifact by the uncompressed size
([MEN-8734](https://northerntech.atlassian.net/browse/MEN-8734)) ([12e6da8](https://github.com/mendersoftware/mender-server-enterprise/commit/12e6da8c13e515e1305bf452062ccbf7d4483d65))  by @bahaa-ghazal

- *(deployments)* Increase the server side delta generation limit to 5 GiB
([MEN-8734](https://northerntech.atlassian.net/browse/MEN-8734)) ([32a46d5](https://github.com/mendersoftware/mender-server-enterprise/commit/32a46d5ab4d7505412a64351c633379e91cb79e2))  by @bahaa-ghazal

- *(deviceauth)* `request_size_limit` configuration not applied
([MEN-8788](https://northerntech.atlassian.net/browse/MEN-8788)) ([93d82a5](https://github.com/mendersoftware/mender-server-enterprise/commit/93d82a59001e23650efb8d5d2518b4b0b9534206))  by @alfrunes

- *(deviceconnect)* Make sure goroutines recover when panicing
([MEN-7750](https://northerntech.atlassian.net/browse/MEN-7750)) ([0f5870a](https://github.com/mendersoftware/mender-server-enterprise/commit/0f5870ad5d8fc073193a243e9b9a4f12f00752c4))  by @bahaa-ghazal

- *(generate-delta-worker)* Do not expose signed url in description
 ([6538a53](https://github.com/mendersoftware/mender-server-enterprise/commit/6538a5351acf73575b2ac1c19659f1af9e70feb6))  by @alfrunes


  Extracts the artifact ID in the URL to avoid printing the signed URL to
  the source artifact.

- *(gui)* Changed pending deployment stats to rely on backend value
([MEN-8522](https://northerntech.atlassian.net/browse/MEN-8522)) ([751c5cd](https://github.com/mendersoftware/mender-server-enterprise/commit/751c5cda92fc09835146ab099710112ce374e8c3))  by @mineralsfree

- *(gui)* Handle error conditions during trial signup gracefully
 ([744dfd1](https://github.com/mendersoftware/mender-server-enterprise/commit/744dfd1deb37675b32e708266673928dce56f1a7))  by @frodeha

- *(gui)* Let artifact generation success depend on artifact presence, not time
 ([3679a0f](https://github.com/mendersoftware/mender-server-enterprise/commit/3679a0f3cea7b782a550d970b6455719b352a2ec))  by @mzedel

- *(gui)* Let theme switch also be reflected via external style definitions
 ([2485bf1](https://github.com/mendersoftware/mender-server-enterprise/commit/2485bf1a8c00b2060797b0977284980fd420fd63))  by @mzedel

- *(gui)* Fetch billing profile on trial
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([0900de9](https://github.com/mendersoftware/mender-server-enterprise/commit/0900de9307a2f5e36bef3c48758a76eeec11f452))  by @mineralsfree

- *(gui)* Fixed contact descriptions
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([a013a00](https://github.com/mendersoftware/mender-server-enterprise/commit/a013a0074da904d19d1ca01c9ad8dfef0382d083))  by @mineralsfree

- *(gui)* Let users know about billing related issues
 ([00ac623](https://github.com/mendersoftware/mender-server-enterprise/commit/00ac6232535cceaaef31cbbe7c5782024fe2f0dc))  by @mzedel


  - to e.g. help identify rate limiting failures

- *(gui)* Fixed an issue that prevented showing billing errors
 ([06f0cec](https://github.com/mendersoftware/mender-server-enterprise/commit/06f0cecd067917479b8249b362d5edfa317b89e4))  by @mzedel

- *(gui)* Fall back to delta job count while pagination total isn't available
 ([79360cc](https://github.com/mendersoftware/mender-server-enterprise/commit/79360cc0e91249c86e867eb766b9216dcd3f2fa9))  by @mzedel

- *(inventory)* Added input validation of attribute scopes
 ([25c7d10](https://github.com/mendersoftware/mender-server-enterprise/commit/25c7d102387bbfdb3af0b0e337c4780305c4c8ac))  by @frodeha

- *(tenantadm)* Added migration for setting missing tenant created_at
 ([742afdd](https://github.com/mendersoftware/mender-server-enterprise/commit/742afdd0ea294cfdf8eefd6b6b9bc56c0e7e668f))  by @frodeha

- *(tenantadm)* Ignore Stripe subscriptions not managed by this service
([MEN-8708](https://northerntech.atlassian.net/browse/MEN-8708)) ([4e8c712](https://github.com/mendersoftware/mender-server-enterprise/commit/4e8c71200c16210da4349667c6b6003d6ca69f05))  by @alfrunes


  Instead of correlating events with customer ID, we correlate with
  subscription IDs. This is mostly to address a transient issue in the
  transition phase where a multi-subscription customer will have the
  subscriptions consolidated, but it also eliminates the need for
  additional database indexing to cover fast customer lookups.

- *(tenantadm)* Remove old "Upgrade from trial" API
([MEN-8763](https://northerntech.atlassian.net/browse/MEN-8763)) ([9a68228](https://github.com/mendersoftware/mender-server-enterprise/commit/9a68228e6f34a4b6070020c104b1cea4e21b9c0c))  by @alfrunes


  The endpoint is superseded by the new self-service upgrade path.

- *(useradm)* Invalidate cache when deleting PAT token
([MEN-7285](https://northerntech.atlassian.net/browse/MEN-7285)) ([e05e898](https://github.com/mendersoftware/mender-server-enterprise/commit/e05e898b7056c79aefad095b9e22f359dcfd1174))  by @bahaa-ghazal

- *(useradm)* Prevent race condition recaching revoked PAT token
 ([1564ec6](https://github.com/mendersoftware/mender-server-enterprise/commit/1564ec6a452c366af2ea4069340e9173669aa4db))  by @bahaa-ghazal

- *(useradm)* Construct valid OIDC redirect_uri
 ([d67ed99](https://github.com/mendersoftware/mender-server-enterprise/commit/d67ed9989bd0efbaa6b2319fc7e0569ec75e548e))  by @frodeha

- *(useradm)* OIDC /login content-type is x-www-form-urlencoded
 ([8abe4a7](https://github.com/mendersoftware/mender-server-enterprise/commit/8abe4a7f64d1cd6d806b15ebf48ae5368132335a))  by @frodeha

- *(useradm)* Don't panic if optional OIDC claim `email` is missing
 ([2fea2c5](https://github.com/mendersoftware/mender-server-enterprise/commit/2fea2c54b4251199cbd17dd78d6f83de81131f45))  by @frodeha

- *(useradm)* Support GET requests to /oidc/:provider/login
 ([161822b](https://github.com/mendersoftware/mender-server-enterprise/commit/161822b09fadf477bd9119076b8aa7ea30a6f8e1))  by @frodeha


  If the OIDC IDP provider doesn't support response_mode=form_post
  (resolved by consulting the /.well-known/openid-configuration of the IDP) we
  default to response_mode=query in the URL generated by
  /oidc/:provider/start.
  
  The "query" response_mode implies that the HTTP
  method of the callback request should be `GET` and we must therefore
  support it.

- List services in Makefile correctly on MacOS
 ([7580e91](https://github.com/mendersoftware/mender-server-enterprise/commit/7580e91c1a3f75bcc2610c4407702a2513339be5))  by @frodeha


  The Makefile function `wildcard`returns both files and directories
  in the /services/ directory (at least on Mac). This leads to test
  execution failing midway. A simple solution is to keep only directories
  using the `dir` function.
  
  In addition, I believe the ordering produced by `wildward` is not
  deterministic, so I added a call to `sort` as well to ensure tests are
  executed in a consistent order (alphabetical).
- Upgrade backend golang version to 1.25.0
 ([d336b7d](https://github.com/mendersoftware/mender-server-enterprise/commit/d336b7d3d160d8630112820f82b3a71b186de0a6))  by @alfrunes




### Documentation


- *(devicemonitor)* Added internal delete device endpoint to api docs
 ([85e5570](https://github.com/mendersoftware/mender-server-enterprise/commit/85e557004ec26e1ad32e3e1b296d2391ba5c9a51))  by @frodeha

- *(inventory)* Added accepted scope values to inventory openapi specs
 ([c186ad3](https://github.com/mendersoftware/mender-server-enterprise/commit/c186ad321a0d391579408ae75ebc247547ccb349))  by @frodeha

- *(inventory)* Add clarity to list devices api docs
 ([c460380](https://github.com/mendersoftware/mender-server-enterprise/commit/c46038013ba60510d2a45fcea66917be29642976))  by @frodeha

- *(useradm)* API documentation for user feedback endpoint
 ([6bc4c29](https://github.com/mendersoftware/mender-server-enterprise/commit/6bc4c298931e0b746ace659b6b3d375fb59c085c))  by @alfrunes

- *(useradm)* Fix swagger spec for feedback API
 ([828ed75](https://github.com/mendersoftware/mender-server-enterprise/commit/828ed75ed01c2538d90dd30d0c67cf1b83d277f9))  by @alfrunes

- *(useradm)* Make API specs more consistent with enterprise
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([1022949](https://github.com/mendersoftware/mender-server-enterprise/commit/1022949e7df31ccb90b624d1c6ba411950c98634))  by @bahaa-ghazal

- *(useradm)* Make API specs more consistent with open source
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([c900a1d](https://github.com/mendersoftware/mender-server-enterprise/commit/c900a1d03aa6b941d84d2c380152b3615b5cbbad))  by @bahaa-ghazal





### Features


- *(deployments)* Experimental API endpoint to explain deployment logs
 ([264e0b1](https://github.com/mendersoftware/mender-server-enterprise/commit/264e0b1252c908f11c7db87d0acc5b423d5fe796))  by @alfrunes


  A new experimental API endpoint is added for invoking LLM to explain
  device logs on failing deployments. The API is only available on consent
  from an admin (provided through useradm global settings).
  
  The feature is experimental and the API may change in the future. For on
  premise instances the feature is disabled by default and requires
  integrating the service with an LLM (see `/etc/deployments/config.yaml`).

- *(deployments)* New experimental endpoint for retrieving logs
 ([6e8c226](https://github.com/mendersoftware/mender-server-enterprise/commit/6e8c226895c19da79187095d442b532882e3bd43))  by @alfrunes


  The new endpoint has a `format` endpoint which supports `text` and
  `text-redacted`. The latter allows previewing the redacted logs sent to
  LLM analysis using the "explain" API. The endpoint is currently
  experimental and subject to changes.

- *(deployments)* Added support for anthropic analysis backend
 ([0e71550](https://github.com/mendersoftware/mender-server-enterprise/commit/0e715506bb4b23b5115a56ef7d5ad5d75a057847))  by @mzedel

- *(devicemonitor)* Added internal delete device endpoint
 ([2cc83f6](https://github.com/mendersoftware/mender-server-enterprise/commit/2cc83f6883c22b092139513105c08a91e66c4484))  by @frodeha

- *(gui)* Let only trial users use demo intervals for deb package installs
([MEN-8620](https://northerntech.atlassian.net/browse/MEN-8620)) ([8117480](https://github.com/mendersoftware/mender-server-enterprise/commit/81174809581bc484bf2f520481676e7c1ecc1fd1))  by @mzedel

- *(gui)* Added log analysis
 ([9f6c8c2](https://github.com/mendersoftware/mender-server-enterprise/commit/9f6c8c29d9d5ab0d76fef5f94b333df99da89329))  by @mzedel

- *(gui)* Let ai request cool down time reflect reality when rate limited
 ([92e8864](https://github.com/mendersoftware/mender-server-enterprise/commit/92e8864a8c9d95991d17ad562877bc6e114ec727))  by @mzedel

- *(gui)* Added execution feedback to troubleshooting device interactions
([MEN-8632](https://northerntech.atlassian.net/browse/MEN-8632)) ([e1e4074](https://github.com/mendersoftware/mender-server-enterprise/commit/e1e4074581b787e9a7bf43943aba68cf9a4a4407))  by @mzedel

- *(gui)* Let tenant sso setting inheritance conditions be more explicit
([MEN-8672](https://northerntech.atlassian.net/browse/MEN-8672)) ([76d4db9](https://github.com/mendersoftware/mender-server-enterprise/commit/76d4db9a219758e21d357f487435cf106bbc62c6))  by @mzedel

- *(gui)* Made it possible for tenants to allow improving ai functionality in the future
([MEN-8719](https://northerntech.atlassian.net/browse/MEN-8719)) ([c2dd114](https://github.com/mendersoftware/mender-server-enterprise/commit/c2dd114e1ec2d2eeb8b33dc300d04de04d3861cd))  by @mzedel

- *(gui)* Switched billing details form to don't disable; validate pattern
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([c3a0a0d](https://github.com/mendersoftware/mender-server-enterprise/commit/c3a0a0da140bf547dcab26322696af293571a159))  by @mineralsfree

- *(gui)* Separated billing details edit & cc edit
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([2dad62a](https://github.com/mendersoftware/mender-server-enterprise/commit/2dad62a9f83030af5759324e1466a08b10c59a65))  by @mineralsfree

- *(gui)* Cc form adjustments
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([d1e9292](https://github.com/mendersoftware/mender-server-enterprise/commit/d1e9292e9a046219234f3eca11f67997c0463bbe))  by @mineralsfree


  autofocus, non disabling validation & disabled state

- *(gui)* Cosmetic subscription adjustments & typography usage
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([0d37587](https://github.com/mendersoftware/mender-server-enterprise/commit/0d375876f258b8d1651e26fd593e054d23bbca10))  by @mineralsfree

- *(gui)* Added special handling for non-stripe non-enterprise customers
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([3e99e17](https://github.com/mendersoftware/mender-server-enterprise/commit/3e99e17765e2010f4feb95f30ce9658a398a36d0))  by @mineralsfree

- *(gui)* Utilized AddonSelect for enterprise/non-stripe users
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([13b7c79](https://github.com/mendersoftware/mender-server-enterprise/commit/13b7c798a8d2815b33fb838bd021ca8541ed81f0))  by @mineralsfree

- *(gui)* Switched to a new endpoint for user feedback
([MEN-7739](https://northerntech.atlassian.net/browse/MEN-7739)) ([e8dae0d](https://github.com/mendersoftware/mender-server-enterprise/commit/e8dae0d247307b49f45f95c4d428c0671300ef7e))  by @mineralsfree

- *(gui)* Adjusted ai feedback to use new feedback endpoint
([MEN-7739](https://northerntech.atlassian.net/browse/MEN-7739)) ([ec2a3f2](https://github.com/mendersoftware/mender-server-enterprise/commit/ec2a3f2c0fd90c3d19a94207e6e05c5a9968b9b4))  by @mineralsfree

- *(gui)* Added chinese server to login notifications
([MEN-8770](https://northerntech.atlassian.net/browse/MEN-8770)) ([ac933a0](https://github.com/mendersoftware/mender-server-enterprise/commit/ac933a083e936486673d0eb8dc8c544350304493))  by @mzedel

- *(gui)* Added improved success payment modal
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([f56e4c6](https://github.com/mendersoftware/mender-server-enterprise/commit/f56e4c64333876fce83b484baed36b0d7a27069b))  by @mineralsfree

- *(gui)* Let confirmation modal to delay the logout after token invalidation
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([2a1a71e](https://github.com/mendersoftware/mender-server-enterprise/commit/2a1a71e76e4d029d030d01ea09e1c0753d783890))  by @mineralsfree

- *(gui)* Added delta artifact generation job retrieval functionality
 ([66e577a](https://github.com/mendersoftware/mender-server-enterprise/commit/66e577ad3872122a10f81627fa6518a2d985c3f5))  by @mzedel

- *(gui)* Added a way to see details about delta generation jobs
([MEN-8250](https://northerntech.atlassian.net/browse/MEN-8250)) ([36c6adf](https://github.com/mendersoftware/mender-server-enterprise/commit/36c6adfdaa51ff5a3ca243d691e290afbbcf9fce))  by @mzedel

- *(gui)* Added overview of recent delta generation jobs
([MEN-8251](https://northerntech.atlassian.net/browse/MEN-8251)) ([0ca8799](https://github.com/mendersoftware/mender-server-enterprise/commit/0ca8799dae18dca14f513fcb3ea48ca6335082f9))  by @mzedel

- *(gui)* Let release upload be focused on releases view to reduce confusion
([MEN-8248](https://northerntech.atlassian.net/browse/MEN-8248)) ([22bc53c](https://github.com/mendersoftware/mender-server-enterprise/commit/22bc53c41293450cb880c58fa5fda847f861ffa5))  by @mzedel

- *(useradm)* Require consent to enable AI features
([MEN-8677](https://northerntech.atlassian.net/browse/MEN-8677)) ([909a9bd](https://github.com/mendersoftware/mender-server-enterprise/commit/909a9bd0b1c47b692014353599021d201e29a561))  by @alfrunes


  There is an explicit option for enabling AI features in the global
  settings (`aiFeatures.enabled`), requiring admin access to allow
  using the feature.

- *(useradm)* New endpoint for submitting user feedback
([MEN-7603](https://northerntech.atlassian.net/browse/MEN-7603)) ([2f73a24](https://github.com/mendersoftware/mender-server-enterprise/commit/2f73a24cb9217d8cea65561bb4f3bdeff786f80b))  by @alfrunes


  POST /api/management/v2/useradm/support/feedback/:form_id
  
  The new endpoint accepts a form response with user feedback. There are
  currently two `form_id` defined: "product" and "feat.ai" for general
  product feedback and feedback specific to the experimental AI feature.

- *(useradm)* Send email notifications on password or email change
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([9472690](https://github.com/mendersoftware/mender-server-enterprise/commit/94726900cb732f6903bc35dec73e01e2943817f7))  by @kjaskiewiczz

- *(workflows)* Delete devicemonitor device when decommissioning devices
 ([6a25915](https://github.com/mendersoftware/mender-server-enterprise/commit/6a25915ecac07346111c9f30af0d4cd12e5d03a9))  by @frodeha

- *(workflows)* New workflow for sending email when user is changing email
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([48ec7e6](https://github.com/mendersoftware/mender-server-enterprise/commit/48ec7e674e275ebcbfaa5ea0b62a68fa61866e6a))  by @kjaskiewiczz

- *(workflows)* New workflow for sending email when user is changing password
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([f152900](https://github.com/mendersoftware/mender-server-enterprise/commit/f152900e34f1e03e6128da37265b1ee421b1888c))  by @kjaskiewiczz

- Enable server-side generation of delta artifacts by default for enterprise tenants
([MEN-7703](https://northerntech.atlassian.net/browse/MEN-7703)) ([ab2b3cf](https://github.com/mendersoftware/mender-server-enterprise/commit/ab2b3cfe2d53b9fc2ac435565e9c2c4d43adc8a9)) 




### Refactor


- *(deviceauth)* Remove tenantadm related code from OS
([MEN-8649](https://northerntech.atlassian.net/browse/MEN-8649)) ([31b9d2b](https://github.com/mendersoftware/mender-server-enterprise/commit/31b9d2beeb60a4485449f620ca58df580ba1cae9))  by @bahaa-ghazal





### Security


- Bump the development-dependencies group across 1 directory with 16 updates
 ([6ce2f8a](https://github.com/mendersoftware/mender-server-enterprise/commit/6ce2f8af551b6f7d51000c89083c953296c17068))  by @dependabot[bot]


  Bumps the development-dependencies group with 16 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.5.0` | `0.6.0` |
  | [@northern.tech/prettier-config](https://github.com/NorthernTechHQ/nt-gui) | `0.2.0` | `0.2.1` |
  | [@northern.tech/themes](https://github.com/NorthernTechHQ/nt-gui) | `0.2.0` | `0.3.0` |
  | [@northern.tech/typescript-config](https://github.com/NorthernTechHQ/nt-gui) | `0.1.3` | `0.2.0` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.4.8` | `1.4.11` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.4.8` | `1.4.11` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `4.0.0` | `4.1.1` |
  | [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) | `6.6.3` | `6.7.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.1.0` | `24.3.0` |
  | [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint/tree/HEAD/packages/eslint-plugin) | `8.38.0` | `8.39.1` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `4.7.0` | `5.0.0` |
  | [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) | `3.44.0` | `3.45.0` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `16.1.2` | `16.1.5` |
  | [msw](https://github.com/mswjs/msw) | `2.10.4` | `2.10.5` |
  | [typescript](https://github.com/microsoft/TypeScript) | `5.7.3` | `5.9.2` |
  | [undici](https://github.com/nodejs/undici) | `7.12.0` | `7.14.0` |
  
  
  
  Updates `@northern.tech/eslint-config` from 0.5.0 to 0.6.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.5.0...@northern.tech/eslint-config-0.6.0)
  
  Updates `@northern.tech/prettier-config` from 0.2.0 to 0.2.1
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/prettier-config-0.2.0...@northern.tech/prettier-config-0.2.1)
  
  Updates `@northern.tech/themes` from 0.2.0 to 0.3.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/themes-0.2.0...@northern.tech/themes-0.3.0)
  
  Updates `@northern.tech/typescript-config` from 0.1.3 to 0.2.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/typescript-config-0.1.3...@northern.tech/typescript-config-0.2.0)
  
  Updates `@rspack/cli` from 1.4.8 to 1.4.11
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.4.11/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.4.8 to 1.4.11
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.4.11/packages/rspack)
  
  Updates `@sentry/webpack-plugin` from 4.0.0 to 4.1.1
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/4.0.0...4.1.1)
  
  Updates `@testing-library/jest-dom` from 6.6.3 to 6.7.0
  - [Release notes](https://github.com/testing-library/jest-dom/releases)
  - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/jest-dom/compare/v6.6.3...v6.7.0)
  
  Updates `@types/node` from 24.1.0 to 24.3.0
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.38.0 to 8.39.1
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.39.1/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 4.7.0 to 5.0.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.0.0/packages/plugin-react)
  
  Updates `core-js` from 3.44.0 to 3.45.0
  - [Release notes](https://github.com/zloirock/core-js/releases)
  - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/zloirock/core-js/commits/v3.45.0/packages/core-js)
  
  Updates `lint-staged` from 16.1.2 to 16.1.5
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v16.1.2...v16.1.5)
  
  Updates `msw` from 2.10.4 to 2.10.5
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.10.4...v2.10.5)
  
  Updates `typescript` from 5.7.3 to 5.9.2
  - [Release notes](https://github.com/microsoft/TypeScript/releases)
  - [Changelog](https://github.com/microsoft/TypeScript/blob/main/azure-pipelines.release-publish.yml)
  - [Commits](https://github.com/microsoft/TypeScript/compare/v5.7.3...v5.9.2)
  
  Updates `undici` from 7.12.0 to 7.14.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.12.0...v7.14.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.6.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@northern.tech/prettier-config"
    dependency-version: 0.2.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@northern.tech/themes"
    dependency-version: 0.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@northern.tech/typescript-config"
    dependency-version: 0.2.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.4.11
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.4.11
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.1.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/jest-dom"
    dependency-version: 6.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.39.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.45.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.5
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.10.5
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: typescript
    dependency-version: 5.9.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.14.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump the production-dependencies group
 ([93d598c](https://github.com/mendersoftware/mender-server-enterprise/commit/93d598c45d73ccb1b4158781d85cb33b346afbe0))  by @dependabot[bot]


  Bumps the production-dependencies group in /frontend with 6 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `9.40.0` | `10.0.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.7.0` | `3.8.1` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.4.0` | `7.7.0` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.59.0` | `7.61.1` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.6.3` | `7.7.1` |
  | [tss-react](https://github.com/garronej/tss-react) | `4.9.18` | `4.9.19` |
  
  
  Updates `@sentry/react` from 9.40.0 to 10.0.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/9.40.0...10.0.0)
  
  Updates `@stripe/react-stripe-js` from 3.7.0 to 3.8.1
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.7.0...v3.8.1)
  
  Updates `@stripe/stripe-js` from 7.4.0 to 7.7.0
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.4.0...v7.7.0)
  
  Updates `react-hook-form` from 7.59.0 to 7.61.1
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.59.0...v7.61.1)
  
  Updates `react-router-dom` from 7.6.3 to 7.7.1
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.7.1/packages/react-router-dom)
  
  Updates `tss-react` from 4.9.18 to 4.9.19
  - [Release notes](https://github.com/garronej/tss-react/releases)
  - [Commits](https://github.com/garronej/tss-react/compare/v4.9.18...v4.9.19)
  
  ---
  updated-dependencies:
  - dependency-name: "@sentry/react"
    dependency-version: 10.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 3.8.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 7.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.61.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.7.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: tss-react
    dependency-version: 4.9.19
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump mermaid from 11.9.0 to 11.10.1 in /frontend
 ([f20bb82](https://github.com/mendersoftware/mender-server-enterprise/commit/f20bb82e79c924b12017a2eabdadd347e85cfae8))  by @dependabot[bot]


  Bumps [mermaid](https://github.com/mermaid-js/mermaid) from 11.9.0 to 11.10.1.
  - [Release notes](https://github.com/mermaid-js/mermaid/releases)
  - [Commits](https://github.com/mermaid-js/mermaid/compare/mermaid@11.9.0...mermaid@11.10.1)
  
  ---
  updated-dependencies:
  - dependency-name: mermaid
    dependency-version: 11.10.1
    dependency-type: indirect
  ...
- Bump the mui group in /frontend with 3 updates
 ([d6671fa](https://github.com/mendersoftware/mender-server-enterprise/commit/d6671fa9230cee890831fe47877c5a68e9dcb6ed))  by @dependabot[bot]


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.9.2 to 8.11.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.11.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the development-dependencies group
 ([ee210fa](https://github.com/mendersoftware/mender-server-enterprise/commit/ee210fae283177c0360da33513d54e11cff1a6b3))  by @dependabot[bot]


  Bumps the development-dependencies group in /frontend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.6.0` | `0.6.1` |
  | [@northern.tech/themes](https://github.com/NorthernTechHQ/nt-gui) | `0.3.0` | `0.3.1` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.4.11` | `1.5.1` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.4.11` | `1.5.1` |
  | [@rspack/plugin-react-refresh](https://github.com/rspack-contrib/rspack-plugin-react-refresh) | `1.4.3` | `1.5.0` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `4.1.1` | `4.2.0` |
  | [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) | `6.7.0` | `6.8.0` |
  | [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint/tree/HEAD/packages/eslint-plugin) | `8.39.1` | `8.41.0` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.0.0` | `5.0.2` |
  | [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) | `3.45.0` | `3.45.1` |
  | [undici](https://github.com/nodejs/undici) | `7.14.0` | `7.15.0` |
  | [vite-plugin-svgr](https://github.com/pd4d10/vite-plugin-svgr) | `4.3.0` | `4.5.0` |
  
  
  Updates `@northern.tech/eslint-config` from 0.6.0 to 0.6.1
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.6.0...@northern.tech/eslint-config-0.6.1)
  
  Updates `@northern.tech/themes` from 0.3.0 to 0.3.1
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/themes-0.3.0...@northern.tech/themes-0.3.1)
  
  Updates `@rspack/cli` from 1.4.11 to 1.5.1
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.1/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.4.11 to 1.5.1
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.1/packages/rspack)
  
  Updates `@rspack/plugin-react-refresh` from 1.4.3 to 1.5.0
  - [Release notes](https://github.com/rspack-contrib/rspack-plugin-react-refresh/releases)
  - [Commits](https://github.com/rspack-contrib/rspack-plugin-react-refresh/compare/v1.4.3...v1.5.0)
  
  Updates `@sentry/webpack-plugin` from 4.1.1 to 4.2.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/4.1.1...4.2.0)
  
  Updates `@testing-library/jest-dom` from 6.7.0 to 6.8.0
  - [Release notes](https://github.com/testing-library/jest-dom/releases)
  - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/jest-dom/compare/v6.7.0...v6.8.0)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.39.1 to 8.41.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.41.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 5.0.0 to 5.0.2
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.0.2/packages/plugin-react)
  
  Updates `core-js` from 3.45.0 to 3.45.1
  - [Release notes](https://github.com/zloirock/core-js/releases)
  - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/zloirock/core-js/commits/v3.45.1/packages/core-js)
  
  Updates `undici` from 7.14.0 to 7.15.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.14.0...v7.15.0)
  
  Updates `vite-plugin-svgr` from 4.3.0 to 4.5.0
  - [Release notes](https://github.com/pd4d10/vite-plugin-svgr/releases)
  - [Commits](https://github.com/pd4d10/vite-plugin-svgr/compare/v4.3.0...v4.5.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.6.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@northern.tech/themes"
    dependency-version: 0.3.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.5.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.5.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/plugin-react-refresh"
    dependency-version: 1.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.2.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/jest-dom"
    dependency-version: 6.8.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.41.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.0.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.45.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.15.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vite-plugin-svgr
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump github.com/ulikunitz/xz from 0.5.12 to 0.5.14 in /backend
 ([38f8599](https://github.com/mendersoftware/mender-server-enterprise/commit/38f8599baa51997ec41dffb28490a096c765ab46))  by @dependabot[bot]


  Bumps [github.com/ulikunitz/xz](https://github.com/ulikunitz/xz) from 0.5.12 to 0.5.14.
  - [Commits](https://github.com/ulikunitz/xz/compare/v0.5.12...v0.5.14)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/ulikunitz/xz
    dependency-version: 0.5.14
    dependency-type: indirect
  ...
- Bump the backend-tests-python-dependencies group across 2 directories with 9 updates
 ([ea1783d](https://github.com/mendersoftware/mender-server-enterprise/commit/ea1783dc61fc1c19a522c2118ca182ec5b899c22))  by @dependabot[bot]


  Bumps the backend-tests-python-dependencies group with 1 update in the /backend/services/iot-manager/tests directory: [requests](https://github.com/psf/requests).
  Bumps the backend-tests-python-dependencies group with 9 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.13.2` | `4.14.1` |
  | [certifi](https://github.com/certifi/python-certifi) | `2025.7.14` | `2025.8.3` |
  | [requests](https://github.com/psf/requests) | `2.32.4` | `2.32.5` |
  | [azure-iot-hub](https://github.com/Azure/azure-iot-hub-python) | `2.6.1` | `2.7.0` |
  | [boto3](https://github.com/boto/boto3) | `1.40.0` | `1.40.21` |
  | [cryptography](https://github.com/pyca/cryptography) | `45.0.5` | `45.0.7` |
  | [filelock](https://github.com/tox-dev/py-filelock) | `3.18.0` | `3.19.1` |
  | [stripe](https://github.com/stripe/stripe-python) | `12.4.0` | `12.5.0` |
  | [redis](https://github.com/redis/redis-py) | `6.2.0` | `6.4.0` |
  
  
  
  Updates `requests` from 2.32.4 to 2.32.5
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.4...v2.32.5)
  
  Updates `pymongo` from 4.13.2 to 4.14.1
  - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
  - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
  - [Commits](https://github.com/mongodb/mongo-python-driver/compare/4.13.2...4.14.1)
  
  Updates `certifi` from 2025.7.14 to 2025.8.3
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.07.14...2025.08.03)
  
  Updates `requests` from 2.32.4 to 2.32.5
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.4...v2.32.5)
  
  Updates `azure-iot-hub` from 2.6.1 to 2.7.0
  - [Changelog](https://github.com/Azure/azure-iot-hub-python/blob/main/RELEASE%20INSTRUCTIONS.md)
  - [Commits](https://github.com/Azure/azure-iot-hub-python/commits)
  
  Updates `boto3` from 1.40.0 to 1.40.21
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.0...1.40.21)
  
  Updates `cryptography` from 45.0.5 to 45.0.7
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.5...45.0.7)
  
  Updates `filelock` from 3.18.0 to 3.19.1
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.18.0...3.19.1)
  
  Updates `stripe` from 12.4.0 to 12.5.0
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.4.0...v12.5.0)
  
  Updates `redis` from 6.2.0 to 6.4.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v6.2.0...v6.4.0)
  
  ---
  updated-dependencies:
  - dependency-name: requests
    dependency-version: 2.32.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.14.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.8.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: requests
    dependency-version: 2.32.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: azure-iot-hub
    dependency-version: 2.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.21
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: filelock
    dependency-version: 3.19.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 6.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([690e8c8](https://github.com/mendersoftware/mender-server-enterprise/commit/690e8c8eca26aab215d5c3d401b411d45160935b))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 16 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.18.2` | `1.19.0` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.37.1` | `1.38.3` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.30.2` | `1.31.6` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.18.2` | `1.18.10` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.66.0` | `1.69.1` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.28.1` | `1.32.2` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.85.1` | `1.87.3` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.7` | `2.11.8` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.44.0` | `1.45.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.11.0` | `9.12.1` |
  | [github.com/spf13/cobra](https://github.com/spf13/cobra) | `1.9.1` | `1.10.1` |
  | [github.com/stretchr/testify](https://github.com/stretchr/testify) | `1.10.0` | `1.11.1` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.40.0` | `0.41.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.42.0` | `0.43.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.34.0` | `0.35.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.33.0` | `0.34.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.18.2 to 1.19.0
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/sdk-breaking-changes-guide-migration.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.18.2...sdk/azcore/v1.19.0)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.37.1 to 1.38.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.37.1...v1.38.3)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.30.2 to 1.31.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.30.2...config/v1.31.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.2 to 1.18.10
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.2...config/v1.18.10)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.66.0 to 1.69.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.66.0...service/iot/v1.69.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.28.1 to 1.32.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.28.1...v1.32.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.85.1 to 1.87.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.85.1...service/s3/v1.87.3)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.7 to 2.11.8
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.7...v2.11.8)
  
  Updates `github.com/nats-io/nats.go` from 1.44.0 to 1.45.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.44.0...v1.45.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.11.0 to 9.12.1
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.11.0...v9.12.1)
  
  Updates `github.com/spf13/cobra` from 1.9.1 to 1.10.1
  - [Release notes](https://github.com/spf13/cobra/releases)
  - [Commits](https://github.com/spf13/cobra/compare/v1.9.1...v1.10.1)
  
  Updates `github.com/stretchr/testify` from 1.10.0 to 1.11.1
  - [Release notes](https://github.com/stretchr/testify/releases)
  - [Commits](https://github.com/stretchr/testify/compare/v1.10.0...v1.11.1)
  
  Updates `golang.org/x/crypto` from 0.40.0 to 0.41.0
  - [Commits](https://github.com/golang/crypto/compare/v0.40.0...v0.41.0)
  
  Updates `golang.org/x/net` from 0.42.0 to 0.43.0
  - [Commits](https://github.com/golang/net/compare/v0.42.0...v0.43.0)
  
  Updates `golang.org/x/sys` from 0.34.0 to 0.35.0
  - [Commits](https://github.com/golang/sys/compare/v0.34.0...v0.35.0)
  
  Updates `golang.org/x/term` from 0.33.0 to 0.34.0
  - [Commits](https://github.com/golang/term/compare/v0.33.0...v0.34.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.19.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.38.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.6
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.10
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.87.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.8
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.45.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.12.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/cobra
    dependency-version: 1.10.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/stretchr/testify
    dependency-version: 1.11.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.41.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.43.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.35.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the e2e-test-dependencies group
 ([3810c06](https://github.com/mendersoftware/mender-server-enterprise/commit/3810c06373de41fa923bf9d2ac206bc37fd762e9))  by @dependabot[bot]


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 2 updates: [dayjs](https://github.com/iamkun/dayjs) and [yaml](https://github.com/eemeli/yaml).
  
  
  Updates `dayjs` from 1.11.13 to 1.11.18
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/v1.11.18/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.13...v1.11.18)
  
  Updates `yaml` from 2.8.0 to 2.8.1
  - [Release notes](https://github.com/eemeli/yaml/releases)
  - [Commits](https://github.com/eemeli/yaml/compare/v2.8.0...v2.8.1)
  
  ---
  updated-dependencies:
  - dependency-name: dayjs
    dependency-version: 1.11.18
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: yaml
    dependency-version: 2.8.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  ...
- Bump @playwright/test
 ([57a1922](https://github.com/mendersoftware/mender-server-enterprise/commit/57a1922e84a64935cdb3305a03a51678a48585af))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.54.2 to 1.55.0
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.54.2...v1.55.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.55.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump github.com/redis/go-redis/v9
 ([ee255e2](https://github.com/mendersoftware/mender-server-enterprise/commit/ee255e2351698964d064b4fa0b7bac2efa3c9d7f))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 1 update: [github.com/redis/go-redis/v9](https://github.com/redis/go-redis).
  
  
  Updates `github.com/redis/go-redis/v9` from 9.12.1 to 9.13.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.12.1...v9.13.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.13.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 2 updates
 ([b1fb007](https://github.com/mendersoftware/mender-server-enterprise/commit/b1fb0078c69f82c459bcfe5753f84d72355556f2))  by @dependabot[bot]


  Bumps the backend-tests-python-dependencies group with 2 updates in the /backend/tests directory: [pytest](https://github.com/pytest-dev/pytest) and [boto3](https://github.com/boto/boto3).
  
  
  Updates `pytest` from 8.4.1 to 8.4.2
  - [Release notes](https://github.com/pytest-dev/pytest/releases)
  - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest/compare/8.4.1...8.4.2)
  
  Updates `boto3` from 1.40.21 to 1.40.24
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.21...1.40.24)
  
  ---
  updated-dependencies:
  - dependency-name: pytest
    dependency-version: 8.4.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.24
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump vite from 7.0.6 to 7.1.5 in /frontend
 ([fd3c822](https://github.com/mendersoftware/mender-server-enterprise/commit/fd3c8223d58894792976e2ac08eaf05d5f61d31c))  by @dependabot[bot]


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 7.0.6 to 7.1.5.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v7.1.5/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 7.1.5
    dependency-type: indirect
  ...
- Bump axios from 1.11.0 to 1.12.0 in /frontend
 ([b460d89](https://github.com/mendersoftware/mender-server-enterprise/commit/b460d8916f2562686675b8d327a7974901a0ddc4))  by @dependabot[bot]


  Bumps [axios](https://github.com/axios/axios) from 1.11.0 to 1.12.0.
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.11.0...v1.12.0)
  
  ---
  updated-dependencies:
  - dependency-name: axios
    dependency-version: 1.12.0
    dependency-type: direct:production
  ...
- Bump the backend-docker-compose-dependencies group across 2 directories with 4 updates
 ([020619a](https://github.com/mendersoftware/mender-server-enterprise/commit/020619a35768dd1682f5128a8a98bcaa07e59819))  by @dependabot[bot]


  Bumps the backend-docker-compose-dependencies group with 2 updates in the / directory: traefik and nats.
  Bumps the backend-docker-compose-dependencies group with 2 updates in the /compose directory: redis and chrislusf/seaweedfs.
  
  
  Updates `traefik` from v3.1 to 3.5
  
  Updates `nats` from 2.10 to 2.11
  
  Updates `redis` from 7.2 to 8.2
  
  Updates `chrislusf/seaweedfs` from 3.85 to 3.97
  
  ---
  updated-dependencies:
  - dependency-name: traefik
    dependency-version: '3.5'
    dependency-type: direct:production
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: nats
    dependency-version: '2.11'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: redis
    dependency-version: '8.2'
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '3.97'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...






## 4.1.0-saas.13 - 2025-08-16


### Bug fixes


- *(deployments)* Wrong version on delta/jobs endpoints
 ([5c64290](https://github.com/mendersoftware/mender-server-enterprise/commit/5c6429007b7331a49c137c95ab3fed5d9deaf09b))  by @merlin-northern

- *(workflows)* Move inventory to end of decommission workflow
 ([355fcd9](https://github.com/mendersoftware/mender-server-enterprise/commit/355fcd91eeb0a0e3cd5d2fb4005d213b00b2a524))  by @alfrunes


  To lower the probability of failed decommission causing the device not
  to show up in the UI. By not removing the device from inventory it is
  possible to initiate the retry from the UI.





### Documentation


- *(useradm)* Move API specification to single file
([QA-1094](https://northerntech.atlassian.net/browse/QA-1094)) ([9bcf6cf](https://github.com/mendersoftware/mender-server-enterprise/commit/9bcf6cf82123f35dc0a0ff7869d0bcd30869aeff))  by @kjaskiewiczz





### Features


- *(workflows)* Support both pull and push mode consumer
([MEN-8326](https://northerntech.atlassian.net/browse/MEN-8326)) ([4a93316](https://github.com/mendersoftware/mender-server-enterprise/commit/4a9331623ffcd19435620ff845c788d3a0e869e2))  by @bahaa-ghazal

- *(workflows)* Add CLI flag to migrate consumers from push to pull mode
 ([8b9a9a2](https://github.com/mendersoftware/mender-server-enterprise/commit/8b9a9a2aeb9dc9406dab6497594d94d156f510e1))  by @bahaa-ghazal





### Security


- Bump the backend-tests-python-dependencies group across 1 directory with 4 updates
 ([43f7d7f](https://github.com/mendersoftware/mender-server-enterprise/commit/43f7d7f647d31124d0d6497e8d10862202f66536))  by @dependabot[bot]


  Bumps the backend-tests-python-dependencies group with 4 updates in the /backend/tests directory: [boto3](https://github.com/boto/boto3), [certifi](https://github.com/certifi/python-certifi), [cryptography](https://github.com/pyca/cryptography) and [stripe](https://github.com/stripe/stripe-python).
  
  
  Updates `boto3` from 1.39.0 to 1.40.0
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.39.0...1.40.0)
  
  Updates `certifi` from 2025.6.15 to 2025.7.14
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.06.15...2025.07.14)
  
  Updates `cryptography` from 45.0.4 to 45.0.5
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.4...45.0.5)
  
  Updates `stripe` from 12.2.0 to 12.4.0
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.2.0...v12.4.0)
  
  ---
  updated-dependencies:
  - dependency-name: boto3
    dependency-version: 1.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.7.14
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...






## 4.1.0-saas.12 - 2025-08-12


### Bug fixes


- *(gui)* Reject configuration deployment with too long field length
([MEN-8123](https://northerntech.atlassian.net/browse/MEN-8123)) ([c95e30f](https://github.com/mendersoftware/mender-server-enterprise/commit/c95e30fae4687dbf1b17e742c0ef3c5900384b01))  by @bahaa-ghazal

- *(gui)* Prevented a situation that created the appearance we support multiple integrations
 ([1dba715](https://github.com/mendersoftware/mender-server-enterprise/commit/1dba715184b01835b42dc09001fab29d506b4754))  by @mzedel

- *(gui)* Let artifact type filtering no longer autoselect an option to reduce user confusion
 ([f77aaee](https://github.com/mendersoftware/mender-server-enterprise/commit/f77aaeeaf164d7310f2456c629c03cc3ab416192))  by @mzedel

- *(gui)* Fixed an issue that prevented showing details of a auditlogged portforward session
 ([a807849](https://github.com/mendersoftware/mender-server-enterprise/commit/a807849137af0a2470e2a0bbb4d53d1f3e7b25a2))  by @mzedel


  - extracted the shared logic to a reusable hook to improve reusability of the working approach

- *(gui)* Added proper links to subscription addon
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([c32a427](https://github.com/mendersoftware/mender-server-enterprise/commit/c32a4272c7385edbb1a7837705cdf99878aa17b0))  by @mineralsfree

- *(gui)* Adjusted price parsing for the new stripe configuration
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([951d3af](https://github.com/mendersoftware/mender-server-enterprise/commit/951d3af8c1509fb7bfebaa913428d9c5466e672a))  by @mineralsfree

- *(gui)* Adjusted billing page for older customers to exclude upgrade page
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([2c0de68](https://github.com/mendersoftware/mender-server-enterprise/commit/2c0de680085518b5cabea33db73543986de61725))  by @mineralsfree

- *(gui)* Aligned license report download location w/ backend expectation
([MEN-8447](https://northerntech.atlassian.net/browse/MEN-8447)) ([4a638e2](https://github.com/mendersoftware/mender-server-enterprise/commit/4a638e2bb9f48b7802fb4d5366a9cbc7bac7716f))  by @mzedel

- *(gui)* Fixed an issue that would prevent showing updated pagination info in some situations
 ([989d785](https://github.com/mendersoftware/mender-server-enterprise/commit/989d78577f7e79aa67508ed94f0da3fdb418b750))  by @mzedel

- *(tenantadm)* `create-org` CLI correctly handles 404 response from workflows
 ([96b2ae2](https://github.com/mendersoftware/mender-server-enterprise/commit/96b2ae2b58e2536997afb054e437384e4849225b))  by @alfrunes

- *(tenantadm)* Make plan bindings config path optional
 ([becc5f8](https://github.com/mendersoftware/mender-server-enterprise/commit/becc5f8e170be87376ee4d406877e6876e10e65f))  by @alfrunes


  Hard-coded the defaults instead of always loading the file which may
  cause unnecessary headaches when trying to execute the binary without
  the config file in the right path.

- *(tenantadm)* Prevent creating child tenant without users
([MEN-8261](https://northerntech.atlassian.net/browse/MEN-8261)) ([01c3fee](https://github.com/mendersoftware/mender-server-enterprise/commit/01c3fee5a5329eac587fa754f229a815d1282e35))  by @bahaa-ghazal

- *(useradm)* Enforce `sso` subject to match email or signup request
([MEN-8513](https://northerntech.atlassian.net/browse/MEN-8513)) ([549d78b](https://github.com/mendersoftware/mender-server-enterprise/commit/549d78b615aa9e327cf95873b3135ab058ad56ba))  by @alfrunes


  This commit changes the endpoints for adding users with `sso` attribute
  set in the request to always validate the subject against the user email
  or signup request.
  The email and login ID from the identity provider is cached at signup
  and is used for validating the user creation request.

- *(useradm)* Make email required when signing up and logging in with oauth2
([MEN-8513](https://northerntech.atlassian.net/browse/MEN-8513)) ([197a92a](https://github.com/mendersoftware/mender-server-enterprise/commit/197a92a103b16ddd86c19da47c71ce5a537839b7))  by @alfrunes

- *(useradm)* Validate User `sso` values with configured providers
([MEN-8513](https://northerntech.atlassian.net/browse/MEN-8513)) ([83e5abf](https://github.com/mendersoftware/mender-server-enterprise/commit/83e5abf49da0b0f296d870cd9f320c693ae0a99f))  by @alfrunes

- *(useradm)* Use configured base URL for OAuth2 redirects
([MEN-8502](https://northerntech.atlassian.net/browse/MEN-8502)) ([aeb7deb](https://github.com/mendersoftware/mender-server-enterprise/commit/aeb7deba0a88a77a835fa59d32fb0dc1f2d45072))  by @alfrunes


  Removes the use of X-Forwarded-Host when generating the redirect URL for
  OAuth2 login and instead rely on the configured value `base_url` (env:
  USERADM_BASE_URL).

- Allow user to see devices info when having read permission
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([758214b](https://github.com/mendersoftware/mender-server-enterprise/commit/758214b50388aa996707caf088db2c3023a86196)) 


  If user have a read permission to a device group, allow the user to see
  the devices information in a deployment sent to the device group.
- Ensure the enterprise backend to return JSON on no method or route
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([b5426ae](https://github.com/mendersoftware/mender-server-enterprise/commit/b5426ae6d89292e3e4fc414c4f30d355db3783e7)) 




### Documentation


- *(deployments)* Deprecate v1 GET `/artifacts/list` management endpoint
([MEN-8183](https://northerntech.atlassian.net/browse/MEN-8183)) ([2b308d5](https://github.com/mendersoftware/mender-server-enterprise/commit/2b308d55b0f08bde3a6d845fa260587bac328d7f)) 

- *(workflows)* Prepare API specification in OpenAPI format
([QA-893](https://northerntech.atlassian.net/browse/QA-893)) ([0986835](https://github.com/mendersoftware/mender-server-enterprise/commit/0986835db0a349d6ac776bc1fc95adc913c2e4f5))  by @kjaskiewiczz

- Adjusted documentation for release process
 ([3f8464f](https://github.com/mendersoftware/mender-server-enterprise/commit/3f8464fb1e9fbf852d09446021706d91146ccee2))  by @alfrunes


  Tried to reword some of the sections as it is quite confusing which
  sections to follow and which to ignore for a hosted Mender release.
  I also made the first step optional, requiring only checking for
  critical fixes for the enterprise sync PRs.




### Features


- *(gui)* Added plan & updated add-on description
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([7a9d144](https://github.com/mendersoftware/mender-server-enterprise/commit/7a9d144b4684f9fe5ccebaf45087afd92361e2d8))  by @mineralsfree

- *(gui)* Added subscription page component
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([ef47bcd](https://github.com/mendersoftware/mender-server-enterprise/commit/ef47bcdd50fa8c52fd54c4d43cab68c48f89594b))  by @mineralsfree

- *(gui)* Added subscription fetch to storehooks
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([e6b2dce](https://github.com/mendersoftware/mender-server-enterprise/commit/e6b2dce18e66c01673ed95a4a5ca379f1cc6f672))  by @mineralsfree

- *(gui)* Added subscription drawer & subscription page adjustments
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([22ee40f](https://github.com/mendersoftware/mender-server-enterprise/commit/22ee40f1180002cfef565231b620c0d8c444f0c3))  by @mineralsfree

- *(gui)* Added subscription page route
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([b4980a4](https://github.com/mendersoftware/mender-server-enterprise/commit/b4980a4e8d63a11c9851ded8e1fcf4937db34155))  by @mineralsfree

- *(gui)* Changed upgrade links to the new subscription page
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([215ae41](https://github.com/mendersoftware/mender-server-enterprise/commit/215ae4173bc1cb89ecc1b5f6e551ee354de54cc0))  by @mineralsfree

- *(gui)* Navigate user to a proper upgrade component depending on the current pricing
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([a8d66a7](https://github.com/mendersoftware/mender-server-enterprise/commit/a8d66a7c1ad6ac4aefacb4103c2db5e8093794df))  by @mineralsfree

- *(tenantadm)* Extend functionality of internal endpoint for getting tenants
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([56b77a2](https://github.com/mendersoftware/mender-server-enterprise/commit/56b77a2f2dc395d2c4c80bbe393b5b4508793f3e))  by @kjaskiewiczz


  Make it possible to filter tenants by plan and trial fields and to specify which fields
  resulting objects should contain.

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([07d5b18](https://github.com/mendersoftware/mender-server-enterprise/commit/07d5b18a1e7df6c710fad94d1d53c6173fadf013))  by @alfrunes


  Added the following configuration parameters:
  
  ```yaml
  ratelimits:
    # auth configures ratelimits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # reject_unmatched rejects requests that does not resolve to a
      # ratelimit group. That is, if either there's no api_pattern matching
      # the request or if the group_expression does not match a group.
      # Defaults to false - disable ratelimiting for unmatched requests.
      reject_unmatched: false
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups:
          # name defines the name of the group. The name is used in
          # match.group_expression to match an api_pattern with a group.
        - name: default
          # interval is the time interval when the rate limiter resets.
          interval: 1m
          # quota is the number of requests allowed in an interval.
          quota: 300
          # event_expression is a go template for grouping requests.
          # The following attributes are available in the context:
          # Identity - contains a subset of the JWT claims:
          # .Subject  (jwt:"sub")          string
          # .Tenant   (jwt:"mender.tenant") string
          # .Plan     (jwt:"mender.plan")   string
          # .Addons   (jwt:"mender.addons") []struct{Enabled bool; Name string}
          # .IsUser   (jwt:"mender.user")   bool
          # .IsDevice (jwt:"mender.device") bool
          # .Trial    (jwt:"mender.trial")  bool
          event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
          # More example groups:
      # - name: "example_slow_group_by_tenant"
      #   quota: 1
      #   interval: 30s
      #   event_expression: "{{with .Identity}}{{.Tenant}}{{end}}"
      # match specifies matching expressions for mapping API requests to rate
      # limiting groups.
      match:
          # api_pattern specifies an API path pattern as defined by http.ServeMux
          # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
        - api_pattern: /
          # group_expression defines  the group for this matching expression.
          # A group can be selected dynamically using Go templates or statically
          # with a literal string.
          # See group.event_expression for template context attributes.
          group_expression: "default"
          # More example match rules:
      # - api_pattern: /api/management/v1/useradm/expample/slow/api/
      #   group_expression: "example_slow_group_by_tenant"
      # - api_pattern: /api/management/v1/useradm/expample/slow/api/
      #   group_expression: >
      #     {{-if .Identity.Trial-}}
      #     example_slow_group_by_tenant
      #     {{-else-}}
      #     default
      #     {{-end-}}
  ```

- *(useradm)* CLI command for getting and exporting usage statistics
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([2c81c3b](https://github.com/mendersoftware/mender-server-enterprise/commit/2c81c3b1b7d5e174c96dc4161cd0b218f3ca94de))  by @kjaskiewiczz

- *(workflows)* New workflow for exporting useradm stats into google spreadsheet
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([a29fdd6](https://github.com/mendersoftware/mender-server-enterprise/commit/a29fdd66a94c7a074193a59b07bd7b8e5510443f))  by @kjaskiewiczz

- Restrict the child tenants SSO changes to the parent tenant SSO
([ME-535](https://northerntech.atlassian.net/browse/ME-535)) ([d704951](https://github.com/mendersoftware/mender-server-enterprise/commit/d704951a865664f066139466a46d35434f5fcce5))  by @merlin-northern


  Support locking the SSO configuration for the child tenants
  to the configuration given by the parent.




### Refactor


- *(gui)* Unified session details display for device connect sessions
 ([8d526ae](https://github.com/mendersoftware/mender-server-enterprise/commit/8d526ae8433393c7f7095fea299e44d17e7ab588))  by @mzedel

- *(tenantadm)* Do not embed stripe.API inside internal client
 ([341719d](https://github.com/mendersoftware/mender-server-enterprise/commit/341719d0bd5298e5998c7b5cf6c2b4cea3eebfa6))  by @alfrunes

- *(useradm)* Rename ErrForbidden to ErrFeatureUnavailableForPlan
 ([224639d](https://github.com/mendersoftware/mender-server-enterprise/commit/224639d2f0cdf70b3d7e531dcf44dfcf4ca58d8f))  by @alfrunes


  It's too easy to use this error variable in places where it shouldn't
  be.

- *(useradm)* Bake some new consts for oauth2 signup cookies
 ([f5e5afd](https://github.com/mendersoftware/mender-server-enterprise/commit/f5e5afdbc8cd8188834badc3a8c9424434dac248))  by @alfrunes





### Security


- Bump @playwright/test
 ([4cfded4](https://github.com/mendersoftware/mender-server-enterprise/commit/4cfded4336983d99e3a09433e9d48893abee1b4a))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.53.2 to 1.54.2
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.53.2...v1.54.2)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.54.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump typescript
 ([72c1988](https://github.com/mendersoftware/mender-server-enterprise/commit/72c19882bc010834c45e144d61591bcc2b6338ee))  by @dependabot[bot]


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 1 update: [typescript](https://github.com/microsoft/TypeScript).
  
  
  Updates `typescript` from 5.8.3 to 5.9.2
  - [Release notes](https://github.com/microsoft/TypeScript/releases)
  - [Changelog](https://github.com/microsoft/TypeScript/blob/main/azure-pipelines.release-publish.yml)
  - [Commits](https://github.com/microsoft/TypeScript/compare/v5.8.3...v5.9.2)
  
  ---
  updated-dependencies:
  - dependency-name: typescript
    dependency-version: 5.9.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump @mui/x-date-pickers in /frontend in the mui group
 ([89980f5](https://github.com/mendersoftware/mender-server-enterprise/commit/89980f56cdf3d84e4e28a034f49caea1a56464fa))  by @dependabot[bot]


  Bumps the mui group in /frontend with 1 update: [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/x-date-pickers` from 8.6.0 to 8.9.2
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.9.2/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.9.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([0ce201b](https://github.com/mendersoftware/mender-server-enterprise/commit/0ce201b6acee13f14559f49f3bc1cf73bc584917))  by @dependabot[bot]


  Bumps the backend-docker-dependencies group with 2 updates in the /backend/services/create-artifact-worker directory: golang and alpine.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `alpine` from 3.22.0 to 3.22.1
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([ea75028](https://github.com/mendersoftware/mender-server-enterprise/commit/ea750287738af93cf168f3e6229684c3d00e796e))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 15 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.18.0` | `1.18.2` |
  | [github.com/Azure/azure-sdk-for-go/sdk/storage/azblob](https://github.com/Azure/azure-sdk-for-go) | `1.6.1` | `1.6.2` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.36.5` | `1.37.1` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.29.17` | `1.30.2` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.17.70` | `1.18.2` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.64.4` | `1.66.0` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.27.4` | `1.28.1` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.82.0` | `1.85.1` |
  | [github.com/go-viper/mapstructure/v2](https://github.com/go-viper/mapstructure) | `2.3.0` | `2.4.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.6` | `2.11.7` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.43.0` | `1.44.0` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.39.0` | `0.40.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.41.0` | `0.42.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.33.0` | `0.34.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.32.0` | `0.33.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.18.0 to 1.18.2
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/go-mgmt-sdk-release-guideline.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.18.0...sdk/azcore/v1.18.2)
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/storage/azblob` from 1.6.1 to 1.6.2
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/go-mgmt-sdk-release-guideline.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.6.1...sdk/storage/azblob/v1.6.2)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.36.5 to 1.37.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.36.5...v1.37.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.29.17 to 1.30.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.29.17...v1.30.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.17.70 to 1.18.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/config/v1.18.2/CHANGELOG.md)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/credentials/v1.17.70...config/v1.18.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.64.4 to 1.66.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.64.4...service/s3/v1.66.0)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.27.4 to 1.28.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.27.4...config/v1.28.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.82.0 to 1.85.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.82.0...service/s3/v1.85.1)
  
  Updates `github.com/go-viper/mapstructure/v2` from 2.3.0 to 2.4.0
  - [Release notes](https://github.com/go-viper/mapstructure/releases)
  - [Changelog](https://github.com/go-viper/mapstructure/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/go-viper/mapstructure/compare/v2.3.0...v2.4.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.6 to 2.11.7
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.6...v2.11.7)
  
  Updates `github.com/nats-io/nats.go` from 1.43.0 to 1.44.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.43.0...v1.44.0)
  
  Updates `golang.org/x/crypto` from 0.39.0 to 0.40.0
  - [Commits](https://github.com/golang/crypto/compare/v0.39.0...v0.40.0)
  
  Updates `golang.org/x/net` from 0.41.0 to 0.42.0
  - [Commits](https://github.com/golang/net/compare/v0.41.0...v0.42.0)
  
  Updates `golang.org/x/sys` from 0.33.0 to 0.34.0
  - [Commits](https://github.com/golang/sys/compare/v0.33.0...v0.34.0)
  
  Updates `golang.org/x/term` from 0.32.0 to 0.33.0
  - [Commits](https://github.com/golang/term/compare/v0.32.0...v0.33.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.18.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/storage/azblob
    dependency-version: 1.6.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.37.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.30.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.66.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.28.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.85.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/go-viper/mapstructure/v2
    dependency-version: 2.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.44.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.33.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...




### Build


- *(gui)* Added HMR enabled dev option
 ([4eb4d22](https://github.com/mendersoftware/mender-server-enterprise/commit/4eb4d22f357acf104e083d9c2477a1b5aac79f18))  by @mzedel







## 4.1.0-saas.11 - 2025-07-28


### Bug fixes


- *(deviceauth)* Fix the pagination logic in devices search endpoint
([MEN-8521](https://northerntech.atlassian.net/browse/MEN-8521)) ([5431bc1](https://github.com/mendersoftware/mender-server-enterprise/commit/5431bc1f6b91379021c633cc2c7d3e29ad31c1d9)) 

- *(deviceconnect)* Increase the file upload size limit
 ([6ff38c3](https://github.com/mendersoftware/mender-server-enterprise/commit/6ff38c39c3a04a37e52098a7d21225bb310c6e1f))  by @bahaa-ghazal

- *(gui)* Restricted to use id when adding users on trial plan
([ME-532](https://northerntech.atlassian.net/browse/ME-532)) ([20f8936](https://github.com/mendersoftware/mender-server-enterprise/commit/20f89367ae97779489c2decfc5d38b9b59d9cf02))  by @mineralsfree

- *(inventory)* Invalid path for device attribute route
([MEN-8216](https://northerntech.atlassian.net/browse/MEN-8216)) ([c4a439b](https://github.com/mendersoftware/mender-server-enterprise/commit/c4a439b3224b112c8b40eff5fbbee6c8438db5b4))  by @alfrunes


  Not a regression as routing is still handled by the gateway, using the
  legacy path names.

- *(gui)* Fixed billing profile not being fetched
 ([9042c6b](https://github.com/mendersoftware/mender-server-enterprise/commit/9042c6be7ccc445a5affca63b65559bb562e6597)) 

- *(gui)* Fixed a problem that could apply RBAC restrictions on non-RBAC plans
([MEN-8498](https://northerntech.atlassian.net/browse/MEN-8498)) ([c870092](https://github.com/mendersoftware/mender-server-enterprise/commit/c87009221163505732cb677e44a9c159233c3d68)) 

- *(gui)* Fixed an issue that could cause the organization token to overflow for older tenants
 ([e04f0e9](https://github.com/mendersoftware/mender-server-enterprise/commit/e04f0e99df3c4edcd932034bc3d0aad31bd8467f)) 

- *(gui)* Fixed another situation that could cause the organization token to overflow
 ([555cb1e](https://github.com/mendersoftware/mender-server-enterprise/commit/555cb1e7ec1571bd5ed02104c1185138b6e25d4a)) 

- *(gui)* Restricted to use id when adding users on trial plan
([ME-532](https://northerntech.atlassian.net/browse/ME-532)) ([20f8936](https://github.com/mendersoftware/mender-server-enterprise/commit/20f89367ae97779489c2decfc5d38b9b59d9cf02)) 

- *(tenantadm)* Aligned api specs w/ code it should represent
 ([d6b4c7f](https://github.com/mendersoftware/mender-server-enterprise/commit/d6b4c7f1b23f4e448108c73c3f396f7a7d636d59))  by @mzedel

- *(useradm)* Always generate a unique user ID for newly created users
([MEN-8514](https://northerntech.atlassian.net/browse/MEN-8514)) ([85e0ea9](https://github.com/mendersoftware/mender-server-enterprise/commit/85e0ea9351a6afc981f0719e66b69a73aad0a0b9))  by @alfrunes

- Make all routes response with JSON when route or method missing
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([0825b4d](https://github.com/mendersoftware/mender-server-enterprise/commit/0825b4d8bcaf40e9e747247f7f7f5a5031c37c8a))  by @bahaa-ghazal
- Ensure that middlewares are set in the correct order
([MEN-8587](https://northerntech.atlassian.net/browse/MEN-8587)) ([e3d1101](https://github.com/mendersoftware/mender-server-enterprise/commit/e3d1101bf5dcdf41090ed50ae8c52920b162734e))  by @bahaa-ghazal
- Allow user to see devices info when having read permission
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([758214b](https://github.com/mendersoftware/mender-server-enterprise/commit/758214b50388aa996707caf088db2c3023a86196))  by @bahaa-ghazal


  If user have a read permission to a device group, allow the user to see
  the devices information in a deployment sent to the device group.
- Ensure the enterprise backend to return JSON on no method or route
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([b5426ae](https://github.com/mendersoftware/mender-server-enterprise/commit/b5426ae6d89292e3e4fc414c4f30d355db3783e7))  by @bahaa-ghazal




### Documentation


- *(deployments)* Create API spec for v2 GET `artifacts` endpoint
([MEN-8180](https://northerntech.atlassian.net/browse/MEN-8180)) ([081969d](https://github.com/mendersoftware/mender-server-enterprise/commit/081969dc39b9bef720f5efe19e3e53b6da972403))  by @bahaa-ghazal

- *(deployments)* Deprecate v1 GET `/artifacts/list` management endpoint
([MEN-8183](https://northerntech.atlassian.net/browse/MEN-8183)) ([2b308d5](https://github.com/mendersoftware/mender-server-enterprise/commit/2b308d55b0f08bde3a6d845fa260587bac328d7f))  by @bahaa-ghazal

- *(tenantadm)* Add API specification for billing profile registration
 ([fb1e172](https://github.com/mendersoftware/mender-server-enterprise/commit/fb1e1720d05662c8b36f24576ed0fb7fc4d8ccaa))  by @alfrunes





### Features


- *(deployments)* Implement new v2 GET `/artifacts` endpoint
([MEN-8181](https://northerntech.atlassian.net/browse/MEN-8181)) ([8e3e25c](https://github.com/mendersoftware/mender-server-enterprise/commit/8e3e25c4446630e49cf5b4f9a0e8cb68fb645827))  by @bahaa-ghazal

- *(deployments)* New internal endpoint to get deployment device groups
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([1e2e380](https://github.com/mendersoftware/mender-server-enterprise/commit/1e2e380cdddee6b0450b62fa0869ab631d0d94e5))  by @bahaa-ghazal

- *(gui)* Let UI aggregate all device software again - not just rootfs info
 ([cfa3712](https://github.com/mendersoftware/mender-server-enterprise/commit/cfa3712ecfd833c0c31151e114b4dd2456665666)) 


  - due to the continued absence of the reporting backend this is re-introduced, but now in combination with the report scoped device retrieval

- *(tenantadm)* New endpoint to view current subscription
 ([3a5ceec](https://github.com/mendersoftware/mender-server-enterprise/commit/3a5ceecac585a4c887b5dede7c6cc715de17de0b))  by @alfrunes


  The new endpoint GET /api/management/v2/billing/subscription
  retrieves the current Subscription.

- *(tenantadm)* API endpoint for registering billing profile
([MEN-8455](https://northerntech.atlassian.net/browse/MEN-8455)) ([ba80ea3](https://github.com/mendersoftware/mender-server-enterprise/commit/ba80ea345ac2ef3bf320f8e752f967355b049b26))  by @alfrunes


  This is a replacement for the previous /upgrade API.

- *(useradm)* Backport redis settings to useradm open source
 ([0e3e894](https://github.com/mendersoftware/mender-server-enterprise/commit/0e3e8940a73131a52e3116bc0980b2ffb57a5e1d))  by @alfrunes


  Exposes two new settings for configuring Redis with useradm open source:
  * redis_connection_string - connection URL to connect to a redis server
    * Exmple: redis://my.redis.fqdn
  * redis_key_prefix - a string that will be prepended to every SET
    operation done by this application.
    * Default: useradm:v1

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([172e232](https://github.com/mendersoftware/mender-server-enterprise/commit/172e23249bfe8bb42d411e584a5a9f3d332e02cf))  by @alfrunes


  Added the following configuration parameters:
  
  ```yaml
  ratelimits:
   # auth configures ratelimits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # default rate limit group is the default ratelimiting parameters used when
      # no group `match`es the expressions.
      default:
        quota: 100    # number of request per
        interval: 60s # interval
        # event_expression is a go template for grouping requests.
        # The following attributes are available in the context:
        # Identity - contains a subset of the JWT claims:
          - .Subject  (jwt:"sub")          string
          - .Tenant   (jwt:"mender.tenant) string
          - .Plan     (jwt:"mender.plan)   string
          - .Addons   (jwt:"mender.addons) struct{Enabled bool; Name string}
          - .IsUser   (jwt:"mender.user)   bool
          - .IsDevice (jwt:"mender.device) bool
          - .Trial    (jwt:"mender.trial)  bool
        event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups: []
      # Example:
      # - name: "slow"
      #   quota: 1
      #   interval: 30s
      #   event_expression: "{{with .Identity}}{{.Tenant}}{{end}}"
      # match specifies matching expressions for mapping API requests to rate
      # limiting groups.
      match: []
      # Example:
      #   # api_pattern specifies an API path pattern as defined by http.ServeMux
      #   # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
      # - api_pattern: /api/management/v1/useradm/slow/api
      #   # group_expression defines the group for this matching expression.
      #   # a group can be selected dynamically using Go templates.
      #   # The template context is the same as ratelimits.default.event_expression
      #   group_expression: "slow"
  ```

- *(useradm)* Add a deployments client with `AreInDeploymentGroups` method
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([519ba94](https://github.com/mendersoftware/mender-server-enterprise/commit/519ba94902f3075f50e4bee8bd5d9222a8bd49bb))  by @bahaa-ghazal

- Integrate requestsize middleware into deployments
 ([c957f12](https://github.com/mendersoftware/mender-server-enterprise/commit/c957f1210db1de0e2d748cfff2f348f63d64edd6))  by @bahaa-ghazal
- Integrate requestsize middleware into deviceauth
 ([a67ade9](https://github.com/mendersoftware/mender-server-enterprise/commit/a67ade9d1ea7609df515a44396680e4101c9f5e9))  by @bahaa-ghazal
- Integrate requestsize middleware into deviceconfig
 ([5cac8ca](https://github.com/mendersoftware/mender-server-enterprise/commit/5cac8ca0f260f16966ad3cb5e605dd193833dcb1))  by @bahaa-ghazal
- Integrate requestsize middleware into deviceconnect
 ([7ca1025](https://github.com/mendersoftware/mender-server-enterprise/commit/7ca10258c293d32fdc8e1567811b5ffe1f4a23fb))  by @bahaa-ghazal
- Integrate requestsize middleware into inventory
 ([9b2ed08](https://github.com/mendersoftware/mender-server-enterprise/commit/9b2ed083119aaea30226f1e9cd80025cbd0b4001))  by @bahaa-ghazal
- Integrate requestsize middleware into iot-manager
 ([7135c16](https://github.com/mendersoftware/mender-server-enterprise/commit/7135c16f1fbdcfd75b3eda787d0146b3e0ed3ac8))  by @bahaa-ghazal
- Integrate requestsize middleware into reporting
 ([0a1797a](https://github.com/mendersoftware/mender-server-enterprise/commit/0a1797a636c8400b6027d46f6d703351aa586d32))  by @bahaa-ghazal
- Integrate requestsize middleware into useradm
 ([bf7b3b5](https://github.com/mendersoftware/mender-server-enterprise/commit/bf7b3b591599962839178ce0dc712911a449bd8e))  by @bahaa-ghazal




### Refactor


- *(deployments)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([a03820f](https://github.com/mendersoftware/mender-server-enterprise/commit/a03820f22f542b67d8ecb9b37b28faaf57f34df3)) 

- *(gui)* Let chart adding + editing rely on rhf
 ([1f5f43f](https://github.com/mendersoftware/mender-server-enterprise/commit/1f5f43f83c97808fd08ac29388947d88ecda255c)) 

- *(pkg)* Create event aware Limiter and refactor redis limiter
 ([2ac56be](https://github.com/mendersoftware/mender-server-enterprise/commit/2ac56be82cc7c180526a5c902fccd3f46f0fffbd))  by @alfrunes

- *(useradm)* Create utility function to load JWT PKI
 ([e1e9c31](https://github.com/mendersoftware/mender-server-enterprise/commit/e1e9c31d4f14a906e3c76aba522e2d7c3143ead5))  by @alfrunes


  ... to lower cyclomatic complexity for main.RunServer.

- Remove rest_utils pkg and migrate existing utils to rest.utils
([MEN-8233](https://northerntech.atlassian.net/browse/MEN-8233)) ([b25a5f9](https://github.com/mendersoftware/mender-server-enterprise/commit/b25a5f944e3c25e6f7552d705c78351a7ce796ae))  by @bahaa-ghazal
- Remove unused ant0ine/go-json-rest utilities from deployments
 ([90dd5f8](https://github.com/mendersoftware/mender-server-enterprise/commit/90dd5f80af8bf35df2461dfe60939700062af8a0))
- Move integration fixtures to conftest.py and remove unused imports
 ([dae51c6](https://github.com/mendersoftware/mender-server-enterprise/commit/dae51c61cbf7a03b487c3307cbcb3c52ebbce44c))  by @alfrunes




### Security


- Bump on-headers, express-session and morgan
 ([873c2c0](https://github.com/mendersoftware/mender-server-enterprise/commit/873c2c001696c19965980485deb1c9fbcb7eb50f))  by @dependabot[bot]


  Bumps [on-headers](https://github.com/jshttp/on-headers), [express-session](https://github.com/expressjs/session) and [morgan](https://github.com/expressjs/morgan). These dependencies needed to be updated together.
  
  Updates `on-headers` from 1.0.2 to 1.1.0
  - [Release notes](https://github.com/jshttp/on-headers/releases)
  - [Changelog](https://github.com/jshttp/on-headers/blob/master/HISTORY.md)
  - [Commits](https://github.com/jshttp/on-headers/compare/v1.0.2...v1.1.0)
  
  Updates `express-session` from 1.18.1 to 1.18.2
  - [Release notes](https://github.com/expressjs/session/releases)
  - [Changelog](https://github.com/expressjs/session/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/session/compare/v1.18.1...v1.18.2)
  
  Updates `morgan` from 1.10.0 to 1.10.1
  - [Release notes](https://github.com/expressjs/morgan/releases)
  - [Changelog](https://github.com/expressjs/morgan/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/morgan/compare/1.10.0...1.10.1)
  
  ---
  updated-dependencies:
  - dependency-name: on-headers
    dependency-version: 1.1.0
    dependency-type: indirect
  - dependency-name: express-session
    dependency-version: 1.18.2
    dependency-type: indirect
  - dependency-name: morgan
    dependency-version: 1.10.1
    dependency-type: indirect
  ...
- Bump on-headers and compression in /frontend
 ([11cd11c](https://github.com/mendersoftware/mender-server-enterprise/commit/11cd11c4dce26cc951a7b261cec7efc65b5479c9))  by @dependabot[bot]


  Bumps [on-headers](https://github.com/jshttp/on-headers) and [compression](https://github.com/expressjs/compression). These dependencies needed to be updated together.
  
  Updates `on-headers` from 1.0.2 to 1.1.0
  - [Release notes](https://github.com/jshttp/on-headers/releases)
  - [Changelog](https://github.com/jshttp/on-headers/blob/master/HISTORY.md)
  - [Commits](https://github.com/jshttp/on-headers/compare/v1.0.2...v1.1.0)
  
  Updates `compression` from 1.8.0 to 1.8.1
  - [Release notes](https://github.com/expressjs/compression/releases)
  - [Changelog](https://github.com/expressjs/compression/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/compression/compare/1.8.0...v1.8.1)
  
  ---
  updated-dependencies:
  - dependency-name: on-headers
    dependency-version: 1.1.0
    dependency-type: indirect
  - dependency-name: compression
    dependency-version: 1.8.1
    dependency-type: indirect
  ...
- Bump the production-dependencies group
 ([8ff713b](https://github.com/mendersoftware/mender-server-enterprise/commit/8ff713b6206aaa16285056bc693c97a2d022c383))  by @dependabot[bot]


  ---
  updated-dependencies:
  - dependency-name: "@sentry/react"
    dependency-version: 9.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 7.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.10.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-big-calendar
    dependency-version: 1.19.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.59.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump @playwright/test
 ([0d169e8](https://github.com/mendersoftware/mender-server-enterprise/commit/0d169e861652ed22ec56df20737d2d51a233b787))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.53.0 to 1.53.2
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.53.0...v1.53.2)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.53.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: playwright
  ...
- Bump pbkdf2 from 3.1.2 to 3.1.3 in /frontend
 ([00e44b0](https://github.com/mendersoftware/mender-server-enterprise/commit/00e44b08654f8d2c3dedc22159db53fa98e88444))  by @dependabot[bot]


  Bumps [pbkdf2](https://github.com/crypto-browserify/pbkdf2) from 3.1.2 to 3.1.3.
  - [Changelog](https://github.com/browserify/pbkdf2/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/crypto-browserify/pbkdf2/compare/v3.1.2...v3.1.3)
  
  ---
  updated-dependencies:
  - dependency-name: pbkdf2
    dependency-version: 3.1.3
    dependency-type: indirect
  ...
- Bump form-data from 4.0.1 to 4.0.4 in /frontend
 ([1de20af](https://github.com/mendersoftware/mender-server-enterprise/commit/1de20af63d14ffcad40a756f3e5d65ec6a923dfd))  by @dependabot[bot]


  Bumps [form-data](https://github.com/form-data/form-data) from 4.0.1 to 4.0.4.
  - [Release notes](https://github.com/form-data/form-data/releases)
  - [Changelog](https://github.com/form-data/form-data/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/form-data/form-data/compare/v4.0.1...v4.0.4)
  
  ---
  updated-dependencies:
  - dependency-name: form-data
    dependency-version: 4.0.4
    dependency-type: indirect
  ...
- Bump axios from 1.10.0 to 1.11.0 in /frontend
 ([ec258ce](https://github.com/mendersoftware/mender-server-enterprise/commit/ec258ce841a5c473515533267253a063db056b7e))  by @dependabot[bot]


  Bumps [axios](https://github.com/axios/axios) from 1.10.0 to 1.11.0.
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.10.0...v1.11.0)
  
  ---
  updated-dependencies:
  - dependency-name: axios
    dependency-version: 1.11.0
    dependency-type: direct:production
  ...
- Bump mender-artifact to the latest version
 ([5091cc4](https://github.com/mendersoftware/mender-server-enterprise/commit/5091cc426c67b6140e7864bb9eedc7629cbed715))  by @alfrunes
- Bump the development-dependencies group across 1 directory with 14 updates
 ([f47ef65](https://github.com/mendersoftware/mender-server-enterprise/commit/f47ef651009e85b7574879e8702bbc704f1b7348))  by @dependabot[bot]


  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.0.15
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.37.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.44.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: globals
    dependency-version: 16.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.10.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: prettier
    dependency-version: 3.6.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.12.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump the mui group in /frontend with 4 updates
 ([0b504f6](https://github.com/mendersoftware/mender-server-enterprise/commit/0b504f67457dda2b09426895ff0ed2362f865429))  by @dependabot[bot]


  ---
  updated-dependencies:
  - dependency-name: "@emotion/styled"
    dependency-version: 11.14.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...






## 4.1.0-saas.10 - 2025-07-09


### Bug fixes


- *(deviceauth)* Fix the pagination logic in devices search endpoint
([MEN-8521](https://northerntech.atlassian.net/browse/MEN-8521)) ([5431bc1](https://github.com/mendersoftware/mender-server-enterprise/commit/5431bc1f6b91379021c633cc2c7d3e29ad31c1d9))  by @bahaa-ghazal

- *(gui)* Fixed an issue that would not show progress in the final phase of phased deployments
 ([5f3be23](https://github.com/mendersoftware/mender-server-enterprise/commit/5f3be23d2aa35f4503979294d8e165c6ca7a9f60))  by @mzedel

- *(gui)* Fixed an issue that prevented reactivating highlighted tooltips in the UI
 ([4babe2e](https://github.com/mendersoftware/mender-server-enterprise/commit/4babe2e0a390dd4e7482692c1217342b2c645de2))  by @mzedel

- *(gui)* Improved likelyhood of getting all device report related data from backend
 ([f429a5d](https://github.com/mendersoftware/mender-server-enterprise/commit/f429a5ddf0166ffe563ace806a33084003a65746))  by @mzedel

- *(gui)* Fixed an issue that could limit release selection during deployment creation
([MEN-8421](https://northerntech.atlassian.net/browse/MEN-8421)) ([a7e5352](https://github.com/mendersoftware/mender-server-enterprise/commit/a7e5352aa2b2491bb61d15142bebab172d906905))  by @mzedel

- *(gui)* Made RBAC roles visible again for non-enterprise users
 ([43f829b](https://github.com/mendersoftware/mender-server-enterprise/commit/43f829b6ec0e44bef0ed1de1a1b83e4e56077afd)) 

- *(gui)* Restored role removal prevention for built-in roles
 ([89a1c43](https://github.com/mendersoftware/mender-server-enterprise/commit/89a1c431af488c7c07577ff5ea4f06b96ef2362d)) 

- *(gui)* Aligned Roles & Users drawer closing behaviour
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([346fd97](https://github.com/mendersoftware/mender-server-enterprise/commit/346fd976cfd026e4b8c85cdf7765f4593a94598b)) 

- *(gui)* Fixed closing animation for deployment drawer
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([a9bca65](https://github.com/mendersoftware/mender-server-enterprise/commit/a9bca657c31002b053297d0c371a191f1369f4e3)) 

- *(gui)* Restored error handling on user edits
([ME-522](https://northerntech.atlassian.net/browse/ME-522)) ([882a5c7](https://github.com/mendersoftware/mender-server-enterprise/commit/882a5c7f6bc03325a4fd5875d2b92d22fe6d7e29)) 


  - regression from 5888d3e3ee47b764b256e89da9419f903936e4f3 in the prior repo

- *(inventory)* Broken links for legacy endpoints for listing devices
([MEN-8517](https://northerntech.atlassian.net/browse/MEN-8517)) ([9cf39b3](https://github.com/mendersoftware/mender-server-enterprise/commit/9cf39b34f5ec6fb313a1b0e3c9afe30b5abce73e))  by @alfrunes


  When using the /api/managment/v1/inventory/devices to list devices, the
  path prefix is rewritten to /api/0.1.0/devices. This commit fixes the
  regression.

- *(tenantadm)* Return application/json in case of no route/method
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([1e4a923](https://github.com/mendersoftware/mender-server-enterprise/commit/1e4a923ead44470b198df26bfcc5d1dfaa50b965))  by @alfrunes


  This is a regression from the migration to gin HTTP framework which
  returns text/plain by default.

- *(useradm)* Use contenttype middleware for login endpoint
 ([1f5bc7d](https://github.com/mendersoftware/mender-server-enterprise/commit/1f5bc7d624d7bd57b9ee9a7d6fbecdfb88650bd7))  by @bahaa-ghazal

- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com/mendersoftware/mender-server-enterprise/commit/d80c818eed43765387cfe81445e187f9c1833156)) 


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(tenantadm)* Add API documentation for preview invoice API
 ([1d14dc9](https://github.com/mendersoftware/mender-server-enterprise/commit/1d14dc93fe6db09baa6d187ca7d70d924a53fc5c))  by @alfrunes

- *(useradm)* Add security section to two-factor APIs
 ([cc0736a](https://github.com/mendersoftware/mender-server-enterprise/commit/cc0736a9d3ad90bf8954277a65f371770515d22f))  by @alfrunes


  The endpoints require authentication.





### Features


- *(gui)* Staggered device report retrieval to further minimize hitting rate limits
 ([02f85ff](https://github.com/mendersoftware/mender-server-enterprise/commit/02f85ff88f4baf77d445a8c1ae6194d748e1a028))  by @mzedel

- *(gui)* Let UI aggregate all device software again - not just rootfs info
 ([cfa3712](https://github.com/mendersoftware/mender-server-enterprise/commit/cfa3712ecfd833c0c31151e114b4dd2456665666))  by @mzedel


  - due to the continued absence of the reporting backend this is re-introduced, but now in combination with the report scoped device retrieval

- *(tenantadm)* Stripe webhooks handle payed subscription invoices
 ([aa1dece](https://github.com/mendersoftware/mender-server-enterprise/commit/aa1dece3b93dc4e074a385b162d6276ed3a10788))  by @alfrunes

- *(tenantadm)* Add option to disable downgrades when submitting subscription changes
([MEN-8347](https://northerntech.atlassian.net/browse/MEN-8347)) ([35edaca](https://github.com/mendersoftware/mender-server-enterprise/commit/35edaca5fbf33820580b7a14e343dc2722665463))  by @kjaskiewiczz

- *(tenantadm)* Create invoice preview
([MEN-8349](https://northerntech.atlassian.net/browse/MEN-8349)) ([cb3bea8](https://github.com/mendersoftware/mender-server-enterprise/commit/cb3bea882d2c55c45ac80313546398419477c3e9))  by @merlin-northern

- *(tenantadm)* Get stripe subscription
([MEN-8148](https://northerntech.atlassian.net/browse/MEN-8148)) ([7b7d04f](https://github.com/mendersoftware/mender-server-enterprise/commit/7b7d04fdbf047199aafe2afaf0104496d88e8767))  by @merlin-northern

- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com/mendersoftware/mender-server-enterprise/commit/9016554b702297ad00f1a748d0824fdf19d05678)) 




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com/mendersoftware/mender-server-enterprise/commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb)) 


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(deployments)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([e8c3289](https://github.com/mendersoftware/mender-server-enterprise/commit/e8c32890c9905f6f5099d9faadc1b2168af9ff99))  by @bahaa-ghazal

- *(deployments)* Migrate deployments enterprise from ant0nie/go-json-rest to gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([3ff31a8](https://github.com/mendersoftware/mender-server-enterprise/commit/3ff31a8ef060e381bddd7d696fbdc3e086fd15c1))  by @bahaa-ghazal

- *(gui)* Let chart adding + editing rely on rhf
 ([1f5f43f](https://github.com/mendersoftware/mender-server-enterprise/commit/1f5f43f83c97808fd08ac29388947d88ecda255c))  by @mzedel

- *(gui)* Let report data retrieval + generation work per single report
 ([049437f](https://github.com/mendersoftware/mender-server-enterprise/commit/049437f4410cc51a5a4f76bc90b5b8ed2fc53385))  by @mzedel

- *(gui)* Let each device report handle data retrieval separately
([ME-542](https://northerntech.atlassian.net/browse/ME-542)) ([23e16b2](https://github.com/mendersoftware/mender-server-enterprise/commit/23e16b2dc95ce3fd4f5b94ed97198c2d9b0a8e5a))  by @mzedel


  + limit report retrieval + visibility to reasonably safe request counts
  - this might reduce availability of dashboard widgets for more users, but until backend support arrives we'll remain limited
  - in order to handle the reduced availability & measure interest a support note was added
  
  - to account for the improbability of return of the reporting service the reliance on this was removed too

- *(gui)* Aligned delta artifact generation settings w/ updated design
 ([b3e0587](https://github.com/mendersoftware/mender-server-enterprise/commit/b3e0587833dade80d103d6db166bcd5cb58683ae))  by @mzedel


  + moved form to RHF to ease working w/ the changed UX

- *(tenantadm)* Increase type safety and consolidate Stripe iterators
 ([99063d4](https://github.com/mendersoftware/mender-server-enterprise/commit/99063d49928a456da9d8e52c7ea789df155cb0a4))  by @alfrunes


  Removed the redundant listIter type as it is covered by the firstBatch
  of the stripeIter type. Also added a comment to provide clarity of the
  generic return argument from stripeIter.Next.

- *(useradm)* Remove the redundant authz middleware
 ([49c629d](https://github.com/mendersoftware/mender-server-enterprise/commit/49c629d0a8bd50314c0c462211e1ea1d29c5dc8d))  by @bahaa-ghazal

- *(useradm)* Make the http pkg structure more consistent
 ([f645fe7](https://github.com/mendersoftware/mender-server-enterprise/commit/f645fe7ce6216cc42a5b11145ff183263c175979))  by @bahaa-ghazal


  Move the endpoints to `router.go` and rename `middleware.go` to `utils.go`

- *(useradm)* Migrate useradm enterprise from ant0nie/go-json-rest to gin
([MEN-8237](https://northerntech.atlassian.net/browse/MEN-8237)) ([f313b66](https://github.com/mendersoftware/mender-server-enterprise/commit/f313b662a022550e85d65dd95579a46280d833fe))  by @bahaa-ghazal

- *(useradm)* Move enterprise endpoints uris to `routing.go`
 ([16fcd7b](https://github.com/mendersoftware/mender-server-enterprise/commit/16fcd7be25adae3e27a7270953926117965280c1))  by @bahaa-ghazal

- Remove unused ant0ine/go-json-rest utilities from deployments
 ([42f090b](https://github.com/mendersoftware/mender-server-enterprise/commit/42f090ba9a5f7fd2a0529688943d3d76646a1cab))  by @bahaa-ghazal
- Swap ant0ine/go-json-rest with gin-gonic/gin in routing pkg
 ([b53abcd](https://github.com/mendersoftware/mender-server-enterprise/commit/b53abcd60631dcbf9a7895af8de2bcdfcc007460))  by @bahaa-ghazal




### Security


- Bump urllib3 from 2.4.0 to 2.5.0 in /backend/tests
 ([f7fcb02](https://github.com/mendersoftware/mender-server-enterprise/commit/f7fcb0283b29b4bb1d56c52e247581d0d486dc67))  by @dependabot[bot]


  Bumps [urllib3](https://github.com/urllib3/urllib3) from 2.4.0 to 2.5.0.
  - [Release notes](https://github.com/urllib3/urllib3/releases)
  - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
  - [Commits](https://github.com/urllib3/urllib3/compare/2.4.0...2.5.0)
  
  ---
  updated-dependencies:
  - dependency-name: urllib3
    dependency-version: 2.5.0
    dependency-type: direct:production
  ...
- Bump github.com/go-viper/mapstructure/v2 in /backend
 ([777d367](https://github.com/mendersoftware/mender-server-enterprise/commit/777d3673eb1bb9b9a3d82aa48cbf8091417f8bb4))  by @dependabot[bot]


  Bumps [github.com/go-viper/mapstructure/v2](https://github.com/go-viper/mapstructure) from 2.2.1 to 2.3.0.
  - [Release notes](https://github.com/go-viper/mapstructure/releases)
  - [Changelog](https://github.com/go-viper/mapstructure/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/go-viper/mapstructure/compare/v2.2.1...v2.3.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/go-viper/mapstructure/v2
    dependency-version: 2.3.0
    dependency-type: indirect
  ...
- Bump pillow from 11.2.1 to 11.3.0 in /backend/tests
 ([8aef575](https://github.com/mendersoftware/mender-server-enterprise/commit/8aef575eb2aa55e2ea26cbc5595181166281a639))  by @dependabot[bot]


  Bumps [pillow](https://github.com/python-pillow/Pillow) from 11.2.1 to 11.3.0.
  - [Release notes](https://github.com/python-pillow/Pillow/releases)
  - [Changelog](https://github.com/python-pillow/Pillow/blob/main/CHANGES.rst)
  - [Commits](https://github.com/python-pillow/Pillow/compare/11.2.1...11.3.0)
  
  ---
  updated-dependencies:
  - dependency-name: pillow
    dependency-version: 11.3.0
    dependency-type: direct:production
  ...
- Bump the backend-tests-python-dependencies group across 2 directories with 10 updates
 ([85a6aeb](https://github.com/mendersoftware/mender-server-enterprise/commit/85a6aebda942e11894a5b1908cf12969d2fcd600))  by @dependabot[bot]


  ---
  updated-dependencies:
  - dependency-name: opensearch-py
    dependency-version: 3.0.0
    dependency-type: direct:production
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest
    dependency-version: 8.4.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.13.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.6.15
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: opensearch-py
    dependency-version: 3.0.0
    dependency-type: direct:production
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.39.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: kubernetes
    dependency-version: 33.1.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pillow
    dependency-version: 11.3.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest-xdist
    dependency-version: 3.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pydantic
    dependency-version: 2.11.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([48e8641](https://github.com/mendersoftware/mender-server-enterprise/commit/48e8641a860e9fbe2c021a34fa54c743a7189f11))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.36.4` | `1.36.5` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.29.16` | `1.29.17` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.17.69` | `1.17.70` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.64.3` | `1.64.4` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.27.3` | `1.27.4` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.80.2` | `1.82.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.4` | `2.11.6` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.10.0` | `9.11.0` |
  | [github.com/urfave/cli](https://github.com/urfave/cli) | `1.22.16` | `1.22.17` |
  
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.36.4 to 1.36.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.36.4...v1.36.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.29.16 to 1.29.17
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.29.16...config/v1.29.17)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.17.69 to 1.17.70
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/credentials/v1.17.69...credentials/v1.17.70)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.64.3 to 1.64.4
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.64.3...service/iot/v1.64.4)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.27.3 to 1.27.4
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.27.3...config/v1.27.4)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.80.2 to 1.82.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.80.2...service/s3/v1.82.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.4 to 2.11.6
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.4...v2.11.6)
  
  Updates `github.com/redis/go-redis/v9` from 9.10.0 to 9.11.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.10.0...v9.11.0)
  
  Updates `github.com/urfave/cli` from 1.22.16 to 1.22.17
  - [Release notes](https://github.com/urfave/cli/releases)
  - [Changelog](https://github.com/urfave/cli/blob/main/docs/CHANGELOG.md)
  - [Commits](https://github.com/urfave/cli/compare/v1.22.16...v1.22.17)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.36.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.29.17
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.17.70
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.64.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.27.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.82.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/urfave/cli
    dependency-version: 1.22.17
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  ...





### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com/mendersoftware/mender-server-enterprise/commit/5ba3fd7deda6421612029b31317cc61c2b1ef373)) 
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com/mendersoftware/mender-server-enterprise/commit/5c2e23a6ff9b073b38cad1ef56e8845264369817)) 




### Revert


- "test: Unit tests for configuring rate limits"
 ([4ef01b1](https://github.com/mendersoftware/mender-server-enterprise/commit/4ef01b1a66d5f20e10d587fbdfc9d3febe14ee8e))  by @alfrunes


  This reverts commit 16caca6ae355f2dfa843c019f31f0722456b1c96.
- "test: Unit tests for rate limit parameters and applying rate limits"
 ([4102778](https://github.com/mendersoftware/mender-server-enterprise/commit/4102778ea46ac4bda13db499177cb491362b6000))  by @alfrunes


  This reverts commit 4bf8462399128586238c734fdd14c90ad7ce0479.
- "feat(deviceauth): Rate limit device requests"
 ([9c158a3](https://github.com/mendersoftware/mender-server-enterprise/commit/9c158a3377fe6b9ac9f98f2b7cb15936237b6de1))  by @alfrunes


  This reverts commit 9c3041f5d54ea06c920ae0cc977c8af594133fb2.
- "feat(deviceauth): Rate limit authenticated devices API"
 ([aa7eff8](https://github.com/mendersoftware/mender-server-enterprise/commit/aa7eff8de394de13f53008e2aaa5273bf7939a5c))  by @alfrunes


  This reverts commit 8c8028081a54a62ba8673071350414b096aa87b0.
- "test: Fix deviceauth.cache tests after changing client initialization"
 ([9d21a83](https://github.com/mendersoftware/mender-server-enterprise/commit/9d21a83e05444189a51e197d4d5945d148e2a7f6))  by @alfrunes


  This reverts commit 721a2f760a38a9c25c38e5aa95fbd9f6f180ea7f.
- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com/mendersoftware/mender-server-enterprise/commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548)) 


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.






## 4.1.0-saas.9 - 2025-06-18


### Bug fixes


- *(gui)* Fixed another situation that could cause the organization token to overflow
 ([555cb1e](https://github.com/mendersoftware/mender-server-enterprise/commit/555cb1e7ec1571bd5ed02104c1185138b6e25d4a))  by @mzedel







## 4.1.0-saas.8 - 2025-06-18


### Bug fixes


- *(gui)* Fixed a problem that could apply RBAC restrictions on non-RBAC plans
([MEN-8498](https://northerntech.atlassian.net/browse/MEN-8498)) ([c870092](https://github.com/mendersoftware/mender-server-enterprise/commit/c87009221163505732cb677e44a9c159233c3d68))  by @mzedel

- *(gui)* Fixed an issue that could cause the organization token to overflow for older tenants
 ([e04f0e9](https://github.com/mendersoftware/mender-server-enterprise/commit/e04f0e99df3c4edcd932034bc3d0aad31bd8467f))  by @mzedel







## 4.1.0-saas.7 - 2025-06-18


### Bug fixes


- *(generate-delta-worker)* Stuck when generating to local path
([MEN-8484](https://northerntech.atlassian.net/browse/MEN-8484)) ([a7e27ca](https://github.com/mendersoftware/mender-server-enterprise/commit/a7e27cad64ebb403766ca8bdfa05389c17affd87))  by @alfrunes


  Only used in tests. The generate-delta command fails when the output is
  a local path.

- *(gui)* Restored error handling on user edits
([ME-522](https://northerntech.atlassian.net/browse/ME-522)) ([882a5c7](https://github.com/mendersoftware/mender-server-enterprise/commit/882a5c7f6bc03325a4fd5875d2b92d22fe6d7e29)) 


  - regression from 5888d3e3ee47b764b256e89da9419f903936e4f3 in the prior repo

- *(gui)* Fixed an issue that would prevent showing all webhook activity
 ([70d9eda](https://github.com/mendersoftware/mender-server-enterprise/commit/70d9eda75dd1cf955daa892bcc86a9760743be5f)) 

- *(gui)* Fixed wording and position of onboarding tooltip
([MEN-8407](https://northerntech.atlassian.net/browse/MEN-8407)) ([69c1a6d](https://github.com/mendersoftware/mender-server-enterprise/commit/69c1a6ddd185ed1277fdbb66b194d6f09c4b06a0))  by @mineralsfree

- *(gui)* Aligned supported OS versions in download section with tool support
([ME-499](https://northerntech.atlassian.net/browse/ME-499)) ([c256688](https://github.com/mendersoftware/mender-server-enterprise/commit/c256688950a0f81fdb63326f6fb524e035969ab3))  by @mzedel

- *(gui)* Fixed billing profile not being fetched
 ([9042c6b](https://github.com/mendersoftware/mender-server-enterprise/commit/9042c6be7ccc445a5affca63b65559bb562e6597))  by @mineralsfree

- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com/mendersoftware/mender-server-enterprise/commit/d80c818eed43765387cfe81445e187f9c1833156)) 


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(auditlogs)* Replace swagger 2.0 specs with Openapi 3.0.1
 ([d624916](https://github.com/mendersoftware/mender-server-enterprise/commit/d6249166af2c6b2aa6dcaf29780bc6a47519ba8d))  by @alfrunes

- *(auditlogs)* Consolidate API specifications into a single OAS file
 ([e47649f](https://github.com/mendersoftware/mender-server-enterprise/commit/e47649f1d9309dd1fbca5bce72b5757548e8b103))  by @alfrunes

- *(auditlogs)* Move OAS to new location and provide symlink
 ([7e55fc3](https://github.com/mendersoftware/mender-server-enterprise/commit/7e55fc3b196fb340080cacc202f1a730aa560632))  by @alfrunes

- *(auditlogs)* Add content type to export endpoint
 ([3f681c7](https://github.com/mendersoftware/mender-server-enterprise/commit/3f681c73959cfce5f8aed81adc10d419ac1eabab))  by @alfrunes

- *(deviceauth)* Rename operation id for removing device authentication
 ([3f99b91](https://github.com/mendersoftware/mender-server-enterprise/commit/3f99b91c57c52214e01a70caa78ed47912956c9f))  by @alfrunes


  "Reject" is in the UI associated with updating the authentication status
  where as "dismiss" is used for removing authentication.

- *(tenantadm)* Convert API docs to OpenAPI specification 3.0
 ([9bf0f58](https://github.com/mendersoftware/mender-server-enterprise/commit/9bf0f588f9312470cfde059ec7b4b056a16c519f))  by @alfrunes

- *(tenantadm)* Consolidate OAS into a single definition
 ([bd79510](https://github.com/mendersoftware/mender-server-enterprise/commit/bd7951099cfbd7f59ae6a6e9d41a74d560a4e910))  by @alfrunes

- *(tenantadm)* Fixup Tenant examples in OAS specs
 ([cf8ac9b](https://github.com/mendersoftware/mender-server-enterprise/commit/cf8ac9b3f21f94fc77f2a58d0391c0b0094c4829))  by @alfrunes

- *(tenantadm)* Fix incorrect type for integer in OAS
 ([2b4c082](https://github.com/mendersoftware/mender-server-enterprise/commit/2b4c0820b88f31dae88d54cd4a1254f6e43bba9a))  by @alfrunes

- *(tenantadm)* Update OAS info section
 ([1e60f1e](https://github.com/mendersoftware/mender-server-enterprise/commit/1e60f1ecef093efb67e9dec1149fa57afda42e96))  by @alfrunes

- *(tenantadm)* Fix invalid objects in `allOf` overrides for Address
 ([eb48e23](https://github.com/mendersoftware/mender-server-enterprise/commit/eb48e2348e1ab3abb73ca3de285a622a772cba5c))  by @alfrunes

- *(tenantadm)* Fix inconsistent schema definitions
 ([fd48cc5](https://github.com/mendersoftware/mender-server-enterprise/commit/fd48cc5e89925e26935ec3c6f594e1d80957e5be))  by @alfrunes





### Features


- *(gui)* Made device tags functionality available in all device auth states
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([7b1f3c6](https://github.com/mendersoftware/mender-server-enterprise/commit/7b1f3c61e4b4151cb81a8aab5c4a22c581e01cb3)) 

- *(gui)* Let tenant token not be visible by default
([MEN-8397](https://northerntech.atlassian.net/browse/MEN-8397)) ([b70e0b4](https://github.com/mendersoftware/mender-server-enterprise/commit/b70e0b44cf627d6b0621da92f0d0a154588aafb1)) 

- *(useradm)* Change user roles handling for plans different than Enterprise
([MEN-8168](https://northerntech.atlassian.net/browse/MEN-8168)) ([1ee0b84](https://github.com/mendersoftware/mender-server-enterprise/commit/1ee0b84a6be11bf2dd2ce28785b64031f1c2f52d))  by @kjaskiewiczz

- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com/mendersoftware/mender-server-enterprise/commit/9016554b702297ad00f1a748d0824fdf19d05678)) 




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com/mendersoftware/mender-server-enterprise/commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb)) 


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(deviceauth)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8235](https://northerntech.atlassian.net/browse/MEN-8235)) ([70e7da8](https://github.com/mendersoftware/mender-server-enterprise/commit/70e7da8bce4e8b06a9e2d65868b46739a2575d59))  by @bahaa-ghazal

- *(deviceauth)* Move api urls and router maker to `routing.go`
([MEN-8235](https://northerntech.atlassian.net/browse/MEN-8235)) ([7ecd14e](https://github.com/mendersoftware/mender-server-enterprise/commit/7ecd14e37aca2d0a8c61b6382e5593a9038b8921))  by @bahaa-ghazal

- *(deviceauth)* Migrate enterprise deviceauth service to gin
([MEN-8235](https://northerntech.atlassian.net/browse/MEN-8235)) ([f0b43c4](https://github.com/mendersoftware/mender-server-enterprise/commit/f0b43c47b1c6cab50ff7bfea401f50bc16719d94))  by @bahaa-ghazal

- *(gui)* Isolated organization information in settings to align with design
([MEN-8411](https://northerntech.atlassian.net/browse/MEN-8411)) ([2d0eb79](https://github.com/mendersoftware/mender-server-enterprise/commit/2d0eb79e1c51eb31c7a9c1df83754f0aee663a70))  by @mzedel


  + made settings items customizable from outside

- *(gui)* Moved billing data to separate settings section & aligned with design
([MEN-8411](https://northerntech.atlassian.net/browse/MEN-8411)) ([bf7578b](https://github.com/mendersoftware/mender-server-enterprise/commit/bf7578b3966c82d293127d4d9a0cf6d98d90008e))  by @mzedel

- *(gui)* Centralized support contact component
 ([0dd79cb](https://github.com/mendersoftware/mender-server-enterprise/commit/0dd79cb8d2cdd8bc96d4f5c47ef0f7d3f58175a4))  by @mzedel

- *(inventory)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([f6899d4](https://github.com/mendersoftware/mender-server-enterprise/commit/f6899d44129b892708bbe0bfcc485fbf8f705166)) 

- *(tenantadm)* Move `middleware.go` to the http package
 ([3f5f338](https://github.com/mendersoftware/mender-server-enterprise/commit/3f5f338d1415a4f11c346d6c157753545c3fbf74))  by @bahaa-ghazal

- *(tenantadm)* Move api handler and router to their corresponding file
 ([24e22ae](https://github.com/mendersoftware/mender-server-enterprise/commit/24e22ae3d0129a6b423e9940bd8bc441dd6e1be4))  by @bahaa-ghazal

- *(tenantadm)* Expect status 404 instead of 405 when sign-up is disabled
 ([0a48ab1](https://github.com/mendersoftware/mender-server-enterprise/commit/0a48ab1729d20fd1876fa44920c98749e6923f3a))  by @bahaa-ghazal


  Update the docs and the acceptence tests to expect 404 instead of 405

- Put MakeTestRequest in dedicated testing package
 ([7597129](https://github.com/mendersoftware/mender-server-enterprise/commit/7597129bd6336a8542ec9357dbf4d105de371269)) 


  Utilities for testing should be separate from application code.
- Remove ant0ine/go-json-rest dependency from `requestid.GetReqId()`
 ([863e415](https://github.com/mendersoftware/mender-server-enterprise/commit/863e41536cd65293b79f65dd127a7100c9d0f569))  by @bahaa-ghazal
- Migrate enterprise inventory service to gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([77b1268](https://github.com/mendersoftware/mender-server-enterprise/commit/77b126808baeeea03fc67f77a9b6c99131fce943)) 


  Migrate the enterprise-only components from ant0nie/go-json-rest to gin-gonic/gin




### Security


- Bump vite from 6.2.6 to 6.3.4 in /frontend
 ([03506da](https://github.com/mendersoftware/mender-server-enterprise/commit/03506da1dfa189da0a062f03c178e0d67fc69d0d)) 


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 6.2.6 to 6.3.4.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v6.3.4/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 6.3.4
    dependency-type: indirect
  ...
- Bump the development-dependencies group across 1 directory with 12 updates
 ([30cc04b](https://github.com/mendersoftware/mender-server-enterprise/commit/30cc04b5c9794066440094afdec1ef2a47edf461)) 


  Bumps the development-dependencies group with 10 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.4.0` | `0.5.0` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.3.8` | `1.3.13` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.3.8` | `1.3.13` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `3.3.1` | `3.5.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `22.15.3` | `22.15.29` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `4.4.1` | `4.5.0` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `3.1.2` | `3.1.4` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `15.5.1` | `16.1.0` |
  | [msw](https://github.com/mswjs/msw) | `2.7.5` | `2.8.7` |
  | [undici](https://github.com/nodejs/undici) | `7.8.0` | `7.10.0` |
  
  
  
  Updates `@northern.tech/eslint-config` from 0.4.0 to 0.5.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.4.0...@northern.tech/eslint-config-0.5.0)
  
  Updates `@rspack/cli` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack)
  
  Updates `@sentry/webpack-plugin` from 3.3.1 to 3.5.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/3.3.1...3.5.0)
  
  Updates `@types/node` from 22.15.3 to 22.15.29
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.32.1 to 8.33.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.33.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 4.4.1 to 4.5.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@4.5.0/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/coverage-v8)
  
  Updates `lint-staged` from 15.5.1 to 16.1.0
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v15.5.1...v16.1.0)
  
  Updates `msw` from 2.7.5 to 2.8.7
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.7.5...v2.8.7)
  
  Updates `undici` from 7.8.0 to 7.10.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.8.0...v7.10.0)
  
  Updates `vitest` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 3.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 22.15.29
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.33.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.8.7
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group across 1 directory with 3 updates
 ([96d55d3](https://github.com/mendersoftware/mender-server-enterprise/commit/96d55d3f34b37fa17ef593d310c1e6e9a0a80a2d)) 


  Bumps the mui group with 3 updates in the /frontend directory: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.2.0 to 8.5.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the backend-golang-dependencies group
 ([a834409](https://github.com/mendersoftware/mender-server-enterprise/commit/a834409d316b166dba470fdd36cf8ce13f28d59a))  by @dependabot[bot]


  Bumps the backend-golang-dependencies group in /backend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.79.3` | `1.80.0` |
  | [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) | `1.10.0` | `1.10.1` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.3` | `2.11.4` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.41.2` | `1.42.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.8.0` | `9.9.0` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.37.0` | `0.38.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.39.0` | `0.40.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.32.0` | `0.33.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.31.0` | `0.32.0` |
  
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.79.3 to 1.80.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.79.3...service/s3/v1.80.0)
  
  Updates `github.com/gin-gonic/gin` from 1.10.0 to 1.10.1
  - [Release notes](https://github.com/gin-gonic/gin/releases)
  - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/gin-gonic/gin/compare/v1.10.0...v1.10.1)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.3 to 2.11.4
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.3...v2.11.4)
  
  Updates `github.com/nats-io/nats.go` from 1.41.2 to 1.42.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.41.2...v1.42.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.8.0 to 9.9.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.8.0...v9.9.0)
  
  Updates `golang.org/x/crypto` from 0.37.0 to 0.38.0
  - [Commits](https://github.com/golang/crypto/compare/v0.37.0...v0.38.0)
  
  Updates `golang.org/x/net` from 0.39.0 to 0.40.0
  - [Commits](https://github.com/golang/net/compare/v0.39.0...v0.40.0)
  
  Updates `golang.org/x/sys` from 0.32.0 to 0.33.0
  - [Commits](https://github.com/golang/sys/compare/v0.32.0...v0.33.0)
  
  Updates `golang.org/x/term` from 0.31.0 to 0.32.0
  - [Commits](https://github.com/golang/term/compare/v0.31.0...v0.32.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.80.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/gin-gonic/gin
    dependency-version: 1.10.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.9.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.38.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.33.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.32.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 5 updates
 ([bfc4838](https://github.com/mendersoftware/mender-server-enterprise/commit/bfc4838fefe59382cb747f5745f8b59f23bc4a71))  by @dependabot[bot]


  Bumps the backend-tests-python-dependencies group with 5 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [boto3](https://github.com/boto/boto3) | `1.38.6` | `1.38.27` |
  | [cryptography](https://github.com/pyca/cryptography) | `44.0.2` | `45.0.3` |
  | [pluggy](https://github.com/pytest-dev/pluggy) | `1.5.0` | `1.6.0` |
  | [redis](https://github.com/redis/redis-py) | `5.2.1` | `6.2.0` |
  | [pytest-xdist](https://github.com/pytest-dev/pytest-xdist) | `3.6.1` | `3.7.0` |
  
  
  
  Updates `boto3` from 1.38.6 to 1.38.27
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.38.6...1.38.27)
  
  Updates `cryptography` from 44.0.2 to 45.0.3
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/44.0.2...45.0.3)
  
  Updates `pluggy` from 1.5.0 to 1.6.0
  - [Changelog](https://github.com/pytest-dev/pluggy/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pluggy/compare/1.5.0...1.6.0)
  
  Updates `redis` from 5.2.1 to 6.2.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v5.2.1...v6.2.0)
  
  Updates `pytest-xdist` from 3.6.1 to 3.7.0
  - [Release notes](https://github.com/pytest-dev/pytest-xdist/releases)
  - [Changelog](https://github.com/pytest-dev/pytest-xdist/blob/master/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest-xdist/compare/v3.6.1...v3.7.0)
  
  ---
  updated-dependencies:
  - dependency-name: boto3
    dependency-version: 1.38.27
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.3
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pluggy
    dependency-version: 1.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 6.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest-xdist
    dependency-version: 3.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump webpack-dev-server and @rspack/cli in /frontend
 ([ff4bc85](https://github.com/mendersoftware/mender-server-enterprise/commit/ff4bc85de991a11e258ba0a1e4a6e1fbd81592f5))  by @dependabot[bot]


  Bumps [webpack-dev-server](https://github.com/webpack/webpack-dev-server) to 5.2.2 and updates ancestor dependency [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli). These dependencies need to be updated together.
  
  
  Updates `webpack-dev-server` from 5.2.0 to 5.2.2
  - [Release notes](https://github.com/webpack/webpack-dev-server/releases)
  - [Changelog](https://github.com/webpack/webpack-dev-server/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/webpack/webpack-dev-server/compare/v5.2.0...v5.2.2)
  
  Updates `@rspack/cli` from 1.3.13 to 1.3.15
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.15/packages/rspack-cli)
  
  ---
  updated-dependencies:
  - dependency-name: webpack-dev-server
    dependency-version: 5.2.2
    dependency-type: indirect
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.15
    dependency-type: direct:development
  ...
- Bump requests in /backend/services/iot-manager/tests
 ([695983a](https://github.com/mendersoftware/mender-server-enterprise/commit/695983abeeaf65400923ec435f2738d7475d7cf5))  by @dependabot[bot]


  Bumps [requests](https://github.com/psf/requests) from 2.32.3 to 2.32.4.
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.3...v2.32.4)
  
  ---
  updated-dependencies:
  - dependency-name: requests
    dependency-version: 2.32.4
    dependency-type: direct:production
  ...
- Bump the backend-docker-dependencies group across 10 directories with 1 update
 ([f39b7fb](https://github.com/mendersoftware/mender-server-enterprise/commit/f39b7fb012b5b92cd74e8042f4fedd12e95ed394))  by @dependabot[bot]


  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/create-artifact-worker directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump @mui/x-date-pickers in /frontend in the mui group
 ([0b07854](https://github.com/mendersoftware/mender-server-enterprise/commit/0b07854d18232ca6bc0f31235ee04db9055c7081))  by @dependabot[bot]


  Bumps the mui group in /frontend with 1 update: [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/x-date-pickers` from 8.5.0 to 8.5.1
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.1/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([ef7e609](https://github.com/mendersoftware/mender-server-enterprise/commit/ef7e609525b582ae01d05d33d36f7aa456e09c09))  by @dependabot[bot]


  Bumps the production-dependencies group in /frontend with 3 updates: [@sentry/react](https://github.com/getsentry/sentry-javascript), [react-hook-form](https://github.com/react-hook-form/react-hook-form) and [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom).
  
  
  Updates `@sentry/react` from 9.24.0 to 9.28.1
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/9.24.0...9.28.1)
  
  Updates `react-hook-form` from 7.56.4 to 7.57.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.56.4...v7.57.0)
  
  Updates `react-router-dom` from 7.6.1 to 7.6.2
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/7.6.2/packages/react-router-dom)
  
  ---
  updated-dependencies:
  - dependency-name: "@sentry/react"
    dependency-version: 9.28.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.57.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump @playwright/test
 ([be22a5f](https://github.com/mendersoftware/mender-server-enterprise/commit/be22a5fd353920f7c195bc1866e7dba38564f116))  by @dependabot[bot]


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.52.0 to 1.53.0
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.52.0...v1.53.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.53.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...




### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com/mendersoftware/mender-server-enterprise/commit/5ba3fd7deda6421612029b31317cc61c2b1ef373)) 
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com/mendersoftware/mender-server-enterprise/commit/5c2e23a6ff9b073b38cad1ef56e8845264369817)) 




### Revert


- *(tenantadm)* Restore swagger specifications for generating types
 ([c06ad4e](https://github.com/mendersoftware/mender-server-enterprise/commit/c06ad4e61f39c5c982596db72036cd3e1b7e1d0c))  by @alfrunes


  ... and remove symlink to new specifications.

- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com/mendersoftware/mender-server-enterprise/commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548)) 


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.
- "ci: Debug mongodb in backend unit tests"
 ([441c1ea](https://github.com/mendersoftware/mender-server-enterprise/commit/441c1eaa43cc79737468aef3068784f0bfadef28)) 


  Enabling logging just overflows the log buffer.
  
  This reverts commit 6d164c4c70d1fff7d28e88a50390f8afb676c814.






## 4.1.0-saas.6 - 2025-06-05


### Bug fixes


- *(gui)* Changed cancel button in device configuration edit to close the form
([MEN-8344](https://northerntech.atlassian.net/browse/MEN-8344)) ([f1f542a](https://github.com/mendersoftware/mender-server-enterprise/commit/f1f542a4322de05692da5a94d85a61d1c840488e))  by @mineralsfree

- *(gui)* Made RBAC roles visible again for non-enterprise users
 ([43f829b](https://github.com/mendersoftware/mender-server-enterprise/commit/43f829b6ec0e44bef0ed1de1a1b83e4e56077afd))  by @mzedel

- *(gui)* Restored role removal prevention for built-in roles
 ([89a1c43](https://github.com/mendersoftware/mender-server-enterprise/commit/89a1c431af488c7c07577ff5ea4f06b96ef2362d))  by @mzedel

- *(gui)* Aligned Roles & Users drawer closing behaviour
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([346fd97](https://github.com/mendersoftware/mender-server-enterprise/commit/346fd976cfd026e4b8c85cdf7765f4593a94598b))  by @mineralsfree

- *(gui)* Fixed closing animation for deployment drawer
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([a9bca65](https://github.com/mendersoftware/mender-server-enterprise/commit/a9bca657c31002b053297d0c371a191f1369f4e3))  by @mineralsfree

- *(gui)* Restored error handling on user edits
([ME-522](https://northerntech.atlassian.net/browse/ME-522)) ([882a5c7](https://github.com/mendersoftware/mender-server-enterprise/commit/882a5c7f6bc03325a4fd5875d2b92d22fe6d7e29))  by @mzedel


  - regression from 5888d3e3ee47b764b256e89da9419f903936e4f3 in the prior repo

- *(gui)* Fixed an issue that would prevent showing all webhook activity
 ([70d9eda](https://github.com/mendersoftware/mender-server-enterprise/commit/70d9eda75dd1cf955daa892bcc86a9760743be5f))  by @mzedel

- *(gui)* Fixed reset button location in device tags & similar editors
 ([00335b2](https://github.com/mendersoftware/mender-server-enterprise/commit/00335b22dff4b324269ceeeac2e664caa061c960))  by @mzedel

- *(gui)* Allowed clearing device tags & device configuration entirely
([ME-529](https://northerntech.atlassian.net/browse/ME-529)) ([896f2a9](https://github.com/mendersoftware/mender-server-enterprise/commit/896f2a967220ecc514b99e8873841ed31f2d2dde))  by @mzedel

- *(gui)* Fixed location of device name tag help to not disturb tag editor
 ([e27417c](https://github.com/mendersoftware/mender-server-enterprise/commit/e27417cbb4298f235bf31044b5934501affcc9af))  by @mzedel


  - this takes the kv related styles from less into the component making theming a bit more consistent and encapsulating the component further

- *(gui)* Prevented device tag editor to be shown when no tags exist
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([3b6b0db](https://github.com/mendersoftware/mender-server-enterprise/commit/3b6b0dbbe39c278bd10d2385c82fd34042d1dbac))  by @mzedel


  - this is to reduce confusion about tags defined async to the current session not being visible

- *(useradm)* RBAC - fix permissions related to inventory filters
([ME-513](https://northerntech.atlassian.net/browse/ME-513)) ([fdb7cd4](https://github.com/mendersoftware/mender-server-enterprise/commit/fdb7cd4de58f7b03860ee6c20f6deae8fc2417ee))  by @kjaskiewiczz


  Users without access to all devices should not be able to get
  inventory filers by Id.





### Documentation


- Fixed parameter in reset password and verify email endpoints
([MEN-8267](https://northerntech.atlassian.net/browse/MEN-8267)) ([649fde5](https://github.com/mendersoftware/mender-server-enterprise/commit/649fde578ac5c6650855db2dd28d6723b297c29b))  by @mineralsfree
- Add API specification for changing subscription
([MEN-8145](https://northerntech.atlassian.net/browse/MEN-8145)) ([ab82128](https://github.com/mendersoftware/mender-server-enterprise/commit/ab821285d360a29fa3b39486662aaebd0eed69b1))  by @alfrunes




### Features


- *(gui)* Made device tags functionality available in all device auth states
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([7b1f3c6](https://github.com/mendersoftware/mender-server-enterprise/commit/7b1f3c61e4b4151cb81a8aab5c4a22c581e01cb3))  by @mzedel

- *(gui)* Let tenant token not be visible by default
([MEN-8397](https://northerntech.atlassian.net/browse/MEN-8397)) ([b70e0b4](https://github.com/mendersoftware/mender-server-enterprise/commit/b70e0b44cf627d6b0621da92f0d0a154588aafb1))  by @mzedel

- *(gui)* Made device tag setting requirement for fully defined keys & values more visible
 ([a3ec69f](https://github.com/mendersoftware/mender-server-enterprise/commit/a3ec69ff8e3fd2940ead0e355a9dc2ac84b9b302))  by @mzedel

- New billing API for managing subscription
([MEN-8145](https://northerntech.atlassian.net/browse/MEN-8145)) ([e9e489d](https://github.com/mendersoftware/mender-server-enterprise/commit/e9e489d21711ed098e279698c6cbe46c690460f4))  by @alfrunes


  The new endpoint
  `POST /api/management/v2/tenantadm/billing/subscription`
  allows the customer to upgrade plan, enable add-ons and change the
  device limit.




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com/mendersoftware/mender-server-enterprise/commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb))  by @alfrunes


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(inventory)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([f6899d4](https://github.com/mendersoftware/mender-server-enterprise/commit/f6899d44129b892708bbe0bfcc485fbf8f705166))  by @bahaa-ghazal

- Put MakeTestRequest in dedicated testing package
 ([7597129](https://github.com/mendersoftware/mender-server-enterprise/commit/7597129bd6336a8542ec9357dbf4d105de371269))  by @alfrunes


  Utilities for testing should be separate from application code.
- Migrate enterprise inventory service to gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([77b1268](https://github.com/mendersoftware/mender-server-enterprise/commit/77b126808baeeea03fc67f77a9b6c99131fce943))  by @bahaa-ghazal


  Migrate the enterprise-only components from ant0nie/go-json-rest to gin-gonic/gin




### Security


- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([7daaeda](https://github.com/mendersoftware/mender-server-enterprise/commit/7daaeda97fdf10652498ed2c3db82d0030486de4))  by @dependabot[bot]


  Bumps the backend-docker-dependencies group with 2 updates in the /backend/services/create-artifact-worker directory: golang and alpine.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `alpine` from 3.21.3 to 3.22.0
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump node in /frontend
 ([906c5f3](https://github.com/mendersoftware/mender-server-enterprise/commit/906c5f3632d55ba59898b4146919ad465c9acc9f))  by @dependabot[bot]


  Bumps node from 23.11.0-alpine3.20 to 24.1.0-alpine3.20.
  
  ---
  updated-dependencies:
  - dependency-name: node
    dependency-version: 24.1.0-alpine3.20
    dependency-type: direct:production
    update-type: version-update:semver-major
  ...
- Bump yaml
 ([64b5ae9](https://github.com/mendersoftware/mender-server-enterprise/commit/64b5ae9b391ec548b940cfe5302bbdf7125b7671))  by @dependabot[bot]


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 1 update: [yaml](https://github.com/eemeli/yaml).
  
  
  Updates `yaml` from 2.7.1 to 2.8.0
  - [Release notes](https://github.com/eemeli/yaml/releases)
  - [Commits](https://github.com/eemeli/yaml/compare/v2.7.1...v2.8.0)
  
  ---
  updated-dependencies:
  - dependency-name: yaml
    dependency-version: 2.8.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump the production-dependencies group
 ([b273830](https://github.com/mendersoftware/mender-server-enterprise/commit/b273830a45f46e45f7b5d4244856ef8f3ee95ef6))  by @dependabot[bot]


  Bumps the production-dependencies group in /frontend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.7.0` | `2.8.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `9.15.0` | `9.24.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.6.0` | `3.7.0` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.2.0` | `7.3.1` |
  | [react-big-calendar](https://github.com/jquense/react-big-calendar) | `1.18.0` | `1.19.2` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.56.1` | `7.56.4` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.5.3` | `7.6.1` |
  | [tss-react](https://github.com/garronej/tss-react) | `4.9.16` | `4.9.18` |
  | [validator](https://github.com/validatorjs/validator.js) | `13.15.0` | `13.15.15` |
  
  
  Updates `@reduxjs/toolkit` from 2.7.0 to 2.8.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.7.0...v2.8.2)
  
  Updates `@sentry/react` from 9.15.0 to 9.24.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/9.15.0...9.24.0)
  
  Updates `@stripe/react-stripe-js` from 3.6.0 to 3.7.0
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.6.0...v3.7.0)
  
  Updates `@stripe/stripe-js` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.2.0...v7.3.1)
  
  Updates `react-big-calendar` from 1.18.0 to 1.19.2
  - [Release notes](https://github.com/jquense/react-big-calendar/releases)
  - [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/jquense/react-big-calendar/compare/v1.18.0...v1.19.2)
  
  Updates `react-hook-form` from 7.56.1 to 7.56.4
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.56.1...v7.56.4)
  
  Updates `react-router-dom` from 7.5.3 to 7.6.1
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.6.1/packages/react-router-dom)
  
  Updates `tss-react` from 4.9.16 to 4.9.18
  - [Release notes](https://github.com/garronej/tss-react/releases)
  - [Commits](https://github.com/garronej/tss-react/compare/v4.9.16...v4.9.18)
  
  Updates `validator` from 13.15.0 to 13.15.15
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.0...13.15.15)
  
  ---
  updated-dependencies:
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.8.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 9.24.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 3.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-big-calendar
    dependency-version: 1.19.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.56.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: tss-react
    dependency-version: 4.9.18
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: validator
    dependency-version: 13.15.15
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump the development-dependencies group across 1 directory with 12 updates
 ([30cc04b](https://github.com/mendersoftware/mender-server-enterprise/commit/30cc04b5c9794066440094afdec1ef2a47edf461))  by @dependabot[bot]


  Bumps the development-dependencies group with 10 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.4.0` | `0.5.0` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.3.8` | `1.3.13` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.3.8` | `1.3.13` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `3.3.1` | `3.5.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `22.15.3` | `22.15.29` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `4.4.1` | `4.5.0` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `3.1.2` | `3.1.4` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `15.5.1` | `16.1.0` |
  | [msw](https://github.com/mswjs/msw) | `2.7.5` | `2.8.7` |
  | [undici](https://github.com/nodejs/undici) | `7.8.0` | `7.10.0` |
  
  
  
  Updates `@northern.tech/eslint-config` from 0.4.0 to 0.5.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.4.0...@northern.tech/eslint-config-0.5.0)
  
  Updates `@rspack/cli` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack)
  
  Updates `@sentry/webpack-plugin` from 3.3.1 to 3.5.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/3.3.1...3.5.0)
  
  Updates `@types/node` from 22.15.3 to 22.15.29
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.32.1 to 8.33.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.33.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 4.4.1 to 4.5.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@4.5.0/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/coverage-v8)
  
  Updates `lint-staged` from 15.5.1 to 16.1.0
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v15.5.1...v16.1.0)
  
  Updates `msw` from 2.7.5 to 2.8.7
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.7.5...v2.8.7)
  
  Updates `undici` from 7.8.0 to 7.10.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.8.0...v7.10.0)
  
  Updates `vitest` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 3.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 22.15.29
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.33.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.8.7
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group across 1 directory with 3 updates
 ([96d55d3](https://github.com/mendersoftware/mender-server-enterprise/commit/96d55d3f34b37fa17ef593d310c1e6e9a0a80a2d))  by @dependabot[bot]


  Bumps the mui group with 3 updates in the /frontend directory: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.2.0 to 8.5.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...




### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com/mendersoftware/mender-server-enterprise/commit/5ba3fd7deda6421612029b31317cc61c2b1ef373))  by @alfrunes
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com/mendersoftware/mender-server-enterprise/commit/5c2e23a6ff9b073b38cad1ef56e8845264369817))  by @alfrunes




### Revert


- "ci: Debug mongodb in backend unit tests"
 ([441c1ea](https://github.com/mendersoftware/mender-server-enterprise/commit/441c1eaa43cc79737468aef3068784f0bfadef28))  by @alfrunes


  Enabling logging just overflows the log buffer.
  
  This reverts commit 6d164c4c70d1fff7d28e88a50390f8afb676c814.






## 4.1.0-saas.5 - 2025-05-09


### Bug fixes


- *(deployments)* Invalid Location header when returning 201 Created
 ([cfccf2a](https://github.com/mendersoftware/mender-server-enterprise/commit/cfccf2a8e71814d8fca40e9135aa6afe06f15344))  by @alfrunes


  The location strips the `/api` path prefix and returns the remaining
  absolute path as relative. Instead, always return the absolute path.

- *(deployments)* Validate configuration on updates
([MEN-8287](https://northerntech.atlassian.net/browse/MEN-8287)) ([ccad883](https://github.com/mendersoftware/mender-server-enterprise/commit/ccad883d7336da2e6181c995f4f09348220f4778))  by @kjaskiewiczz


  With this commit, when doing configuration update using internal
  endpoint, we validate the configuration.

- *(gui)* Fixed an issue that would prevent showing unassigned static group devices
([ME-519](https://northerntech.atlassian.net/browse/ME-519)) ([cf7f15d](https://github.com/mendersoftware/mender-server-enterprise/commit/cf7f15d7cc1b2761ec1ad2804387cb62e155504a))  by @mineralsfree

- *(gui)* Fixed an issue that would add device filter automatically
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([8d0233c](https://github.com/mendersoftware/mender-server-enterprise/commit/8d0233cadf69f6930888c7820579f02611841a02))  by @mineralsfree

- *(gui)* Fixed an issue with a filter input not reset after save
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([ed6b9f9](https://github.com/mendersoftware/mender-server-enterprise/commit/ed6b9f97d1d55bef11b50b880b9fd14a488d9d94))  by @mineralsfree

- *(gui)* Fixed an issue with 'true' value being set after selecting 'exists' operator
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([b8c8d8a](https://github.com/mendersoftware/mender-server-enterprise/commit/b8c8d8a9fea896dccc1add172816ebbb5b85ebfd))  by @mineralsfree

- *(gui)* Ensured selection filter is reset when attribute or value input are emptied
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([9cb2ff3](https://github.com/mendersoftware/mender-server-enterprise/commit/9cb2ff3e002d045a225c4a3de30be0cd51e6fc0e))  by @mineralsfree

- *(gui)* Restored global settings layout after general input layout adjustments
 ([f83c94e](https://github.com/mendersoftware/mender-server-enterprise/commit/f83c94eb38a1a425e8031d0693262120bb48db6b))  by @mzedel

- *(gui)* Fixed an issue that prevented showing deployment calendar entries
 ([a7d386f](https://github.com/mendersoftware/mender-server-enterprise/commit/a7d386fdcaa19f81db059d709e52d998c0e99ea8))  by @mzedel

- *(useradm)* RBAC - fix permissions related to inventory filters
([ME-510](https://northerntech.atlassian.net/browse/ME-510)) ([c38ab7f](https://github.com/mendersoftware/mender-server-enterprise/commit/c38ab7f5a024d2bdeffaff1d0a3ca06f0083d11a))  by @kjaskiewiczz


  Users without access to all devices should not be able to delete
  inventory filers.

- *(useradm)* Fix permissions for assigning users to tenants
([ME-507](https://northerntech.atlassian.net/browse/ME-507)) ([0efc65e](https://github.com/mendersoftware/mender-server-enterprise/commit/0efc65e970f2cb75fda55be534c13580d99dd239))  by @kjaskiewiczz


  User with multiple roles, where one of the roles is Admin role, should
  be able to assign users to tenants.

- Check if deployment was found when updating device deployment status
([MEN-7749](https://northerntech.atlassian.net/browse/MEN-7749)) ([6b15227](https://github.com/mendersoftware/mender-server-enterprise/commit/6b15227135cc38dd96813c204c3a12d494f0313f))  by @bahaa-ghazal
- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com/mendersoftware/mender-server-enterprise/commit/d80c818eed43765387cfe81445e187f9c1833156))  by @alfrunes


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(deployments)* Fix API specification
([QA-990](https://northerntech.atlassian.net/browse/QA-990)) ([4f8d069](https://github.com/mendersoftware/mender-server-enterprise/commit/4f8d069d054761479abad32b2c1630581be3a422))  by @kjaskiewiczz


  Remove type properties from fields where value is not strictly defined.

- *(inventory)* Migrate API specs to OpenAPI v3.0.1
([QA-886](https://northerntech.atlassian.net/browse/QA-886)) ([e7ce7e5](https://github.com/mendersoftware/mender-server-enterprise/commit/e7ce7e5762405732e9cb02ee32447dc1073ee369))  by @kjaskiewiczz

- Fix API specifications to be compliant with OpenAPI 3 format
([QA-990](https://northerntech.atlassian.net/browse/QA-990)) ([26e9fd2](https://github.com/mendersoftware/mender-server-enterprise/commit/26e9fd22c9e3a7c34b4564703842f8b7d7282948))  by @kjaskiewiczz
- Covert enterprise API docs to OpenAPI v3
([QA-886](https://northerntech.atlassian.net/browse/QA-886)) ([f44166c](https://github.com/mendersoftware/mender-server-enterprise/commit/f44166c8edf5a9c54e28631075511bbea0651721))  by @alfrunes




### Features


- *(deviceauth)* Rate limit authenticated devices API
([MEN-7744](https://northerntech.atlassian.net/browse/MEN-7744)) ([8c80280](https://github.com/mendersoftware/mender-server-enterprise/commit/8c8028081a54a62ba8673071350414b096aa87b0))  by @alfrunes


  Added adaptive ratelimiting for devices APIs based on the `max_devices`
  limit. Two new configuration options are exposed:
   * `ratelimits.interval` - duration until the quota resets
   * `ratelimits.quotas` - mapping plan names to quota weights. The final
     burst limit is computed as `ratelimits.quotas[plan] * max_devices`
  
  The rate limiting counter is independent for each API path (independent
  of method and version).

- *(deviceauth)* Rate limit device requests
([MEN-7744](https://northerntech.atlassian.net/browse/MEN-7744)) ([9c3041f](https://github.com/mendersoftware/mender-server-enterprise/commit/9c3041f5d54ea06c920ae0cc977c8af594133fb2))  by @alfrunes


  Added adaptive ratelimiting for devices APIs based on the `max_devices`
  limit. Two new configuration options are exposed:
   * `ratelimits.devices.enable` - enable device level rate limit
   * `ratelimits.devices.interval` - duration until the quota resets
   * `ratelimits.devices.quota_plan` - mapping plan names to quota
      weights. The final burst limit is computed as
      `ratelimits.quotas[plan] * max_devices`
   * `ratelimits.devices.quota_default` - rate limit fallback for plans
     with undefined limits.
  
  The rate limiting counter is independent for each API path (independent
  of method and version).

- *(generate-delta-worker)* Update `mender-artifact` to latest v4.1.0
([MEN-8337](https://northerntech.atlassian.net/browse/MEN-8337)) ([294c6dd](https://github.com/mendersoftware/mender-server-enterprise/commit/294c6dd8c2e9bef4c1907559f0f7fe8fd0583125))  by @lluiscampos


  Modifying also the integration to build the tool from source instead or
  repurposing the upstream Debian package. This has the main advantage
  that we can compile it statically (by disabling a feature that we don't
  use) and that we have control of the compatibility aspects of the
  binary.

- Add caching for device limits
([MEN-7760](https://northerntech.atlassian.net/browse/MEN-7760)) ([5466c62](https://github.com/mendersoftware/mender-server-enterprise/commit/5466c626ca1437ed366151263c3bc03686c58853))  by @alfrunes
- Delta generation job details view API support
([MEN-8289](https://northerntech.atlassian.net/browse/MEN-8289)) ([00fb186](https://github.com/mendersoftware/mender-server-enterprise/commit/00fb1864b6edf4db1f0037a34beb446d72503114))  by @merlin-northern
- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com/mendersoftware/mender-server-enterprise/commit/9016554b702297ad00f1a748d0824fdf19d05678))  by @bahaa-ghazal




### Revert


- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com/mendersoftware/mender-server-enterprise/commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548))  by @alfrunes


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.






## 4.1.0-saas.4 - 2025-04-10


### Bug fixes


- *(gui)* Fixed an issue where admin existence sometimes wasn't taken into account on tenant creation
 ([330ac67](https://github.com/mendersoftware/mender-server-enterprise/commit/330ac67ee20b0ffeaf9a20b9f48db5b48a2bd169))  by @mzedel

- *(gui)* Fixed an issue that prevented properly paginating deployments
([MEN-8212](https://northerntech.atlassian.net/browse/MEN-8212)) ([a20db14](https://github.com/mendersoftware/mender-server-enterprise/commit/a20db1477aab026d60297e789cbbd85e242b8d7c))  by @mzedel

- *(gui)* Fixed an issue on tenant creation that prevented some email addresses from becoming tenant admins
([ME-470](https://northerntech.atlassian.net/browse/ME-470)) ([20b32f9](https://github.com/mendersoftware/mender-server-enterprise/commit/20b32f90130521dd54d51ff30202e122b298a093))  by @mzedel

- *(gui)* Fixed an issue that would retain passwords on tenant creation across different admins
 ([a5e2132](https://github.com/mendersoftware/mender-server-enterprise/commit/a5e2132c015bd3a7c296c6848cf136157ffbad1b))  by @mzedel

- *(gui)* Fixed layout issue on tenant list + aligned styling with remainder of codebase
 ([cc41aee](https://github.com/mendersoftware/mender-server-enterprise/commit/cc41aee501ecd4834c73abc051e51df3a90b8868))  by @mzedel

- *(gui)* Fixed an issue propagating password validation errors
 ([d1d8827](https://github.com/mendersoftware/mender-server-enterprise/commit/d1d882768d39b7cca657cd091c5bcedd8e416f57))  by @mzedel

- *(gui)* Ensured errormessages get propagated in forms
 ([b19f8b3](https://github.com/mendersoftware/mender-server-enterprise/commit/b19f8b33727fd0aab573ebf677a93a3a7811ae39))  by @mzedel

- *(gui)* Fixed an issue that could hinder pagination in very frequently created deployments
 ([34ca4ea](https://github.com/mendersoftware/mender-server-enterprise/commit/34ca4eab7332388e3ddd5a830b8458890315ee42))  by @mzedel

- *(useradm)* Added missing permission scope option to allow generating correct types
 ([e956965](https://github.com/mendersoftware/mender-server-enterprise/commit/e9569657d3fd7dbf638879c320d79029e814ed48))  by @mzedel

- *(useradm)* Added missing permission information in API specs
 ([1f534d1](https://github.com/mendersoftware/mender-server-enterprise/commit/1f534d15c382da7fc3e0498bd064f2c9f6291814))  by @mzedel

- *(deployments)* Use the read preference in FindOldestActiveDeviceDeployment
 ([10f8b55](https://github.com/mendersoftware/mender-server-enterprise/commit/10f8b5503fa2901cb1ecdc374117b513ed9b841b))  by @merlin-northern




### Documentation


- *(deployments)* GET delta/jobs endpoint API docs
([MEN-8199](https://northerntech.atlassian.net/browse/MEN-8199)) ([8bec3b5](https://github.com/mendersoftware/mender-server-enterprise/commit/8bec3b59c805b55a52df77765bd794064e52d089))  by @merlin-northern

- *(deviceauth)* Enhance description of the /devices/count endpoint
([MEN-8255](https://northerntech.atlassian.net/browse/MEN-8255)) ([c9e3633](https://github.com/mendersoftware/mender-server-enterprise/commit/c9e3633f10d6439b8e6e19b49607ebb0d2c83c76))  by @kjaskiewiczz





### Features


- *(deployments)* Get the list of delta generation jobs
([MEN-8199](https://northerntech.atlassian.net/browse/MEN-8199)) ([a0ed3b0](https://github.com/mendersoftware/mender-server-enterprise/commit/a0ed3b08a5b91cadc6e334789aa205b57eab7694))  by @merlin-northern

- *(gui)* Made subtenant creation a bit more comfortable in case of errors
([ME-469](https://northerntech.atlassian.net/browse/ME-469)) ([e01171f](https://github.com/mendersoftware/mender-server-enterprise/commit/e01171fe5aa9434cad9eefb16f52a6c785657bbe))  by @mzedel

- *(gui)* Added more user visible context on tenant creation failures
 ([c027064](https://github.com/mendersoftware/mender-server-enterprise/commit/c02706471c536f15e844fd5806deb999dbdbb5d2))  by @mzedel


  - also centralized mui alert styling to account for increased usage

- *(gui)* Made login form less reactive when entering login info
([MEN-8221](https://northerntech.atlassian.net/browse/MEN-8221)) ([00b4d7b](https://github.com/mendersoftware/mender-server-enterprise/commit/00b4d7be55cfaebdbcd787e308a720d01a40362d))  by @mzedel

- *(gui)* Added sentry integration
 ([0fe2ad0](https://github.com/mendersoftware/mender-server-enterprise/commit/0fe2ad0682fc250f75947f8eda690663a3ad2b7d))  by @mzedel

- *(gui)* Enhanced debugging info to help track down user issues
 ([c559467](https://github.com/mendersoftware/mender-server-enterprise/commit/c559467c461470e66d7d3a68674511c1215a8cc2))  by @mzedel

- *(gui)* Allowed enabling fine grained state debug information to be sent
 ([298059d](https://github.com/mendersoftware/mender-server-enterprise/commit/298059dff2d29cb8367b50753e0b7421ceb28341))  by @mzedel





### Refac


- *(gui)* Split signup in separate forms to ease handling validation mode differences
 ([620592b](https://github.com/mendersoftware/mender-server-enterprise/commit/620592bea038b835990e7625db7ae7f736f3f6e4))  by @mzedel

- *(gui)* Rely on externally gzipping build files to use sourcemaps in sentry
 ([24bdd2f](https://github.com/mendersoftware/mender-server-enterprise/commit/24bdd2f3f048e8088daf40fffd92afc7eed15dbc))  by @mzedel







## 4.1.0-saas.3 - 2025-03-20


### Bug fixes


- *(deployment)* Ignore false errors when deleting data that does not exist
([MEN-8213](https://northerntech.atlassian.net/browse/MEN-8213)) ([532d95a](https://github.com/mendersoftware/mender-server-enterprise/commit/532d95ab87f1bea1027d7ff83b3281c7d4740f26))  by @bahaa-ghazal

- *(gui)* Removed border on active tab in left nav bar
([MEN-8113](https://northerntech.atlassian.net/browse/MEN-8113)) ([a5d5df4](https://github.com/mendersoftware/mender-server-enterprise/commit/a5d5df49f70a34427edcde7348858fbb9d18c4b7))  by @mineralsfree

- *(gui)* Fixed time filter in past deployments
([MEN-7989](https://northerntech.atlassian.net/browse/MEN-7989)) ([25cdee0](https://github.com/mendersoftware/mender-server-enterprise/commit/25cdee07a5e6f76942f8b0dcaa67a4f76b1b2ecb))  by @mineralsfree

- *(gui)* Fixed location not being changed on device status filter change
([MEN-8118](https://northerntech.atlassian.net/browse/MEN-8118)) ([36eb469](https://github.com/mendersoftware/mender-server-enterprise/commit/36eb4695544a0fdc2559d4178b9e0cfa5c647691))  by @mineralsfree

- *(gui)* Restored rspack to license generator compatible version
 ([1280dc7](https://github.com/mendersoftware/mender-server-enterprise/commit/1280dc7363135444575611f32f5011935557f01b))  by @mzedel

- *(gui)* Fixed default roles being shown before loading ones from backend
([MEN-8095](https://northerntech.atlassian.net/browse/MEN-8095)) ([d934020](https://github.com/mendersoftware/mender-server-enterprise/commit/d9340200ce40229fab441e2334117906ab18e103))  by @mineralsfree

- *(gui)* Fixed an issue that would prevent new signups from using the onboarding
 ([fbaa329](https://github.com/mendersoftware/mender-server-enterprise/commit/fbaa329fb66bb3dc687db463a7cc507f8643a6b8))  by @mzedel

- *(gui)* Default to eu in eu.hosted domain during signup
([MEN-7925](https://northerntech.atlassian.net/browse/MEN-7925)) ([0512d24](https://github.com/mendersoftware/mender-server-enterprise/commit/0512d24b7b6ddbf8e90677f737da4625d95c5e6f))  by @mineralsfree

- *(gui)* Fixed webhook configuration checks by subscription
 ([6b5989d](https://github.com/mendersoftware/mender-server-enterprise/commit/6b5989d8b61fc05bde9b788b69b60474f99983f2))  by @mzedel

- *(gui)* Ensured form validation is applied during validation phase only
 ([b6b870c](https://github.com/mendersoftware/mender-server-enterprise/commit/b6b870c9c39a3e5a24f42ef9bec02184fc830bb0))  by @mzedel

- *(gui)* Fixed permission extension issue in roles form
([MEN-8108](https://northerntech.atlassian.net/browse/MEN-8108)) ([0a41d0d](https://github.com/mendersoftware/mender-server-enterprise/commit/0a41d0dd4fec2a82ab8e746fa6a8a748843dc1a3))  by @mineralsfree

- *(gui)* Fixed an issue that prevented phased deployments when reusing phase definitions
([MEN-8192](https://northerntech.atlassian.net/browse/MEN-8192)) ([f9b735f](https://github.com/mendersoftware/mender-server-enterprise/commit/f9b735f250a41db9e073546fc69a6a471028a50a))  by @mzedel

- *(gui)* Fixed an issue that could clear search queries
 ([c308b2b](https://github.com/mendersoftware/mender-server-enterprise/commit/c308b2bd72f915c11521af236f9fd4ed6659f4e4))  by @mzedel


  - when search was run multiple times in non-search searchfields

- *(gui)* Provide more context on failed 2fa enabled login
 ([dfcb767](https://github.com/mendersoftware/mender-server-enterprise/commit/dfcb767e33c054bdca64aba209eb8ce05902a89a))  by @mzedel

- *(gui)* Fixed an issue that would prevent some info messages from showing
 ([e1277bd](https://github.com/mendersoftware/mender-server-enterprise/commit/e1277bdf3c289d2c383ce4303da4567606193bf5))  by @mzedel

- *(gui)* Restored group creation notification
 ([3bdb3f3](https://github.com/mendersoftware/mender-server-enterprise/commit/3bdb3f34c8b1e6aa3c2e1cf34a619933684d4f04))  by @mzedel

- *(iot-manager)* Do not store events if there are no integrations
([MEN-7868](https://northerntech.atlassian.net/browse/MEN-7868)) ([0c0ee9d](https://github.com/mendersoftware/mender-server-enterprise/commit/0c0ee9d3e497d04cbf43e4693fbdd17c30f1edb3))  by @merlin-northern

- *(iot-manager)* Creating new integration creates a new ID
([MEN-7801](https://northerntech.atlassian.net/browse/MEN-7801)) ([c52491e](https://github.com/mendersoftware/mender-server-enterprise/commit/c52491eb648fa6ab6550ca39386327b1ae2de4df))  by @merlin-northern

- *(tenantadm)* Emit structured logs on request panic
 ([6c67dc3](https://github.com/mendersoftware/mender-server-enterprise/commit/6c67dc36b07e41cbef1367f241a2637fcf311bab))  by @alfrunes


  The former request middleware handling Go panics would emit the panic
  stack trace in an unstructured format. This commit lets the accesslog
  handle it and emit it in the `trace` log context key.

- *(tenantadm)* Waiting for workflow does not abort immediately when it is not yet scheduled
([MEN-8165](https://northerntech.atlassian.net/browse/MEN-8165)) ([6dc0790](https://github.com/mendersoftware/mender-server-enterprise/commit/6dc0790b8c000eba3203fcc36ff9ccd303102ba0))  by @bahaa-ghazal

- Race when provisioning and connecting a device
([MEN-8164](https://northerntech.atlassian.net/browse/MEN-8164)) ([eae5bf2](https://github.com/mendersoftware/mender-server-enterprise/commit/eae5bf230060838f6b93d656ba19d68c609bb425))  by @alfrunes


  If a device gets provisioned and submits a connection request while the
  device is getting provisioned, the device might end up in an
  inconsistent state where the connection status gets overwritten to
  "unknown".
  The issue was discovered in a test where the system was under load
  and the device was running on the same network (artificially low RTT).
- Prevent demoting a service provider with children
([MEN-7841](https://northerntech.atlassian.net/browse/MEN-7841)) ([b342ada](https://github.com/mendersoftware/mender-server-enterprise/commit/b342adae3f343fcc4c82381732fbe33d91d318eb))  by @bahaa-ghazal
- Clear `auditlogs` when promoting a tenant to SP
([MEN-7787](https://northerntech.atlassian.net/browse/MEN-7787)) ([5ab72dc](https://github.com/mendersoftware/mender-server-enterprise/commit/5ab72dc60b6d3a0247c8774e13ff0a54dd8ea474))  by @bahaa-ghazal
- Stop deviceconnect's `/connect` endpoints from sending ping
([MEN-8061](https://northerntech.atlassian.net/browse/MEN-8061)) ([79a32a6](https://github.com/mendersoftware/mender-server-enterprise/commit/79a32a6f12fd1b90be3560a896e50d8d63516210))  by @bahaa-ghazal
- Generate delta worker aborting before artifact upload completes
([MEN-8177](https://northerntech.atlassian.net/browse/MEN-8177)) ([4901878](https://github.com/mendersoftware/mender-server-enterprise/commit/4901878b6eb41dd208ead2f55027b633749b2732))  by @alfrunes


  The artifact generator aborts uploading an artifact prematurely once
  either of the input files are processed and returns exit code 0. This
  results in a very confusing error where the API reports a successfully
  generated artifact, but the artifact is never fully uploaded and
  available through the APIs.
- Generate delta worker for custom S3 bucket
([MEN-8202](https://northerntech.atlassian.net/browse/MEN-8202)) ([0ac2923](https://github.com/mendersoftware/mender-server-enterprise/commit/0ac2923e0261a53a69f298b543e460143558c3e6))  by @alfrunes
- Skip IoT Core/IoT Hub integration if device is not yet provisioned
([MEN-8230](https://northerntech.atlassian.net/browse/MEN-8230)) ([eeffe42](https://github.com/mendersoftware/mender-server-enterprise/commit/eeffe42fd158956bb531c916639b84c93d6d4e63))  by @alfrunes


  If a device has not previously been provisioned, it is not part of the
  integration and should be excluded from the sync.




### Documentation


- Migrate deployments specs to OpenAPI 3.0
 ([4631b2f](https://github.com/mendersoftware/mender-server-enterprise/commit/4631b2fc3f16a53490089b273c708a0ffee3b345))  by @alfrunes
- Correct spelling errors and incorrect descriptions
 ([001407c](https://github.com/mendersoftware/mender-server-enterprise/commit/001407c4538f1cc7147c950ef73f27892c732476))  by @alfrunes
- Migrate deployments specs to OpenAPI 3 and align with open-source
 ([297b808](https://github.com/mendersoftware/mender-server-enterprise/commit/297b808bf43bfb04d6f17e7d5ec3405a5360aff8))  by @alfrunes




### Features


- *(gui)* Added year to timeframe picker
([MEN-8136](https://northerntech.atlassian.net/browse/MEN-8136)) ([48a5e98](https://github.com/mendersoftware/mender-server-enterprise/commit/48a5e98cdfc7793fac653f80d1dbe7ae6172956c))  by @mineralsfree

- *(gui)* Changed login form to a more stepwise approach in order to reduce confusion
([MEN-7761](https://northerntech.atlassian.net/browse/MEN-7761)) ([543bf7a](https://github.com/mendersoftware/mender-server-enterprise/commit/543bf7a7d0e6b2cd0badf20be9a9ecdb0ce2bc6c))  by @mzedel


  - this relies on an as of yet unreleased bugfix release of RHF
  Ticket: MEN-7761

- *(gui)* Made password forgotten flow more informative to reduce confusion
([MEN-7761](https://northerntech.atlassian.net/browse/MEN-7761)) ([ed81bc6](https://github.com/mendersoftware/mender-server-enterprise/commit/ed81bc69f2d809be0f95f060042c7762bd3855c6))  by @mzedel

- *(iot-manager)* Allowed disabling address verification during webhook configuration
 ([e05997c](https://github.com/mendersoftware/mender-server-enterprise/commit/e05997c7c7846c5fec9049a1b937461431687b3a))  by @mzedel

- *(iot-manager)* Added integration_id query parameter to API for getting events
([MEN-7801](https://northerntech.atlassian.net/browse/MEN-7801)) ([bc0dae3](https://github.com/mendersoftware/mender-server-enterprise/commit/bc0dae393ecf61edba3c71555248c2fef25cd2ac))  by @merlin-northern


  Allows to:
  * get device events from iot-manager by integration ID
  * maintains backward compatibility for GET /event
  * with UI calling the new endpoint this fixes the showing
    of events from old webhooks in the integraiton details

- Accept `null` to unset suspend and trial expiration date
([MEN-7727](https://northerntech.atlassian.net/browse/MEN-7727)) ([13046eb](https://github.com/mendersoftware/mender-server-enterprise/commit/13046ebdcb11607186f2a5e88b051e405ace9dc2))  by @bahaa-ghazal




### Refac


- *(gui)* Extraced login related form elements to isolate form handling
 ([0088e78](https://github.com/mendersoftware/mender-server-enterprise/commit/0088e78dac5aa9d8512809fb8a197428201e8a38))  by @mzedel







## 4.1.0-saas.2 - 2025-02-25


### Bug fixes


- *(gui)* Let read-only user no longer think they could act on selected releases
([MEN-8110](https://northerntech.atlassian.net/browse/MEN-8110)) ([dd710a7](https://github.com/mendersoftware/mender-server-enterprise/commit/dd710a723b68c15f6d92b22e3ea81356e5e638c7))  by @mzedel

  also aligned component label + usage with reality

- *(gui)* Fixed pagination for pending deployments
([MEN-8140](https://northerntech.atlassian.net/browse/MEN-8140)) ([c3f406b](https://github.com/mendersoftware/mender-server-enterprise/commit/c3f406b1585756cc9d57638a549edb7e4b81093e))  by @mzedel

- *(gui)* Prevented a situation where one release upload could prevent another
([MEN-8125](https://northerntech.atlassian.net/browse/MEN-8125)) ([84b24ec](https://github.com/mendersoftware/mender-server-enterprise/commit/84b24ec1ae572731c44cdb5ab937de13c9cc0bcb))  by @mzedel

- *(gui)* Made rbac limitations visible in release tagging too
 ([c706020](https://github.com/mendersoftware/mender-server-enterprise/commit/c7060207dfe15eae736bcfd5b9d84f51b8f083a7))  by @mzedel

- *(gui)* Ensured release tag creation is waited for before changing UI
([MEN-8078](https://northerntech.atlassian.net/browse/MEN-8078)) ([9b0c722](https://github.com/mendersoftware/mender-server-enterprise/commit/9b0c7226f187a77a4831460dd48ea8bc2cba9ef2))  by @mzedel

- *(gui)* Fixed an issue with editing credit card when no billing address was provided
([MEN-8154](https://northerntech.atlassian.net/browse/MEN-8154)) ([0fd9658](https://github.com/mendersoftware/mender-server-enterprise/commit/0fd9658edee50b7db614eb45a83931db43518380))  by @mineralsfree





### Documentation


- *(deployments)* Fix spelling
 ([f2a8379](https://github.com/mendersoftware/mender-server-enterprise/commit/f2a8379bd770e465573123d3f892642dfcdbeb72))  by @vbpieter

- Add missing breaking changes to enterprise changelog
 ([794bd4d](https://github.com/mendersoftware/mender-server-enterprise/commit/794bd4dc7f970ec9b026b3fdcf78d75dc226b39b))  by @alfrunes
- Add missing breaking changes to changelog
 ([799f42d](https://github.com/mendersoftware/mender-server-enterprise/commit/799f42dad02145fedf80d1d6e29bb5239536f7de))  by @alfrunes




### Features


- *(gui)* Split release deployment onboarding step in 2 steps
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([3fc2e9a](https://github.com/mendersoftware/mender-server-enterprise/commit/3fc2e9a61fe128b52b73ad24de356cfb59a658bd))  by @mineralsfree

- *(gui)* Made ui improvements to the deployment onboarding flow
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([35d0f11](https://github.com/mendersoftware/mender-server-enterprise/commit/35d0f116319efa79d24edc64957d3f0f6552e16c))  by @mineralsfree

- *(gui)* Made onboard action tooltip rely on position of action item
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([dfeb0d6](https://github.com/mendersoftware/mender-server-enterprise/commit/dfeb0d6e574d2192b59bfe4918645d1d07d61960))  by @mineralsfree

- *(gui)* Made device issue selection on devices page available for more plans
([MEN-8076](https://northerntech.atlassian.net/browse/MEN-8076)) ([d7d2f97](https://github.com/mendersoftware/mender-server-enterprise/commit/d7d2f976518ef822d103834e0eb1816f0fcdb01b))  by @mzedel

- *(gui)* Made device tag confirmation message align with change
 ([3374b93](https://github.com/mendersoftware/mender-server-enterprise/commit/3374b93c9d899d68a7563171ec1645c2987b7b92))  by @mzedel

- *(gui)* Unified dialog backdrop and esc closing behaviour
([MEN-7998](https://northerntech.atlassian.net/browse/MEN-7998)) ([8b78680](https://github.com/mendersoftware/mender-server-enterprise/commit/8b786806a390feda0281de233acf6639bc61a8a1))  by @mineralsfree

- Implementing internal `Tenantadm` api to remove parent reference from tenant
([MEN-8097](https://northerntech.atlassian.net/browse/MEN-8097)) ([63ac8bd](https://github.com/mendersoftware/mender-server-enterprise/commit/63ac8bd40d79a32c97e6b89436a39f74963d36a1))  by @bahaa-ghazal






## 4.1.0-saas.1 - 2025-02-20


### Bug fixes


- *(gui)* Fixed date parsing & formatting issues after dayjs migation
([95dd540](https://github.com/mendersoftware/mender-server-enterprise/commit/95dd5400cc14888ae965feeba48c21bef7e4b901))  by @mzedel

- *(gui)* Fixed an issue that would prevent showing phased deployments
([1e73ba7](https://github.com/mendersoftware/mender-server-enterprise/commit/1e73ba734acbb33f2432d0b209a4baafd669651d))  by @mzedel

- Fix(gui): ensured deployment phase information stays inside its boundaries
([MEN-7995](https://northerntech.atlassian.net/browse/MEN-7995)) ([87fe82d](https://github.com/mendersoftware/mender-server-enterprise/commit/87fe82d7467cdcaf95397f0e37889167456f105b))  by @mzedel

- Fix(gui): fixed an issue that prevented upload progress from being shown
  aligning upload progress tracking with updated payload structure after rtk migration
([MEN-8074](https://northerntech.atlassian.net/browse/MEN-8074)) ([1b715c8](https://github.com/mendersoftware/mender-server-enterprise/commit/1b715c82aa75e016a681038459bfadb6f3ae89cd))  by @mzedel




### Features


- Count devices deviceauth command line and workflow
([MEN-8058](https://northerntech.atlassian.net/browse/MEN-8058)) ([7128716](https://github.com/mendersoftware/mender-server-enterprise/commit/7128716912a562e28e52f1638ee6224273bb0dc5))  by @merlin-northern






## 4.1.0-saas - 2025-02-13


### Bug fixes


- *(gui)* Made user list tracking rely only on backend data instead of local store to prevent duplicate users listed
([MEN-8049](https://northerntech.atlassian.net/browse/MEN-8049)) ([7d1b060](https://github.com/mendersoftware/mender-server-enterprise/commit/7d1b060d096ff2549305cc0f453d8a35b21257b0))  by @mzedel

- *(gui)* Fixed an issue that would cause the ui to crash when creating phased deployments
 ([9827ba9](https://github.com/mendersoftware/mender-server-enterprise/commit/9827ba928889f52e7eb4216b68707386c082dc74))  by @mzedel

- *(gui)* Fixed remaining device percentage not being displayed correctly on phased deployment creation
 ([5600913](https://github.com/mendersoftware/mender-server-enterprise/commit/560091349c778c288ad1bdc5a8bcd9b54c39f399))  by @mzedel

- Update outdated api endpoints in the `inventory` service
([MEN-7017](https://northerntech.atlassian.net/browse/MEN-7017)) ([73c7149](https://github.com/mendersoftware/mender-server-enterprise/commit/73c714951a61642b2fc100214c61e5f66c27ee0c))  by @bahaa-ghazal
- Limiting the size of metadata when uploading and generating artifacts
([MEN-7166](https://northerntech.atlassian.net/browse/MEN-7166)) ([9e80728](https://github.com/mendersoftware/mender-server-enterprise/commit/9e8072874c94da9e7a3659207e08c6a05fc48cc4))  by @bahaa-ghazal




### Documentation


- *(deployments)* Clarifications for the GET /deployments version 2 endpoint.
([MEN-8053](https://northerntech.atlassian.net/browse/MEN-8053)) ([0231b1b](https://github.com/mendersoftware/mender-server-enterprise/commit/0231b1b1786a7c341d0b56544e17e952c4bd5059))  by @merlin-northern

- *(inventory)* Describe inventory webhook events.
([MEN-8041](https://northerntech.atlassian.net/browse/MEN-8041)) ([66df3f5](https://github.com/mendersoftware/mender-server-enterprise/commit/66df3f5532e8743176365c992f74afa2781bbf15))  by @merlin-northern





### Features


- *(gui)* Clarified user creation capabilities for non-enterprise users
([MEN-7883](https://northerntech.atlassian.net/browse/MEN-7883)) ([d2fd192](https://github.com/mendersoftware/mender-server-enterprise/commit/d2fd192e8c09443dabb694288d73636853b02d86))  by @mzedel

- *(gui)* Added automatic refresh to get webhook events
([MEN-8045](https://northerntech.atlassian.net/browse/MEN-8045)) ([502e06a](https://github.com/mendersoftware/mender-server-enterprise/commit/502e06aab96f3ce980cd6fe197a2fd6d7e99233a))  by @mzedel







## 4.0.0-rc.9 - 2025-01-30


### Bug fixes


- *(gui)* Ensured target directory is nonempty on artifact generation
([MEN-8010](https://northerntech.atlassian.net/browse/MEN-8010)) ([5616722](https://github.com/mendersoftware/mender-server-enterprise/commit/561672221f31d0be257c4e1da98c63eda40f792d))  by @mzedel

- *(gui)* Fixed an issue that could prevent listing devices with their custom identity in a deployment report
 ([f1fcf26](https://github.com/mendersoftware/mender-server-enterprise/commit/f1fcf26f33a3ae458e60f994fed60231d75abd5c))  by @mzedel

- *(gui)* Fixed an issue that would prevent navigating to devices from a software distribution chart
([MEN-8038](https://northerntech.atlassian.net/browse/MEN-8038)) ([6516986](https://github.com/mendersoftware/mender-server-enterprise/commit/6516986b82ce08ecdfd9ed3c790590796c60da2d))  by @mzedel

- *(useradm)* Resolve user ID to email on AssignUserToTenants.
([MEN-8004](https://northerntech.atlassian.net/browse/MEN-8004)) ([b7229df](https://github.com/mendersoftware/mender-server-enterprise/commit/b7229df43e563cd6fed0ddaab074fb4cae1cb4fd))  by @merlin-northern

- Grant `Read` role premission to download audit log
([MEN-7869](https://northerntech.atlassian.net/browse/MEN-7869)) ([0aee905](https://github.com/mendersoftware/mender-server-enterprise/commit/0aee905cd5bf48b5951ad8143852d648705d8b80))  by @bahaa-ghazal




### Features


- *(gui)* Added explanation about integration number limitation
([MEN-7899](https://northerntech.atlassian.net/browse/MEN-7899)) ([dbdfa67](https://github.com/mendersoftware/mender-server-enterprise/commit/dbdfa672a62eb30745fb4b0e73bea7d345644932))  by @mzedel





### Build


- *(make)* Add enterprise version build id
 ([d115b84](https://github.com/mendersoftware/mender-server-enterprise/commit/d115b848f436aa119f29ad79b8cd7e86b90c8666))  by @alfrunes


  Updates the linked version symbol to contain a suffix `+enterprise`.







## 4.0.0-rc.8 - 2025-01-27


### Bug fixes


- *(gui)* Aligned webhook details behaviour w/ rest of UI
([MEN-7955](https://northerntech.atlassian.net/browse/MEN-7955)) ([7860b5b](https://github.com/mendersoftware/mender-server-enterprise/commit/7860b5b40c698b580f5a299ee8c9206490ea5710))  by @mzedel

- *(gui)* Prevented sso config retrieval on plans that don't support this
 ([fe6da5d](https://github.com/mendersoftware/mender-server-enterprise/commit/fe6da5dbea68222226ab01f52df7e5975fedc09d))  by @mzedel

- *(gui)* Fixed an issue that would prevent deleting & tagging releases in the release overview
([MEN-7960](https://northerntech.atlassian.net/browse/MEN-7960)) ([16b2628](https://github.com/mendersoftware/mender-server-enterprise/commit/16b2628feaf39eba631b5ab013bf3eeecfa95217))  by @mzedel

- *(gui)* Let on-prem installations refer to the docs to prevent server-url misconfiguration following monorepo transition
([MEN-7948](https://northerntech.atlassian.net/browse/MEN-7948)) ([e0dae51](https://github.com/mendersoftware/mender-server-enterprise/commit/e0dae512f67f08f312a61bd3be8192b7bbb7d6db))  by @mzedel

- *(gui)* Fixed end date filters out today's entries in the Audit log, Deployments and Devices
 ([3ee84f2](https://github.com/mendersoftware/mender-server-enterprise/commit/3ee84f2d743b51462f72e68efeae870a51c4d12c))  by @aleksandrychev

- *(iot-manager)* Filter integrations by event scope
([MEN-7956](https://northerntech.atlassian.net/browse/MEN-7956)) ([08f062d](https://github.com/mendersoftware/mender-server-enterprise/commit/08f062db0f1b033bd4cae2052e7b7335e8d56df3))  by @kjaskiewiczz


  Decommission and provision device events and device status change
  event should be sent to integrations containing deviceauth scope.

- *(tenantadm)* It should not be possible to make tenant without device limit a Service Provider tenant
([MEN-7954](https://northerntech.atlassian.net/browse/MEN-7954)) ([f144db6](https://github.com/mendersoftware/mender-server-enterprise/commit/f144db677152250baa47ebede394fe8f85ee7d52))  by @kjaskiewiczz

- Deviceauth healthcheck panics malformed inventory address
 ([70d493a](https://github.com/mendersoftware/mender-server-enterprise/commit/70d493a6913827d893758cd481a535de67fbeff9))  by @alfrunes
- Use internal URLs for storage backend when generating artifacts
([MEN-7939](https://northerntech.atlassian.net/browse/MEN-7939)) ([3d72d5e](https://github.com/mendersoftware/mender-server-enterprise/commit/3d72d5e5b0294a3dcf3faa4413104ef27f95ba19))  by @alfrunes
  - **BREAKING**: Generate artifacts API ignores `storage.proxy_uri` and
`aws.external_url` configuration values and instead access the API using
the same URL as deployments service.


  When generating artifacts, the backend will use the direct access URL
  instead of rewriting the URL using the configured `storage.proxy_uri` or
  `aws.external_url`.
- Use internal URLs for storage backend when generating delta artifacts
([MEN-7939](https://northerntech.atlassian.net/browse/MEN-7939)) ([29eed8a](https://github.com/mendersoftware/mender-server-enterprise/commit/29eed8a37aba778309aca862135f13069abc1151))  by @alfrunes
  - **BREAKING**: Generating delta artifacts ignores `storage.proxy_uri`
and `aws.external_url` configuration values and instead access the API
using the same URL as deployments service.


  When generating delta artifacts, the backend will use the direct access
  URLs instead of rewriting the URL using the configured
  `storage.proxy_uri` or `aws.external_url`.
- Deployment device count should not exceed max devices
([MEN-7847](https://northerntech.atlassian.net/browse/MEN-7847)) ([15e5fee](https://github.com/mendersoftware/mender-server-enterprise/commit/15e5feec727e4257a1ee4345265146a194edb4ab))  by @alfrunes


  Added a condition to skip deployments when the device count reaches max
  devices.
- Segmentation fault for `create-org` CLI timeouts
 ([6054f85](https://github.com/mendersoftware/mender-server-enterprise/commit/6054f855a32e45b3d08f6f06fb15965e1a772b03))  by @alfrunes


  If the service times out waiting for a workflows to complete, the app
  can incorrectly return no error and a nil tenant object.
  This commit simplifies the polling loop and ensures that en error is
  always returned after timeouts.
- Align the tenantadm API with the documentation
([MEN-7986](https://northerntech.atlassian.net/browse/MEN-7986)) ([57a538c](https://github.com/mendersoftware/mender-server-enterprise/commit/57a538cda76a43b93d5a4a5bb191e63a42f40972))  by @alfrunes


  The v1 APIs are retrieving undocumented attributes from other backend
  services (deployments and deviceauth). As a side effect, the internal
  user authentication middleware is fetching this data on every request
  to the management APIs only to discard the information.




### Documentation


- Fix typo in snippet for creating tenant
 ([a346d33](https://github.com/mendersoftware/mender-server-enterprise/commit/a346d33781086d157d831478cfb64bebeef6c3bd))  by @alfrunes
- Docmentation on backend integration tests running separately
([QA-683](https://northerntech.atlassian.net/browse/QA-683)) ([a8f8d54](https://github.com/mendersoftware/mender-server-enterprise/commit/a8f8d545573100186fba953c7179592a23196b23))  by @merlin-northern
- Add missing API parameters to the documentation
 ([7f68520](https://github.com/mendersoftware/mender-server-enterprise/commit/7f68520e8dd4c102b78735b68c0bdbfb986685c7))  by @alfrunes




### Features


- *(gui)* Added feedback on file size limits to artifact upload dialog
([MEN-7858](https://northerntech.atlassian.net/browse/MEN-7858)) ([d612334](https://github.com/mendersoftware/mender-server-enterprise/commit/d612334ebfae6b1a3d416016ee500b89daa70804))  by @mzedel

- *(gui)* Aligned text input appearance with MUI updated guidelines
([MEN-7838](https://northerntech.atlassian.net/browse/MEN-7838)) ([e5d5672](https://github.com/mendersoftware/mender-server-enterprise/commit/e5d56720b901a451fa47a514424f710763b50291))  by @mzedel





### Performance


- Only count tenants when required
 ([55e953b](https://github.com/mendersoftware/mender-server-enterprise/commit/55e953b3b9112fadd04abe3bfe350afd27b23042))  by @alfrunes


  In most instances the tenant count is discarded.




### Refac


- Move compat tests to dedicated test suite
 ([059f437](https://github.com/mendersoftware/mender-server-enterprise/commit/059f4375d3b33073e711fdbf81212a2cd5dacfbb))  by @alfrunes
- Share path for upserting next deployment for a device
 ([5b863c9](https://github.com/mendersoftware/mender-server-enterprise/commit/5b863c951945528f090b55694d1d18c707940bfa))  by @alfrunes


  Makes conflict resolution with open source easier to manage.





