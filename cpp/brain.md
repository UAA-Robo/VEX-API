# brain<br>

Use the brain class to see battery information, SD card information, or write to the Screen. <br> 
Start by creating an instance of the brain object.

<b> Example </b> <br>
```clike
vex::brain TestBrain
```

______________________________________________________________________________________________________________________________

## <u>Timer</u>

### timer
 ```clike
vex::brain::timer(timeUnits units)
```

**Description** <br>
Gets the value of the timer in the units specified. <br>
Returns a double that represents the value of the timer. 

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | vex::timeUnits TODO:link | The unit of time that will be returned. |

**Example** 
>```clike
>  cout << TestBrain.timer(sec);
>```

<br><br>
### resetTimer
 ```clike
vex::brain::resetTimer()
```

**Description** <br>
Resets the timer to 0. 

**Example** 
>```clike
>  TestBrain.resetTimer()
>```

<br><br>
### setTimer
 ```clike
vex::brain::setTimer(double value, timeUnits units)
```

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
 ```clike
TODO full method
```

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

______________________________________________________________________________________________________________________________
## <u>Sensing</u>

### TODO method name
 ```clike
TODO full method
```

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
