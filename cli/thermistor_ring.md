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

4. 




rivctl sensor set RING01 -l/configuration/ring_temperature.json
rivctl calibrate sensor RING01 clear
rivctl calibrate sensor RING01 point 22.3
rivctl calibrate sensor RING01 list
{ point: 22.3, values: [20.1, 23.1, 21.2, 20.5, 22.1, Error] }
rivctl calibrate sensor RING01 point 22.3
rivctl calibrate sensor RING01 list
{ point: 22.3, values: [20.1, 23.1, 21.2, 20.5, 22.1, 21.2] }
rivctl calibrate sensor RING01 fit
Fit complete!
rivctl sensor get RING01
{
...
calibration:
}
