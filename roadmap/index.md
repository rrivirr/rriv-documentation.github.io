# Development Roadmap

## Phase 1

Use the WaterBear shield to provide kitted and reliable low cost monitoring systems.

* Field testing
* Finalize case, initial kitted systems, and reliability
	* Temperature + conductivity system (restoration)
	* Gas monitoring system (wetland/river science)
* Version 2 command line interface with menued navigation
* Create documentation for kits, deployment use, and DIY build.
* Sensor and actuator driver architecture
* USB access for mass storage, serial interface, and firmware update
* Workflows: scripted setup and tutorials
* Use nuanced build macros to defeat code size limitations

## Phase 2

Leverage standalone, modular RRIV PCBs to support advanced deployment management, telemetry, and configurations.  Support generic use cases and prototyping needs.

* Stackable, modular PCBs
	* Circular main board
	* Field access daugher board
	* Sensor driver boards, when needed
	* Power board(s)
	* Telemetry board(s), Bluetooth 
* Data storage and publishing from CLI
* Telemetry drivers
* Milestone 1 deployment management - sharable deployment configurations


## Phase 3

Sharing, usability, and power options

* Sharing, global repository
	* Data
	* Configurations
	* Workflows
* Load drivers at runtime
* Self charging power systems
