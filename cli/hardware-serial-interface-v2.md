# Hardware Serial Interface

## Overview


Command documentation conventions:

* \<required>
* [optional]
* {...} json blob


RRIV compatible devices are configured using declarative commands as
 
`<object> <command> [arguments]`  

Commands common to most objects are as follows:

### set

Creates or updates a resource.

### get

Gets current parameters of a resource, in a machine readable format.

### rm

Removes a resource

~~### ls~~

~~Lists all resources of a particular tyle, in a tabular human readable format.~~

### run

Custom actions

<br/>

## Commands

### Datalogger

Configurate data logger timing and metadata.

#### datalogger set {...}
{...} is JSON blob tha contains one or more datalogger parameter variables

```
{	
	"logger_name":"my device",
	"site_name":"OAK2:,
	"deployment_identifier":"X12",
	"interval": 10,
	"burst_number": 10,
	"start_up_delay": 1,
	"burst_delay": 2,
	"user_note": "none",
	"user_value": 12
}
```

| Parameter        | Data Type | Description |
| ---------------- | --------- | ------------|
| logger_name      | string    | a name for the logger |
| site_name        | string    | site code |
| deployment_identifier | string | identify a deployment |
| wake_interval         | int | minutes between wakes while deployed |
| warm\_up_delay   | int | minutes to wait between wakeup and measurement sensor initialization |
| burst_interval      | int | minutes between burst cycle initialization |
| user_note        | string | a note to add to each reading |
| user_value       | int | a value to add to each reading | 

#### datalogger get [parameter]

Get datalogger configuration.  When called with a parameter argument, returns just the parameter requested.  Otherwise returns the entire JSON blob.

#### datalogger reset

Resets datalogger to factory default configuration

#### datalogger mode \<mode_request> [arg]

Changes the mode the datalogger is in

| Mode Request         | Description |
| --------------------- | ------------|
| interactive           | Moves to interactive mode, which allows configuration |
| bench                 | Moves to bench mode, which adds continuous serial output of measurements in addition to interactive mode features |
| deploy                | Moves immediately to deployment, sleeps the devices and awaits the next measurement cycle |
| deploy \<timestamp> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   | Moves to wait mode and sleeps the device.  When timestamp is reached, the device wakes and deploys |

<br/>
### Sensor

Commands to configure installed sensors.

#### sensor \<id> set {...}

Creates or updates a sensor configuration.  If a sensor with the provided id is currently configured, it is updated.  Otherwise, a new sensor configuration is created.

The JSON blob can contain some or all configuration parameters for indicated sensor driver.  "type" specifies the kind of sensor installed and its corresponding driver, and is required when creating a new sensor.


Example (for generic analog sensor):

```
{	
	"type":"generic_analog",
	"burst_size":10,
	"adc_select":"internal",
	"sensor_port":1,
}
```



#### sensor [id] get [parameter]

Get a sensor configuration, corresponding to the id.  When called with a parameter argument, returns just the parameter requested.  Otherwise returns the entire JSON blob.

If id is not specified, returns a JSON array containing all sensor configurations.

#### sensor rm \<id>

Remove the sensor configuration matching the corresponding id

#### sensor ls

List all configured sensors in a tabluar format

#### sensor <id> calibration <subcommand> <args>
Sensor calibration is driver dependent, and subcommands are implemented on a per-driver basis.

##### get
Get JSON blob of current calibration parameters, fit, and status of current calibration underway if any.
##### status
Tabular, human readable output of current calibration parameters, fit, and status of calibration underway if any.
##### set <parameter> <val>
Set a calibration parameter as defined by the driver
##### fit [type]
##### clear
Clear calibration of given sensor
##### run \<command>

<br/>
### Actuator

Summary: actuator set, get, rm, ls

#### actuator [id] set {...}

Creates or updates an actuator configuration.  If an actuator with the provided id is currently configured, it is updated.  Otherwise, a new sensor configuration is created.

#### actuator \<id> get [parameter]

Get a actuator configuration, corresponding to the id.  When called with a parameter argument, returns just the parameter requested.  Otherwise returns the entire JSON blob.

If id is not specified, returns a JSON array containing all actuator configurations.

#### actuator rm \<id>

Remove the actuator configuration matching the corresponding id

#### actuator ls

List all configured actuators in a tabluar format

<br/>
### Telemeter

Summary: telemeter set, get, rm, ls

#### telemeter [id] set {...}

Creates or updates an telemeter configuration.  If an actuator with the provided id is currently configured, it is updated.  Otherwise, a new sensor configuration is created.

#### telemeter \<id> get [parameter]

Get a actuator configuration, corresponding to the id.  When called with a parameter argument, returns just the parameter requested.  Otherwise returns the entire JSON blob.

If id is not specified, returns a JSON array containing all telemeter configurations.

#### telemeter rm \<id>

Remove the telemeter configuration matching the corresponding id

#### telemeter ls

List all configured telemeters in a tabluar format


<br/>
### Board
The commands access features of the board itself and firmware metadata

#### board version

#### board firmware warranty
#### board firmware conditions
#### board firmware license

#### board rtc set \<epoch>
Set real time clock epoch time

#### board rtc get
Get the current real time clock epoch time stored on a RRIV device

#### board restart


#### board i2c ls
#### board memory check
#### board mcu [stop,sleep]

#### board signal <signal> [high,low]

| Signal       | Description |
| --------------------- | ------------|
| exADC | enable/disable exADC|
| 3v3Boost | enable/disable 3v3 boost converted|








