# Thermistor Ring Protocols

## Thermistor Ring Calibration
* Thermistor ring outputs two sets of values: the raw °C values from the digital thermistors using the factory calibration and the calibrated values using the offset produced by calibration.

### Thermistor Ring Calibration Commands

1. Set the temperature
```rrivctl sensor set RING01 -f configuration/ring_temprature.json```
2. Clear existing calibration
```rivctl calibrate sensor RING01 clear```
3. Calibrate for a given point (here we are calibrating when the known temperature is 22.3°C)
```rrivctl calibrate sensor RING01 point 22.3```
4. This command will list the current ring values
```rivctl calibrate sensor RING01 list```
5. Now we apply the calibration data to our dataset.
```rivctl calibrate sensor RING01 fit```
6. Now we can run the command below and we will see all the configs including the calibration.
```rivctl sensor get RING01```
