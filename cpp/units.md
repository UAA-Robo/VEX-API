# VEX Custom Units
Many VEX API functions take custom units as an argument. These are defined as follows.

______________________________________________________________________________________________________________________________

## <u>Motor-related Units</u>

### percentUnits
`enum class percentUnits`

**Description** <br>
The measurement units for percentage values.

**Options** 

| Enum | Description |
| :--- | :---------- |
| pct | A percentage unit that represents a value from 0% to 100% |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, vex::velocityUnits::pct);  // Sets my_motor's default velocity to 50%
>```

### timeUnits
`enum class timeUnits`

**Description** <br>
The measurement units for time values.

**Options** 

| Enum | Description |
| :--- | :---------- |
| sec | A time unit that is measured in seconds. |
| msec | A time unit that is measured in milliseconds. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setTimeout(5, vex::timeUnits::sec);  // Sets my_motor's timeout to 5 seconds
>  
>  my_motor.spinFor(vex::directionType::fwd, 1.0, vex::rotationUnits::rev, false);  // Spin for one rotation
>  // If the motor does not finish its spin in 5 seconds, the motor will stop
>```
______________________________________________________________________________________________________________________________

## <u>Brain/LCD-related Units</u>

