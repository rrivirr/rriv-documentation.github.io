# Thermistor Ring Protocols

## Thermistor Ring Calibration
* Thermistor ring outputs two sets of values: the raw °C values from the digital thermistors using the factory calibration and the calibrated values using the offset produced by calibration.

### Thermistor Ring Calibration Commands

1. Set the temperature
```rrivctl sensor set RING01 -f configuration/ring_temprature.json```
2. Clear existing calibration
```rivctl calibrate sensor RING01 clear```
3. Cal
```rrivctl calibrate sensor RING01 point 22.3```

4. 
