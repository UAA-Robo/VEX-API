# controller::lcd
Use the Screen instances of the lcd classes within the controller class to get write to the controller screen

`controller.Screen` <br>
________________________________________________________________________________________________________________

### clearLine
`void clearLine()`
`void clearLine(int number)`


**Description** <br>
Clears the line specified by the parameter. Clears current line if no line number is passed.

| Name | Value | Description |
| :--- | :---- | :---------- |
| number | int | The line number to be cleared from 1-3. |

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
my_controller.Screen.print("Hello");  // Print "Hello"
vex::wait(1, vex::sec);  // Wait 1 second
my_controller.Screen.clearLine(1);  // Clears "Hello" on the first line
```
______________________________________________________________________________________________________________________________

### clearScreen
`void clearScreen()`

**Description** <br>
Clears the controller's LCD screen.

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
my_controller.Screen.clearScreen();
```

______________________________________________________________________________________________________________________________

### column
`int32_t column()`

**Description** <br>
An integer that tracks the current cursor position's column, starting at 1.
**Returns** an integer that tracks the current cursor position's column, starting at 1.

**Example** 
```clike
vex::controller my_controller = vex::controller();
my_controller.Screen.setCursor(1,1);
my_controller.Screen.print("Hello");

// Gets the current curser column and increments it
int curser_column = my_controller.Screen.column();
curser_column += 1;

// Sets the cursor to the incremented column so "World!" prints 1 space after "Hello"
my_controller.Screen.setCursor(1, curser_column);
my_controller.Screen.print("World!");
```

______________________________________________________________________________________________________________________________

### newLine
`void newLine()`

**Description** <br>
Moves the cursor to the next line.

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
my_controller.Screen.clearScreen();
my_controller.Screen.setCursor(1,1);  // Set cursor to first row and column
my_controller.Screen.print("Hello");  // Print "Hello" on the first line
my_controller.Screen.newLine();
my_controller.Screen.print("World");  // Print "World" on the next line
```
______________________________________________________________________________________________________________________________
### print
`void print(T value)` <br>
`void print(T value)` <br>
`void print(const char *format, ... )` <br>
`void print(char *format, ... )` <br>

**Description** <br>
Prints a number, string, or Boolean.

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | template | Information to display on the screen. |
| format | (const) char*| A variable list of parameters to insert into format string. |

**Example** 
```clike
vex::controller my_controller = vex::controller();  // Initialize a controller
my_controller.Screen.clearScreen();

int three = 3;
float four = 4.0;

my_controller.Screen.setCursor(1, 1);  // Sets cursor to first row and first column
my_controller.Screen.print("One, two");  // Prints "One, two"

my_controller.Screen.setCursor(2, 1);  // Sets cursor to  next row
my_controller.Screen.print(three);  // Prints "3"

my_controller.Screen.setCursor(3, 1); // Sets cursor to next row
my_controller.Screen.print("one, 2, %d, %.1f", three, four);  // Prints "One, 2, 3, 4.0,"
```

______________________________________________________________________________________________________________________________

### row
`int32_t row()`

**Description** <br>
An integer that tracks the current cursor position's row, starting at 1.
**Returns** an integer that tracks the current cursor position's row, starting at 1.

**Example** 
```clike
vex::controller my_controller = vex::controller();
my_controller.Screen.clearScreen();
my_controller.Screen.setCursor(1,1);
my_controller.Screen.print("Hello");

// Gets the current curser row and increments it
int curser_row = my_controller.Screen.row();
curser_row += 1;

// Sets the cursor to the incremented row so "World!" prints on the next line
my_controller.Screen.setCursor(curser_row, 1);
my_controller.Screen.print("World!");
```
______________________________________________________________________________________________________________________________


### setCursor
`void setCursor(int32_t row, int32_t col)`

**Description** <br>
Sets the cursor to the row and column number set in the parameters.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| row | int | Sets the row number for where the cursor is placed, ranging from 1-3. |
| col | int | Sets the column number for where the cursor is placed, starting at 1. |

**Example** 
```clike
vex::controller my_controller = vex::controller();
my_controller.Screen.clearScreen();
my_controller.Screen.setCursor(2,1); // Sets the cursor 
my_controller.Screen.print("Hello World");  // Prints "Hello World" on the Middle Line
```