# controller::axis
Use the instances of the axis class within the controller class to get input from the axis.

`controller.Axis1` (Horizontal Right Joystick) <br> 
`controller.Axis2` (Vertical Right Joystick) <br>
`controller.Axis3` (Vertical Left Joystick)  <br>
`controller.Axis4` (Horizontal Left Joystick) <br>
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
// Prints the number of times Axis 1 was released since the program started
void print_times_changed() {    
    my_controller.Screen.setCursor(1,1);
    my_controller.Screen.clearLine();
    times_changed += 1;
    
    // For example, prints "Axis1: 1 time(s)"
    my_controller.Screen.print("Axis1: %d time(s)", times_changed);  
}

int main() {
    // Calls the print_times_changed function when Axis 1 (right joystick) is changed horizontally
    my_controller.Axis1.changed(print_times_changed);  
}
```
______________________________________________________________________________________________________________________________

### position
`int32_t position(percentUnits units = percentUnits::pct)`

**Description** <br>
Gets the position of the joystick axis on a scale from -100 to 100.
**Returns** an integer that represents the position of the joystick axis as defined by the unit in the parameter.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| units | [vex::percentUnits](cpp/units?id=percentunits) | (Optional) The type of unit that will be returned. By default, this parameter is a percentage. |

**Example** 
```clike
  vex::controller my_controller = vex::controller();
  float position;

  // Continuously and prints Axis 1's position to the controller as a percent
  while (true) {
      position = my_controller.Axis1.position(vex::percentUnits::pct); 
      my_controller.Screen.setCursor(1,1);
      my_controller.Screen.clearLine();

      // For example, prints "Axis1: 20.00%"
      my_controller.Screen.print("Axis1: %.2f%", position);
  }
```
______________________________________________________________________________________________________________________________

### value
`int32_t  value(void)`

**Description** <br>
Gets the value of the joystick axis on a scale from -127 to 127.
**Returns** an integer that represents the value of the joystick axis.

**Example** 
```clike
vex::controller my_controller = vex::controller();
int position;

// Continuously and prints Axis 1's raw position to the controller 
while (true) {
    position = my_controller.Axis1.value(); 
    my_controller.Screen.setCursor(1,1);
    my_controller.Screen.clearLine();

    // For example, prints "Axis1: 127"
    my_controller.Screen.print("Axis1: %d%", position);
}
```

