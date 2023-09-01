# VEX Custom Units
Many VEX API functions take custom units as an argument. These are defined as follows.

______________________________________________________________________________________________________________________________

## <u>Hardware-related Units</u>

### percentUnits

The measurement units for percentage values.


| Enum | Description |
| :--- | :---------- |
| vex::percentUnits::pct | A percentage unit that represents a value from 0% to 100% |


### timeUnits

The measurement units for time values.


| Enum | Description |
| :--- | :---------- |
| vex::timeUnits::sec | A time unit that is measured in seconds. |
| vex::timeUnits::msec | A time unit that is measured in milliseconds. |


### currentUnits

The measurement units for current values.


| Enum | Description |
| :--- | :---------- |
| vex::currentUnits::amp | A current unit that is measured in amps. |


### voltageUnits

The measurement units for voltage values.


| Enum | Description |
| :--- | :---------- |
| vex::voltageUnits::volt | A voltage unit that is measured in volts. |
| vex::voltageUnits::mV | The measurement units for power values millivolts. |


### powerUnits

The measurement units for power values.


| Enum | Description |
| :--- | :---------- |
| vex::powerUnits::watt | A power unit that is measured in watts. |


### torqueUnits

The measurement units for torque values.


| Enum | Description |
| :--- | :---------- |
| vex::torqueUnits::Nm | A torque unit that is measured in Newton Meters. |
| vex::torqueUnits::InLb | A torque unit that is measured in Inch Pounds. |


### rotationUnits

The measurement units for rotation values.


| Enum | Description |
| :--- | :---------- |
| vex::rotationUnits::deg | A rotation unit that is measured in degrees. |
| vex::rotationUnits::rev | A rotation unit that is measured in revolutions. |
| vex::rotationUnits::raw | A rotation unit that is measured in raw data form. |


### velocityUnits

The measurement units for velocity values.


| Enum | Description |
| :--- | :---------- |
| vex::velocityUnits::pct | A velocity unit that is measured in percentage. (Identical to `(int)vex::percentUnits::pct`) |
| vex::velocityUnits::rpm | A velocity unit that is measured in rotations per minute. |
| vex::velocityUnits::dps | A velocity unit that is measured in degrees per second. |


### distanceUnits

The measurement units for distance values.


| Enum | Description |
| :--- | :---------- |
| vex::distanceUnits::mm | A distance unit that is measured in millimeters. |
| vex::distanceUnits::in | A distance unit that is measured in inches. |
| vex::distanceUnits::cm | A distance unit that is measured in centimeters. |


### analogUnits

The measurement units for analog values.


| Enum | Description |
| :--- | :---------- |
| vex::analogUnits::pct | An analog unit that is measured in percentage. (Identical to `(int)vex::percentageUnits::pct`) |
| vex::analogUnits::range8bit | An analog unit that is measured in an 8-bit analog value (a value with 256 possible states). |
| vex::analogUnits::range10bit | An analog unit that is measured in a 10-bit analog value (a value with 1024 possible states). |
| vex::analogUnits::range12bit | An analog unit that is measured in a 12-bit analog value (a value with 4096 possible states). |
| vex::analogUnits::mV | An analog unit that is measured in millivolts. |


### temperatureUnits

The measurement units for temperature values.


| Enum | Description |
| :--- | :---------- |
| vex::temperatureUnits::celsius | A temperature unit that is measured in celsius. |
| vex::temperatureUnits::fahrenheit | A temperature unit that is measured in fahrenheit. |

______________________________________________________________________________________________________________________________

## <u>Motor-related Units</u>

### directionType

The defined units for direction values.


| Enum | Description |
| :--- | :---------- |
| vex::directionType::fwd | A direction unit that is defined as forward. |
| vex::directionType::rev | A direction unit that is defined as backward. |
| vex::directionType::undefined | |


### turnType

The defined units for turn values.


| Enum | Description |
| :--- | :---------- |
| vex::turnType::left | A turn unit that is defined as left turning. |
| vex::turnType::right | A turn unit that is defined as right turning. |


### brakeType

The defined units for brake values.


| Enum | Description |
| :--- | :---------- |
| vex::brakeType::coast | A brake unit that is defined as coast. |
| vex::brakeType::brake | A brake unit that is defined as brake. |
| vex::brakeType::hold | A brake unit that is defined as hold. |
| vex::brakeType::undefined | |


### gearSetting

The defined units for gear values.


| Enum | Description |
| :--- | :---------- |
| vex::gearSetting::ratio36_1 | A gear unit that is defined as the red 36:1 gear cartridge used in V5 Smart Motors. |
| vex::gearSetting::ratio18_1 | A gear unit that is defined as the green 18:1 gear cartridge used in V5 Smart Motors. |
| vex::gearSetting::ratio6_1 | A gear unit that is defined as the blue 6:1 gear cartridge used in V5 Smart Motors. |


