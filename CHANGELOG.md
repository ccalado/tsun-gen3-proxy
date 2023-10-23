# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.4.2] - 2023-10-21

- count unknown data types in received messages
- count definition errors in our internal tables
- increase test coverage of the Infos class to 100%
- avoid resetting the daily generation counters even if the inverter sends zero values at sunset
   
## [0.4.1] - 2023-10-20

- fix issue [#18](https://github.com/s-allius/tsun-gen3-proxy/issues/18)
- initialize the proxy statistics
- avoid resetting total generation counters
  
## [0.4.0] - 2023-10-16

- fix issue [#8](https://github.com/s-allius/tsun-gen3-proxy/issues/8)
- implement [#10](https://github.com/s-allius/tsun-gen3-proxy/issues/10)
- fix: don't dispatch ignored messages so that they are not forwarded
- add systemtests
- fix unit tests, which were broken since version 0.3.0
- add proxy device to home assistant
- add statistic counter to proxy device
- support multiple inverter registration at home assistant
  
## [0.3.0] - 2023-10-10

❗Due to the definition of values for diagnostics, the MQTT devices of controller and inverter should be deleted in the Home Assistant before updating to version '0.3.0'. After the update, these are automatically created again. The measurement data is retained.

### Changes

- optimize and reduce logging
- switch to pathon 3.12
- classify some values for diagnostics 
  
## [0.2.0] - 2023-10-07

This version halves the size of the Docker image and reduces the attack surface for security vulnerabilities, by omitting unneeded code. The feature set is exactly the same as the previous release version 0.1.0.

### Changes

- move from slim-bookworm to an alpine base image
- install python requirements with pip wheel
- disable DEBUG log for releases
- support building of release candidates

## [0.1.0] - 2023-10-06

- refactoring of the connection classes
- change user id on startup
- register MQTT topics to home assistant, even if we have multiple inverters

## [0.0.6] - 2023-10-03

- Bump aiomqtt to version 1.2.1
- Force MQTT registration when the home assistant has set the status to online again
- fix control byte output in tx trace
- dealloc async_stream instances in connection termination

## [0.0.5] - 2023-10-01

- Entity icons updated
- Prints version on start
- Prepare for MQTT component != sensor
- Add MQTT origin
  
## [0.0.4] - 2023-09-30

- With this patch we ignore the setting 'suggested_area' in config.toml, because it makes no sense with multiple devices. We are looking for a better solution without combining all values into one area again in a later version.
  
❗Due to the change from one device to multiple devices in the Home Assistant, the previous MQTT device should be deleted in the Home Assistant after the update to pre-release '0.0.4'. Afterwards, the proxy must be restarted again to ensure that the sub-devices are created completely.

### Added

- Register multiple devices at home-assistant instead of one for all measurements.
  Now we register: a Controller, the inverter and up to 4 input devices to home-assistant.
  
## [0.0.3] - 2023-09-28

### Added

- Fixes Running Proxy with host UID and GUID #2

## [0.0.2] - 2023-09-27

### Added

- Dockerfile opencontainer labels
- Send voltage and current of inputs to mqtt

## [0.0.1] - 2023-09-25

### Added

- Logger for inverter packets
- SIGTERM handler for fast docker restarts
- Proxy as non-root docker application 
- Unit- and system tests
- Home asssistant auto configuration
- Self-sufficient island operation without internet

## [0.0.0] - 2023-08-21

### Added

- First checkin, the project was born
