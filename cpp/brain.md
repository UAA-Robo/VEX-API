# brain<br>
Use the brain class to see battery information, SD card information, or write to the Screen. <br>

`vex::brain()`

<b> Example </b> <br>
```clike
vex::brain my_brain = vex::brain();
```

___
### timer

`vex::timer(timeUnits units)`

**Description** <br>
Gets the value of the timer in the units specified. *Returns* a double that represents the value of the timer. 

**Parameters**

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::timeUnits](cpp/units?id=timeunits) | The unit of time that will be returned. |


**Example** 
```clike
vex::brain my_brain = vex::brain();
my_brain.timer(vex::timeUnits::sec);  //Gets time in seconds
```
___

### resetTimer
`vex::brain::resetTimer()`

**Description** <br>
Resets the timer to 0. 

**Example** 
```clike
vex::brain my_brain = vex::brain();
vex::task::sleep(3000);  // Wait for 3 seconds
my_brain.resetTimer();
```
___

### setTimer
`vex::brain::setTimer(double value, timeUnits units)`

**Description** <br>
Sets the timer to a value and time unit. 

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | The value that the timer is set to. |
| units | [vex::timeUnits](cpp/units?id=timeunits) | The unit of time that will be returned. |

**Example** 
```clike
vex::brain my_brain = vex::brain();
vex::task::sleep(3000);  // Wait for 3 seconds
my_brain.setTimer(2, vex::timeUnits::sec);  //Set timer back to 2 seconds
```
___


## TODO: Other methods