______________________________________________________________________________________________________________________________

## <u>Brain/LCD-related Units</u>

### fontType

The defined units for font values.


| Enum | Description |
| :--- | :---------- |
| vex::fontType::mono20 | A font unit that is defined as mono20. |
| vex::fontType::mono30 | A font unit that is defined as mono30. |
| vex::fontType::mono40 | A font unit that is defined as mono40. |
| vex::fontType::mono60 | A font unit that is defined as mono60. |
| vex::fontType::prop20 | A font unit that is defined as prop20. |
| vex::fontType::prop30 | A font unit that is defined as prop30. |
| vex::fontType::prop40 | A font unit that is defined as prop40. |
| vex::fontType::prop60 | A font unit that is defined as prop60. |
| vex::fontType::mono15 | A font unit that is defined as mono15. (Not in spec) |
| vex::fontType::mono12 | A font unit that is defined as mono12. (Not in spec) |
| vex::fontType::cjk16 | A font unit that is defined as cjk16. (Not in spec) |


### triportType

The defined units for triport devices.


| Enum | Description |
| :--- | :---------- |
| vex::triportType::analogInput | A triport unit that is defined as an analog input. |
| vex::triportType::analogOutput | A triport unit that is defined as an analog output. |
| vex::triportType::digitalInput | A triport unit that is defined as a digital input. |
| vex::triportType::digitalOutput | A triport unit that is defined as a digital output. |
| vex::triportType::button | A triport unit that is defined as a button. |
| vex::triportType::potentiometer | A triport unit that is defined as a potentiometer. |
| vex::triportType::lineSensor | A triport unit that is defined as a line sensor. |
| vex::triportType::lightSensor | A triport unit that is defined as a light sensor. |
| vex::triportType::gyro | A triport unit that is defined as a gyro. |
| vex::triportType::accelerometer | A triport unit that is defined as an accelerometer. |
| vex::triportType::motor | A triport unit that is defined as a motor. |
| vex::triportType::servo | A triport unit that is defined as a servo. |
| vex::triportType::quadEncoder | A triport unit that is defined as a quadrature encoder. |
| vex::triportType::sonar | A triport unit that is defined as a sonar. |
| vex::triportType::motors | A triport unit that is defined as a motor with slew rate control. |


### controllerType

The defined units for controller devices.


| Enum | Description |
| :--- | :---------- |
| vex::controllerType::primary | A controller unit defined as a primary controller. |
| vex::controllerType::partner | A controller unit defined as a partner controller. |


### axisType

The defined units for inertial sensor axis.


| Enum | Description |
| :--- | :---------- |
| vex::axisType::xaxis | TODO |
| vex::axisType::yaxis | TODO |
| vex::axisType::zaxis | TODO |


### orientationType

The defined units for inertial sensor orientation.


| Enum | Description |
| :--- | :---------- |
| vex::orientationType::roll | TODO |
| vex::orientationType::pitch | TODO |
| vex::orientationType::yaw | TODO |


### sizeType

The defined units for distance sensor object size.


| Enum | Description |
| :--- | :---------- |
| vex::sizeType::none | TODO |
| vex::sizeType::small | TODO |
| vex::sizeType::medium | TODO |
| vex::sizeType::large | TODO |


### ledState

The defined units for optical sensor led state.


| Enum | Description |
| :--- | :---------- |
| vex::ledState::off | TODO |
| vex::ledState::on | TODO |


### gestureType

The defined units for optical sensor gesture types.


| Enum | Description |
| :--- | :---------- |
| vex::gestureType::none | TODO |
| vex::gestureType::up | TODO |
| vex::gestureType::down | TODO |
| vex::gestureType::left | TODO |
| vex::gestureType::right | TODO |


### linkType

The defined units for vexlink types.


| Enum | Description |
| :--- | :---------- |
| vex::linkType::undefined | |
| vex::linkType::manager | A vexlink type that is defined as the manager radio. |
| vex::linkType::worker | A vexlink type that is defined as the worker radio. |
| vex::linkType::raw | A vexlink type that is defined as a raw unmanaged link. |


## Controller-related types

### button (child class of controller)
The defined buttons for use on the VEX V5 Controller

| Class | Description |
| :--- | :---------- |
| ButtonL1 | |
| vex::linkType::manager | A vexlink type that is defined as the manager radio. |
| vex::linkType::worker | A vexlink type that is defined as the worker radio. |
| vex::linkType::raw | A vexlink type that is defined as a raw unmanaged link. |