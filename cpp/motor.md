# motor

```clike
vex::motor( int32_t index);
vex::motor( int32_t index, bool reverse);
vex::motor( int32_t index, gearSetting gears);
vex::motor( int32_t index, gearSetting gears, bool reverse);
```
<b> Parameters </b> <br>

| Name | Value | Description |
| :--- | :---- | :---------- |
| index | int32_t | The port index for this motor object. The index is zero-based. |
| reverse | bool | Sets the reverse flag for the new motor object. |
| gears | gearSetting | sets the gear's setting for the new motor object. |

<b> Example </b> <br>
>```clike
>  vex::motor left_motor = vex::motor(PORT1); // Initialize left_motor at port 1
>  vex::motor right_motor = vex::motor(PORT2, true) // Initialize right_motor at port 2 and sets the reverse flag to true
>```

______________________________________________________________________________________________________________________________

## <u>Setting</u>

### setReversed
 ```clike
void setReversed(bool value);
```

**Description** <br>
Sets the motor mode to "reverse", which will make motor commands spin the motor in the opposite direction.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | bool | If set to true, motor commands spin the motor in the opposite direction. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1); // Initialize my_motor at port 1
>  my_motor.setReversed(true);
>```

### setVelocity
 ```clike
void setVelocity(double velocity, velocityUnits units);
```

**Description** <br>
Sets the velocity of the motor based on the parameters set in the command. This command will not run the motor. Any subsequent call that does not contain a specified motor velocity will use this value.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| velocity | double | Sets the amount of velocity. |
| units | vex::velocityUnits | The measurement unit for the velocity value. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1); // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, velocityUnits::pct); // Sets my_motor's default velocity to 50%
>  // Spins motor for 3 seconds
>  my_motor.spin(directionType::fwd);
>  task::sleep(3000);
>  my_motor.stop();
>```
______________________________________________________________________________________________________________________________

## <u>Action</u>


______________________________________________________________________________________________________________________________
## <u>Sensing</u>
