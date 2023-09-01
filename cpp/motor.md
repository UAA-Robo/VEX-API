# motor

`vex::motor( int32_t index)` <br>
`vex::motor( int32_t index, bool reverse)` <br>
`vex::motor( int32_t index, gearSetting gears)` <br>
`vex::motor( int32_t index, gearSetting gears, bool reverse)` <br>

<b> Parameters </b> <br>

| Name | Value | Description |
| :--- | :---- | :---------- |
| index | int32_t | The port index for this motor object. The index is zero-based. |
| reverse | bool | Sets the reverse flag for the new motor object. |
| gears | [gearSetting](cpp/units?id=gearsetting) | sets the gear's setting for the new motor object. |

<b> Example </b> <br>

```clike
vex::motor my_left_motor = vex::motor(vex::PORT1);  // Initialize my_left_motor at port 1
vex::motor my_right_motor = vex::motor(vex::PORT2, true);  // Initialize my_right_motor at port 2 and sets the reverse flag to true
```

______________________________________________________________________________________________________________________________

### setReversed
`void setReversed(bool value)`

**Description** <br>
Sets the motor mode to "reverse", which will make motor commands spin the motor in the opposite direction.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | bool | If set to true, motor commands spin the motor in the opposite direction. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);
my_motor.setReversed(true);  // Set the motor to spin in reverse
 
// Spins my_motor for 3 seconds
my_motor.spin(vex::directionType::fwd);  //Spinning forward will now be reversed
vex::task::sleep(3000);
my_motor.stop();
```

### setVelocity
`void setVelocity(double velocity, velocityUnits units)` <br>
`void setVelocity(double velocity, percentUnits units)`

**Description** <br>
Sets the velocity of the motor based on the parameters set in the command. This command will not run the motor. Any subsequent call that does not contain a specified motor velocity will use this value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| velocity | double | Sets the amount of velocity. |
| units | [vex::velocityUnits](cpp/units?id=velocityunits) | The measurement unit for the velocity value. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the velocity value. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setVelocity(50.0, vex::velocityUnits::pct);  // Sets my_motor's default velocity to 50%
  
// Spins my_motor for 3 seconds
my_motor.spin(vex::directionType::fwd);
vex::task::sleep(3000);
my_motor.stop();
```

### setBrake (Legacy)
`void setBrake(brakeType mode)`

**Description** <br>
Sets the stopping mode of the motor by passing a brake mode as a parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| mode | [vex::brakeType](cpp/units?id=braketype) | The stopping mode can be set to coast, brake, or hold. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setStopping(vex::brakeType::coast);  // Sets my_motor's stopping mode to coast.
  
// Spins my_motor for 3 seconds
my_motor.spin(vex::directionType::fwd);
vex::task::sleep(3000);
my_motor.stop();  // Watch the motor spin down!
```

### setStopping
`void setStopping(brakeType mode)`

**Description** <br>
Sets the stopping mode of the motor by passing a brake mode as a parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| mode | [vex::brakeType](cpp/units?id=braketype) | The stopping mode can be set to coast, brake, or hold. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setStopping(vex::brakeType::coast);  // Sets my_motor's stopping mode to coast.
// Spins my_motor for 3 seconds
my_motor.spin(vex::directionType::fwd);
vex::task::sleep(3000);
my_motor.stop();  // Watch the robot slide!
```

### resetPosition
`void resetPosition()`

**Description** <br>
Resets the motor's encoder to the value of zero.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 50.0, vex::percentUnits::pct);  // Spin the motor
vex::task::sleep(1000);  // Spin for 1 second
my_motor.stop();
my_motor.resetPosition();  // Resets my_motor's encoder to the value of zero at the current motor position.
```

### setPosition
`void setPosition(double value, rotationUnits units)`

**Description** <br>
Sets the value of the motor's encoder to the value specified in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | Sets the current position of the motor. |
| units | [vex::rotationUnits](cpp/units?id=rotationunits) | The measurement unit for the position value. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
  
// Spins my_motor for 3 seconds
my_motor.spin(vex::directionType::fwd);
vex::task::sleep(3000);
my_motor.stop();
  
my_motor.setPosition(120.0, vex::rotationUnits::deg);  // Sets my_motor's encoder to the value of 120 degrees at the current motor position.
```

