# controller::axis
Use the instances of the axis class within the controller class to get input from the axis.

`controller.Axis1` <br>
`controller.Axis2` <br>
`controller.Axis3` <br>
`controller.Axis4` <br>
______________________________________________________________________________________________________________________________

### changed
`changed(void (*callback)(void))`

**Description** <br>
Sets the function to be called when the joystick axis value changes.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| callback | function | A reference to a function. |

**Example** 
```clike
  TODO example
```

______________________________________________________________________________________________________________________________

### value
`int32_t  value(void)`

**Description** <br>
Gets the value of the joystick axis on a scale from -127 to 127.
**Returns** an integer that represents the value of the joystick axis.

**Example** 
```clike
TODO
```

______________________________________________________________________________________________________________________________

### released
`int32_t position(percentUnits units = percentUnits::pct)`


**Description** <br>
Gets the position of the joystick axis on a scale from -100 to 100.
**Returns** an integer that represents the position of the joystick axis as defined by the unit in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [percentUnits::pct](cpp/units?id=percentunits) | (Optional) The type of unit that will be returned. By default, this parameter is a percentage. |

**Example** 
```clike
TODO example
```