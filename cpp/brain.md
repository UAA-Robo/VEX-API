# brain<br>
Use the brain class to see battery information, SD card information, or write to the Screen. <br>

`vex::brain()`

<b> Example </b> <br>
> ```clike
> vex::brain my_brain = vex::brain();
> ```

______________________________________________________________________________________________________________________________________
## <u>Sensing</u> `

### timer

`vex::timer(timeUnits units)`

**Description** <br>
Gets the value of the timer in the units specified. *Returns* a double that represents the value of the timer. 

**Parameters**

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | vex::timeUnits TODO:link | The unit of time that will be returned. |


**Example** 
> ```clike
> vex::brain my_brain = vex::brain();
> my_brain.timer(vex::timeUnits::sec);  //Gets time in seconds
> ```

<br><br>
______________________________________________________________________________________________________________________________________

## <u>Setting</u> 
### resetTimer
`vex::brain::resetTimer()`

**Description** <br>
Resets the timer to 0. 

**Example** 
>```clike
> vex::brain my_brain = vex::brain();
> my_brain.resetTimer();
>```

<br><br>
### setTimer
`vex::brain::setTimer(double value, timeUnits units)`

**Description** <br>
Sets the timer to a value and time unit. 

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | double | The value that the timer is set to. |
| units | vex::timeUnits TODO:link | The unit of time that will be returned. |

**Example** 
>```clike
>  TestBrain.setTimer(350, sec)
>```
______________________________________________________________________________________________________________________________

## <u>Action</u>

### TODO method name
`TODO full method`


**Description** <br>
TODO description

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| TODO | TODO | TODO |

**Example** 
>```clike
>  TODO example
>```