### setTimeout
`void setTimeout(int32_t time, timeUnits units)`

**Description** <br>
Sets the timeout for the motor. If the motor does not reach its' commanded position prior to the completion of the timeout, the motor will stop.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| time | int32_t | Sets the amount of time. |
| units | [vex::timeUnits](cpp/units?id=timeunits) | The measurement unit for the time value. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setTimeout(5, vex::timeUnits::sec);  // Sets my_motor's timeout to 5 seconds
my_motor.spinFor(vex::directionType::fwd, 1.0, vex::rotationUnits::rev, false);  // Spin for one rotation
// If the motor does not finish its spin in 5 seconds, the motor will stop
  
```


### setMaxTorque
`void setMaxTorque(double value, percentUnits units)` <br>
`void setMaxTorque(double value, torqueUnits units)` <br>
`void setMaxTorque(double value, currentUnits units)` <br>

**Description** <br>
Sets the max torque of the motor.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | Sets the amount of torque. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the torque value. |
| units | [vex::torqueUnits](cpp/units?id=torqueunits) | The measurement unit for the torque value, |
| units | [vex::currentUnits](cpp/units?id=currentunits) | The measurement unit for the torque value. |

**Example** 
```clike
vex::motor my_lift_motor = vex::motor(vex::PORT1);  // Initialize my_lift_motor at port 1
my_lift_motor.setMaxTorque(2.5, vex::currentUnits::amp);  // Sets my_lift_motor's maximum torque to that calculated by a 2.5 amp current draw
  
my_lift_motor.spinFor(vex::directionType::fwd, 0.75, vex::rotationUnits::rev, false);
  
```
______________________________________________________________________________________________________________________________


### spin
`void spin(directionType dir)` <br>
`void spin(directionType dir, double velocity, velocityUnits units)` <br>
`void spin(directionType dir, double velocity, percentUnits units)` <br>
`void spin(directionType dir, double voltage, voltageUnits units)`

**Description** <br>
Turns on the motor and spins it in a specified direction and a specified velocity (if included).

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| dir | [vex::directionType](cpp/units?id=directiontype) | The direction to spin the motor. |
| velocity | double | Sets the amount of velocity. |
| voltage | double | Sets the amount of volts. |
| units | [vex::velocityUnits](cpp/units?id=velocityunits) | The measurement unit for the velocity value. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the velocity value. |
| units | [vex::voltageUnits](cpp/units?id=voltageunits) | The measurement unit for the voltage value. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setVelocity(50.0, vex::velocityUnits::pct);  // Sets the default velocity of my_motor to 50%
  
my_motor.spin(vex::directionType::fwd, 100.0, vex::velocityUnits::pct);  // Spins my_motor at 100% velocity
vex::task::sleep(1000);
my_motor.stop();
  
my_motor.spin(vex::directionType::fwd);  // Spins my_motor at default velocity of 50%
```


### spinTo / spinToPosition
`bool spinTo(double rotation, rotationUnits units, bool waitForCompletion=true)` <br>
`bool spinTo(double rotation, rotationUnits units, double velocity, velocityUnits units_v, bool waitForCompletion=true)` <br> <br>

`bool spinToPosition(double rotation, rotationUnits units, bool waitForCompletion=true)` <br>
`bool spinToPosition(double rotation, rotationUnits units, double velocity, velocityUnits units_v, bool waitForCompletion=true)`

