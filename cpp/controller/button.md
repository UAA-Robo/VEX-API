# controller::button
Use the instances of the button class within the controller class to get input from the buttons.

`controller.ButtonL1` <br>
`controller.ButtonL2` <br>
`controller.ButtonR1` <br>
`controller.ButtonR2` <br>
`controller.ButtonUp` <br>
`controller.ButtonDown` <br>
`controller.ButtonLeft` <br>
`controller.ButtonRight` <br>
`controller.ButtonX` <br>
`controller.ButtonB` <br>
`controller.ButtonY` <br>
`controller.ButtonRight` <br>

______________________________________________________________________________________________________________________________

### pressed
`void pressed( void (*callback)(void)) const;`

**Description** <br>
Sets the function to be called when the button is pressed.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| callback | function | A reference to a function. |

**Example** 
```clike
  TODO example
```
______________________________________________________________________________________________________________________________

### released
`void released(void (*callback)(void)) const;`

**Description** <br>
Sets the function to be called when the button is released.


**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| callback | function | A reference to a function. |

**Example** 
```clike
TODO example
```
______________________________________________________________________________________________________________________________

### pressing
`bool pressing(void) const;`

**Description** <br>
Gets the status of a button.
**Returns** a Boolean value based on the pressed states of the button. If the button is pressed it will return true.

**Example** 
```clike
while(true) {
    if (my_controller.ButtonA.pressing()) {
        my_controller.Screen.clearScreen();
        my_controller.Screen.setCursor(1, 1);
        my_controller.Screen.print("Button A is pressed!");
    }
 }
```
