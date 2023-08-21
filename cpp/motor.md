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
| gears | gearSetting | sets the gear's setting for the new motor object. |

<b> Example </b> <br>

> ```clike
> vex::motor my_left_motor = vex::motor(vex::PORT1);  // Initialize left_motor at port 1
> vex::motor my_right_motor = vex::motor(vex::PORT2, true);  // Initialize right_motor at port 2 and sets the reverse flag to true
> ```

______________________________________________________________________________________________________________________________

## <u>Setting</u>

### setReversed
`void setReversed(bool value)`

**Description** <br>
Sets the motor mode to "reverse", which will make motor commands spin the motor in the opposite direction.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | bool | If set to true, motor commands spin the motor in the opposite direction. |

**Example** 
>```clike
> vex::motor my_motor = vex::motor(vex::PORT1);
> my_motor.setReversed(true); // Set the motor to spin in reverse
> 
> // Spins motor for 3 seconds
> my_motor.spin(vex::directionType::fwd);  //Spinning forward will now be reversed
> vex::task::sleep(3000);
> my_motor.stop();
>```

### setVelocity
`void setVelocity(double velocity, velocityUnits units)` <br>
`void setVelocity(double velocity, percentUnits units)`

**Description** <br>
Sets the velocity of the motor based on the parameters set in the command. This command will not run the motor. Any subsequent call that does not contain a specified motor velocity will use this value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| velocity | double | Sets the amount of velocity. |
| units | vex::velocityUnits | The measurement unit for the velocity value. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the velocity value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, vex::velocityUnits::pct);  // Sets my_motor's default velocity to 50%
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(vex::directionType::fwd);
>  vex::task::sleep(3000);
>  my_motor.stop();
>```

### setBrake (Legacy)
`void setBrake(brakeType mode)`

**Description** <br>
Sets the stopping mode of the motor by passing a brake mode as a parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| mode | vex::brakeType | The stopping mode can be set to coast, brake, or hold. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(coast);  // Sets my_motor's stopping mode to coast.
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(vex::directionType::fwd);
>  vex::task::sleep(3000);
>  my_motor.stop();  // Watch the motor spin down!
>```

### setStopping
`void setStopping(brakeType mode)`

**Description** <br>
Sets the stopping mode of the motor by passing a brake mode as a parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| mode | vex::brakeType | The stopping mode can be set to coast, brake, or hold. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(vex::coast);  // Sets my_motor's stopping mode to coast.
>  // Spins motor for 3 seconds
>  my_motor.spin(vex::directionType::fwd);
>  vex::task::sleep(3000);
>  my_motor.stop();  // Watch the robot slide!
>```

### resetPosition
`void resetPosition()`

**Description** <br>
Resets the motor's encoder to the value of zero.

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.spin(vex::directionType::fwd, 50.0, vex::percentUnits::pct); // Spin the motor
>  vex::task::sleep(1000);  // Spin for 1 second
>  my_motor.stop();
>  my_motor.resetPosition();  // Resets my_motor's encoder to the value of zero at the current motor position.
>```

### setPosition
`void setPosition(double value, rotationUnits units)`

**Description** <br>
Sets the value of the motor's encoder to the value specified in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | Sets the current position of the motor. |
| units | vex::rotationUnits | The measurement unit for the position value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(coast);  // Sets my_motor's stopping mode to coast.
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(vex::directionType::fwd);
>  vex::task::sleep(3000);
>  my_motor.stop();
>  
>  my_motor.setPosition(120.0, rotationUnits::deg);  // Sets my_motor's encoder to the value of 120 degrees at the current motor position.
>```

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
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setTimeout(5, vex::timeUnits::sec);  // Sets my_motor's timeout to 5 seconds
>  
>  my_motor.spinFor(vex::directionType::fwd, 1.0, vex::rotationUnits::rev, false);  // Spin for one rotation
>  // If the motor does not finish its spin in 5 seconds, the motor will stop
>  
>```


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
| units | vex::torqueUnits | The measurement unit for the torque value, |
| units | vex::currentUnits | The measurement unit for the torque value. |

**Example** 
>```clike
>  vex::motor my_lift_motor = vex::motor(vex::PORT1);  // Initialize my_lift_motor at port 1
>  my_lift_motor.setMaxTorque(2.5, vex::currentUnits::amp); // Sets my_lift_motor's maximum torque to that calculated by a 2.5 amp current draw
>  
>  my_lift_motor.spinFor(vex::directionType::fwd, 0.75, vex::rotationUnits::rev, false);
>  
>```
______________________________________________________________________________________________________________________________

## <u>Action</u>

### spin
`void spin(directionType dir)` <br>
`void spin(directionType dir, double velocity, velocityUnits units)` <br>
`void spin(directionType dir, double velocity, percentUnits units)`
`void spin(directionType dir, double voltage, voltageUnits units)`

**Description** <br>
Turns on the motor and spins it in a specified direction and a specified velocity (if included).

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| dir | vex::directionType | The direction to spin the motor. |
| velocity | double | Sets the amount of velocity. |
| voltage | double | Sets the amount of volts. |
| units | vex::velocityUnits | The measurement unit for the velocity value. |
| units | [vex::percentUnits](cpp/units?id=percentunits) | The measurement unit for the velocity value. |
| units | vex::voltageUnits | The measurement unit for the voltage value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, vex::velocityUnits::pct); // Sets the default velocity of my_motor to 50%
>  
>  my_motor.spin(vex::directionType::fwd, 100.0, vex::velocityUnits::pct); // Spins my_motor at 100%
>  vex::task::sleep(1000);
>  my_motor.stop();
>  
>  my_motor.spin(vex::directionType::fwd); // Spins my_motor at default velocity of 50%
>```


### spinTo
`bool spinTo(double rotation, rotationUnits units, bool waitForCompletion=true)` <br>
`bool spinTo(double rotation, rotationUnits units, double velocity, velocityUnits units_v, bool waitForCompletion=true)`

**Description** <br>
Turns on the motor and spins it to an absolute target rotation value at a specified velocity (if included). <br>
*Returns* a Boolean that signifies when the motor has reached the target rotation value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| rotation | double | Sets the amount of rotation. |
| units | vex::rotationUnits | The measurement unit for the rotation value. |
| velocity | double | Sets the amount of velocity. |
| units_v | vex::velocityUnits | The measurement unit for the velocity value. |
| waitForCompletion | bool | (optional) If true, your program will wait until the motor reaches the target rotational value. If false, the program will continue after calling this function. By default, this parameter is true. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.spinTo(120.0, vex::rotationUnits::deg, 10.0, vex::velocityUnits::pct, false); // Spins my_motor to the 120 degree position at 10% velocity
>  // . . .
>  // Code continues to run after function call
>```
______________________________________________________________________________________________________________________________
## <u>Sensing</u>