**Description** <br>
Turns on the motor and spins it to an absolute target rotation value at a specified velocity (if included). <br>
*Returns* a Boolean that signifies when the motor has reached the target rotation value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| rotation | double | Sets the amount of rotation. |
| units | [vex::rotationUnits](cpp/units?id=rotationunits) | The measurement unit for the rotation value. |
| velocity | double | Sets the amount of velocity. |
| units_v | [vex::velocityUnits](cpp/units?id=velocityunits) | The measurement unit for the velocity value. |
| waitForCompletion | bool | (optional) If true, your program will wait until the motor reaches the target rotational value. If false, the program will continue after calling this function. By default, this parameter is true. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spinTo(120.0, vex::rotationUnits::deg, 10.0, vex::velocityUnits::pct, false);  // Spins my_motor to the 120 degree position at 10% velocity
// . . .
// Code continues to run after function call
```


### spinFor
`bool spinFor(double time, timeUnits units);` <br>
`bool spinFor(double time, timeUnits units, double velocity, velocityUnits units_v)` <br>
`bool spinFor(directionType dir, double time, timeUnits)` <br>
`bool spinFor(directionType dir, double time, timeUnits, double velocity, velocityUnits units_v)`

**Description** <br>
Turns on the motor and spins it to a relative target value at a specified velocity. <br>
*Returns* true on success, false if parameter error

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| time | double | Sets the amount of time. |
| units | [vex::timeUnits](cpp/units?id=timeunits) | The measurement unit for the time value. |
| velocity | double | Sets the amount of velocity. |
| units_v | [vex::velocityUnits](cpp/units?id=velocityunits) | The measurement unit for the velocity value. |
| dir | [vex::directionType](cpp/units?id=directiontype) | Specifies the direction to the spin the motor in. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spinFor(vex::directionType::fwd, 10.0, vex::timeUnits::sec);  // Spins my_motor for 10 seconds at the default velocity
```


### stop
`void stop()`

**Description** <br>
Stops the motor using the default brake mode.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 50.0, vex::velocityUnits::pct);  // Spins my_motor at 50% velocity in the forward direction
  
my_motor.stop();  // Stops my_motor
```
______________________________________________________________________________________________________________________________


### isSpinning
`bool isSpinning()`

**Description** <br>
Checks to see if the motor is rotating to a specific target. <br>
*Returns* a true Boolean if the motor is on and is rotating to a target. Returns a false Boolean if the motor is done rotating to a target.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spinFor(vex::directionType::fwd, 10.0, vex::timeUnits::sec);  // Spins my_motor for 10 seconds at the default velocity

bool my_status = my_motor.isSpinning();  // Stores to my_status whether my_motor is spinning or not
```


### isDone / isSpinningMode
`bool isDone()` <br>
`bool isSpinningMode()`

**Description** <br>
Checks to see if the motor is done rotating to a specific target. <br>
*Returns* a false Boolean if the motor is on and is rotating to a target. Returns a true Boolean if the motor is done rotating to a target.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spinFor(vex::directionType::fwd, 2.5, vex::timeUnits::sec);  // Spins my_motor for 2.5 seconds at the default velocity

vex::task::sleep(5000);  // Wait for 5 seconds
if (my_motor.isDone()) {
    // Execute functions if my_motor is done spinning
}
```


### direction
`directionType direction()`

**Description** <br>
Gets which direction the motor is spinning. <br>
*Returns* the direction that the motor is spinning.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd);  // Spins my_motor forward at the default velocity

vex::task::sleep(5000);  // Wait for 5 seconds
if (my_motor.direction() == vex::directionType::fwd) {
    // Execute functions if my_motor is spinning forward
}
```


### position
`double position(rotationUnits units)`

**Description** <br>
Gets the current position of the motor's encoder. <br>
*Returns* a double that represents the current position of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::rotationUnits](cpp/units?id=rotationunits) | The measurement unit for the position. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 10.0, vex::velocityUnits::pct);  // Spins my_motor at 10% velocity


if (my_motor.position(vex::rotationUnits::deg) > 120) {
    // Execute functions if my_motor has rotated farther than 120 degrees
}
```


### velocity
`double position(velocityUnits units)` <br>
`double position(percentUnits units)`

**Description** <br>
Gets the current velocity of the motor. <br>
*Returns* a double that represents the current velocity of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::velocityUnits](cpp/units?id=velocityunits) | The measurement unit for the velocity. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the velocity. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setVelocity(75.0, vex::velocityUnits::pct);  // Sets the default velocity of my_motor
my_motor.spin(vex::directionType::fwd, 50.0, vex::velocityUnits::pct);  // Spins my_motor at 50% velocity


if (my_motor.velocity(vex::velocityUnits::pct) != 50.0) {
    // Execute functions if my_motor is not spinning at 50% velocity
}
```


### current
`double current(currentUnits units = currentUnits::amp)` <br>
`double position(percentUnits units)`

