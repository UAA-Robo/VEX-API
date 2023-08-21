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
>```clike
>  vex::motor left_motor = vex::motor(PORT1);  // Initialize left_motor at port 1
>  vex::motor right_motor = vex::motor(PORT2, true);  // Initialize right_motor at port 2 and sets the reverse flag to true
>```

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
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.setReversed(true);
>```

### setVelocity
`void setVelocity(double velocity, velocityUnits units)`

**Description** <br>
Sets the velocity of the motor based on the parameters set in the command. This command will not run the motor. Any subsequent call that does not contain a specified motor velocity will use this value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| velocity | double | Sets the amount of velocity. |
| units | vex::velocityUnits | The measurement unit for the velocity value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, velocityUnits::pct);  // Sets my_motor's default velocity to 50%
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(directionType::fwd);
>  task::sleep(3000);
>  my_motor.stop();
>```

### setBrake (Legacy)
`void setBrake(vex::brakeType mode)`

**Description** <br>
Sets the stopping mode of the motor by passing a brake mode as a parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| mode | vex::brakeType | The stopping mode can be set to coast, brake, or hold. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(coast);  // Sets my_motor's stopping mode to coast.
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(directionType::fwd);
>  task::sleep(3000);
>  my_motor.stop();  // Watch the robot slide!
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
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(coast);  // Sets my_motor's stopping mode to coast.
>  // Spins motor for 3 seconds
>  my_motor.spin(directionType::fwd);
>  task::sleep(3000);
>  my_motor.stop();  // Watch the robot slide!
>```

### resetPosition(void)
 ```clike
void resetPosition();
```

**Description** <br>
Resets the motor's encoder to the value of zero.

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.spin(directionType::fwd, 50.0, percentUnits::pct); // Spin the motor
>  task::sleep(1000);  // Spin for 1 second
>  my_motor.stop();
>  my_motor.resetPosition();  // Resets my_motor's encoder to the value of zero at the current motor position.
>```

### setPosition(double value, rotationUnits units);
`void setPosition(double value, rotationUnits units);`

**Description** <br>
Sets the value of the motor's encoder to the value specified in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | Sets the current position of the motor. |
| units | vex::rotationUnits | The measurement unit for the position value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1);  // Initialize my_motor at port 1
>  my_motor.setStopping(coast);  // Sets my_motor's stopping mode to coast.
>  
>  // Spins motor for 3 seconds
>  my_motor.spin(directionType::fwd);
>  task::sleep(3000);
>  my_motor.stop();
>  
>  my_motor.setPosition(120.0, rotationUnits::deg);  // Sets my_motor's encoder to the value of 120 degrees at the current motor position.
>```

### setTimeout;
`clike void setTimeout(int32_t time, timeUnits units)`

**Description** <br>
Sets the timeout for the motor. If the motor does not reach its' commanded position prior to the completion of the timeout, the motor will stop.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | Sets the amount of time. |
| units | vex::timeUnits | The measurement unit for the time value. |

**Example** 
>```clike
>  TODO
>```
______________________________________________________________________________________________________________________________

## <u>Action</u>


______________________________________________________________________________________________________________________________
## <u>Sensing</u>
