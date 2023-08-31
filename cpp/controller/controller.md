# controller
Use the controller class to use the buttons and joysticks, print to the LCD screen, vibrate the controller, and more. Start by creating a controller object.

`controller()` <br>
`controller(controllerType id)`

<b> Parameters </b> <br>

| Name | Value | Description |
| :--- | :---- | :---------- |
| id | [controllerType](cpp/units?id=controllertype) | The type of controller that is being created. This can be set to primary or partner. |

<b> Example </b> <br>
```clike
vex::controller my_primary_controller = vex::controller(vex::controllerType::primary);  // Initialize a primary controller
vex::controller my_secondary_controller = vex::controller(vex::controllerType::partner);  // Initialize a secondary controller
```
______________________________________________________________________________________________________________________________

### rumble
`void rumble(const char *str)`

**Description** <br>
Rumbles the controller by a pattern defined by the parameter. Dots equal short, dashes equal long and space equals pause.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| str | char* |  A string that consists of dots and dashes that represent the rumble pattern. |

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
my_controller.rumble("... -");  // Vibrate the controller 3 short times, then pause, then vibrate the controller 1 long time.
```
______________________________________________________________________________________________________________________________

### installed
`bool installed()`

**Description** <br>
*Returns* true if the controller is linked to the brain. Else returns false. TODO: check this!

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
// If the controller is connected, print "Controller is connected!" to the first line of the controller screen
if (my_controller.installed()) {
    my_controller.Screen.clearScreen();
    my_controller.Screen.setCursor(1, 1);
    my_controller.Screen.print("Controller is connected!");
}
```