**Description** <br>
Gets the electrical voltage of the motor in percentage of maximum (if specified) <br>
*Returns* a double that represents the electrical current of the motor in the units defined in the parameter or as percentage of max current.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::currentUnits](cpp/units?id=currentunits) | The measurement unit for the current, defaults to vex::currentUnits::amp. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the current. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setVelocity(100.0, vex::velocityUnits::pct);  // Sets the default velocity of my_motor
my_motor.spin(vex::directionType::fwd);  // Spins my_motor at default velocity


double my_current = my_motor.current();  // Gets the electrical current of my_motor in amps
```


### current
`double current(currentUnits units = currentUnits::amp)` <br>
`double position(percentUnits units)`

**Description** <br>
Gets the electrical voltage of the motor in percentage of maximum (if specified). <br>
*Returns* a double that represents the electrical current of the motor in the units defined in the parameter or as percentage of max current.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::currentUnits](cpp/units?id=currentunits) | The measurement unit for the current, defaults to vex::currentUnits::amp. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the current. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.setVelocity(100.0, vex::velocityUnits::pct);  // Sets the default velocity of my_motor
my_motor.spin(vex::directionType::fwd);  // Spins my_motor at default velocity


double my_current = my_motor.current();  // Gets the electrical current of my_motor in amps
```


### voltage
`double voltage(voltageUnits units = voltageUnits::volt)`

**Description** <br>
Gets the electrical voltage of the motor. <br>
*Returns* a double that represents the electrical voltage of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::voltageUnits](cpp/units?id=voltageunits) | The measurement unit for the voltage. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 4.0, vex::voltageUnits::volt);  // Spins my_motor at 4.0 volts


double my_voltage = my_motor.voltage();  // Gets the voltage of my_motor in volts
```


### power
`double power(powerUnits units = powerUnits::watt)`

**Description** <br>
Gets the power of the motor. <br>
*Returns* a double that represents the power of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::powerUnits](cpp/units?id=powerunits) | The measurement unit for the power. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 20.0, vex::velocityUnits::pct);  // Spins my_motor at 20% velocity


double my_power = my_motor.power();  // Gets the voltage of my_motor in watts
```


### torque
`double torque(torqueUnits units = torqueUnits::Nm)`

**Description** <br>
Gets the torque of the motor. <br>
*Returns* a double that represents the torque of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::torqueUnits](cpp/units?id=torqueunits) | The measurement unit for the torque. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 10.0, vex::velocityUnits::pct);  // Spins my_motor at 10% velocity


double my_torque = my_motor.torque();  // Gets the torque of my_motor in Nm
```


### efficiency
`double efficiency(percentUnits units = percentUnits::pct)`

**Description** <br>
Gets the efficiency of the motor. <br>
*Returns* the efficiency of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::percentUnits](cpp/units?id=percentunits) | (Optional) The measurement unit for the efficiency. By default, this parameter is a percentage. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 25.0, vex::velocityUnits::pct);  // Spins my_motor at 25% velocity


double my_efficiency = my_motor.efficiency();  // Gets the efficiency of my_motor as a percentage
```


### temperature
`double temperature(percentUnits units = percentUnits::pct)` <br>
`double temperature(temperatureUnits units)`

**Description** <br>
Gets the temperature of the motor. <br>
*Returns* the temperature of the motor in the units defined in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the temperature |
| units | [vex::temperatureUnits](cpp/units?id=temperatureunits) | The measurement unit for the temperature. |

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
my_motor.spin(vex::directionType::fwd, 100.0, vex::velocityUnits::pct);  // Spins my_motor at 100% velocity


if (my_motor.temperature(vex::temperatureUnits::celsius) > 30) {
    // Execute functions if my_motor is over 30 degrees Celsius
}
```


### getMotorType
`int32_t getMotorType()`

**Description** <br>
Gets the type of the motor, 11W or 5.5W. <br>
*Returns* the type of the motor, 0 is 11W, 1 is 5.5W.

**Example** 
```clike
vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1

// Spin my_motor differently based on its type
if (my_motor.getMotorType() == 1) my_motor.spin(vex::directionType::fwd, 35.0, vex::velocityUnits::pct);
else my_motor.spin(vex::directionType::fwd, 25.0, vex::velocityUnits::pct);
```