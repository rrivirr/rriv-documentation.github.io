# Steps
The new C++ class file created by the driver template script contains the complete skeleton of variables and functions needed to create a working driver for your sensor.  However, some functions and variables will need to be updated to complete the implementation of the driver.  Other functions and variables only need to be updated to implement optional features.  There are also functions and variables that do not need to be updated at all, they are just part of the driver skeleton code itself.

An approach to updating necessary functions and variables should proceed as follows:
1. Implement sensor setup and measurement functionality.
2. Implement data output functionality.
3. Implement sensor specific configuration functionality (optional).
4. Implement callibration functionality (optional).

## Implement sensor setup and measurement functionality.

Sensor setup and measurement functionality is implemented by updating the following functions:
1. setup()
2. stop()
3. isWarmedup()
4. takeMeasurement()

### setup()

The *setup()* function should preform any logic that is needed to start collecting readings from the sensor.  An analog sensor typically has not setup logic.  iDigital sensors, such as I2C, SPI, or GPIO protocol sensors, often _will_ have commands that must be sent to them to start collecting readings, or select certain functionality.  Details on this can be found in the documentation for the sensor being integrated.  This logic all goes in the setup() function.

### stop()

*stop()* is called for each sensor right before the datalogger goes to sleep between measurement cycles.  Some digital sensors have specific logic for halting readings, or have specific low power modes.  Any related logic from the sensor's documentation should be implemented in the stop() function.

### isWarmedUp()

*isWarmedUp()* returns a boolean value, indicating if the sensor is ready to start returning values.  *isWarmedUp()* is called after *setup()*, and the datalogger will wait for *isWarmedUp()* to return true before starting to read measurements from the sensor.  The logic of *isWarmedUp()* will typically be a time delay or  command that checks with a digital sensor for readiness.  More advanced implementations might look at a standard deviation of returned values, such as for an analog sensor.

### takeMeasurement()

This function attempts to take a single measurement from the sensor, and returns true or false depending on if the measurement was successfully taken.  Additionally, this function must save the measurement value into the *this.value* and add this value into the burst summary calculation logic.  In the case where a sensor returns multiple variable, the class must be updated to provide private storage for as many variables as necessary and all must be populated on a successful sensor read. 

Burst summary calculation is the mechanism by which multiple readings during a burst are combined to produce a single reading, typically a mean value.  addValueToBurstSummaryMean(tag, value) is used to track these values and later produce a mean.  To use this function in takeMeasurement, use a #define to define a tag for each variable returned by the sensor, and call addValueToBurstSummaryMean with this tag in the first parameter and a measuremented value in the second parameter for each variable measured successfully by the sensor.


## Implement data output functionality.

## Implement sensor specific configuration functionality (optional).

## Implement callibration functionality (optional).
