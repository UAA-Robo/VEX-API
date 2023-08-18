# motor

```clike
vex::motor( int32_t index);
vex::motor( int32_t index, bool reverse);
vex::motor( int32_t index, gearSetting gears);
vex::motor( int32_t index, gearSetting gears, bool reverse);
```
<b> Parameters </b> <br>

| Name | Value | Description |
| :--- | :---- | :---------- |
| TODO | TODO | TODO |

<b> Example </b> <br>
```clike
TODO
```

______________________________________________________________________________________________________________________________

## <u>Setting</u>

### setReversed
 ```clike
void setReversed(bool value);
```

**Description** <br>
Sets the motor mode to "reverse", which will make motor commands spin the motor in the opposite direction.

**Parameters** 

| Name | Value | Description |
| :--- | :---- | :---------- |
| value | bool | If set to true, motor commands spin the motor in the opposite direction. |

**Example** 
>```clike
>  vex::motor my_motor = vex::motor(PORT1); // Initialize my_motor at port 1
>  my_motor.setReversed(true);
>```
______________________________________________________________________________________________________________________________

## <u>Action</u>


______________________________________________________________________________________________________________________________
## <u>Sensing</u>
