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
`void pressed( void (*callback)(void))`

**Description** <br>
Sets the function to be called when the button is pressed.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| callback | function | A reference to a function. |

**Example** 
```clike
vex::controller my_controller = vex::controller();
int times_pressed = 0;

// Prints the number of times button A was pressed since the program started
void print_times_pressed() {    
    my_controller.Screen.setCursor(1,1);
    my_controller.Screen.clearLine();
    times_pressed += 1;
    
    // For example, prints "A pressed 1 time(s)"
    my_controller.Screen.print("A pressed %d time(s)", times_pressed);  
}

int main() {
    // Calls the print_times_pressed function when Button A is pressed
    my_controller.ButtonA.pressed(print_times_pressed);  
}
```
______________________________________________________________________________________________________________________________

### pressing
`bool pressing(void)`

**Description** <br>
Gets the status of a button.
**Returns** a Boolean value based on the pressed states of the button. If the button is pressed it will return true.

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
while(true) {
    if (my_controller.ButtonA.pressing()) {
        my_controller.Screen.clearScreen();
        my_controller.Screen.setCursor(1, 1);
        my_controller.Screen.print("Button A is pressed!");
    }
 }
```
______________________________________________________________________________________________________________________________

### released
`void released(void (*callback)(void))`

**Description** <br>
Sets the function to be called when the button is released.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| callback | function | A reference to a function. |

**Example** 
```clike
vex::controller my_controller = vex::controller();
int times_released = 0;

// Prints the number of times button A was released since the program started
void print_times_released() {    
    my_controller.Screen.setCursor(1,1);
    my_controller.Screen.clearLine();
    times_released += 1;
    
    // For example, prints "A released 1 time(s)"
    my_controller.Screen.print("A released %d time(s)", times_released);  
}

int main() {
    // Calls the print_times_released function when Button A is released
    my_controller.ButtonA.released(print_times_released);  
}
```

