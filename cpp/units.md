# VEX Custom Units
Many VEX API functions take custom units as an argument. These are defined as follows.

______________________________________________________________________________________________________________________________

## <u>Motor Units</u>

### percentUnits
`enum class percentUnits`

**Description** <br>
A percentage unit that represents a value from 0% to 100%
*Returns* enum

**Options** 

| Enum | Value | Description |
| :--- | :---- | :---------- |
| pct | 0 | Renders the value parameter of a given function in terms of a percentage. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(vex::PORT1);  // Initialize my_motor at port 1
>  my_motor.setVelocity(50.0, vex::velocityUnits::pct);  // Sets my_motor's default velocity to 50%
>```
______________________________________________________________________________________________________________________________

## <u>Brain/LCD Units</u>

