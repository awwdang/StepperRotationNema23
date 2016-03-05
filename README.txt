Requires all files in the directory to run the bipolar stepper motor.

Runs in a continuous rotation as long as the the joystick is tilted.
Angular Position values will be added in the updates.
NEVER remove a coil that belongs to the motor from the AutoDriver board while it is powered up
as the resulting feedback can damage the AutoDriver board's circuit.

BOOT UP:
	Run dPIN_example.ino for start up and upload it to the Arduino board.
	At the bottom of the file, modify the value in dSPIN_Move function to adjust the rotation movement of the stepper.
	The loops prior to each move function handle your input, for initial setup, this relates to the analog joystick
	potentiometer values.
	Call functions in dSPIN_support to augment how the stepper motor will rotate.

POWER REQUIREMENTS:
	This system requires 12V at 2.8A to power the motor. The motor is still operational at lower ratings without load.
	Personal Limit tests currently has the motor powered at 24V and 30V at 2.8A.
	9V battery/Serial Cable from computer to power the Arduino board, LiPo Battery (I used a Multistar 14.8V @ 8000mAh)

NEMA 23 - 76:1 GEARBOX ATTACHMENT
	This powerful bipolar stepper with a rear shaft and a planetary gearbox has a 0.023° step angle and 
	240 kg·cm of torque at low speeds. Since the motor is attached to a 76:1 gearbox, it is expected to rotate
	at low speeds, which high amounts of torque. Removal of the gearbox can be done and you can expect to see higher
	RPM. 
	Additonal specifications for the motor can be found at http://www.phidgets.com/products.php?product_id=3334_0
	http://www.robotshop.com/en/12v-28a-3333-oz-in-nema-23-bipolar-stepper-motor.html
	http://www.robotshop.com/media/files/pdf/datasheet-3334.pdf


MANUAL CONTROL:
	Control of this bipolar stepper motor is through a joystick input for testing purposes. Additional control can
	be done through a Taranis Controller after modifying the code to support PinChange.h interrupts.

L6470 AUTODRIVER
	Original Github Repository: https://github.com/sparkfun/SparkFun_AutoDriver_Arduino_Library
	This board supports 8V - 45V and upto 3A. This board can be attached to another L6470 AUTODRIVER
	to synch control with another bipolar stepper motor.
	The L6470 circuit will heat up and a heatsink is required for safe operation.
	The Autodriver has built in overcurrent detection, undervoltage detection, overtemperature detection,
	stall detection.
	Beauty about this device is that you don't need to count the steps for your stepper motor to control it's
	position as it is controled over an SPI link. This allows for acceleration and deceleration smooth out
	it's movement.


REQUIREMENTS: 
	NEMA 23: http://www.robotshop.com/en/12v-28a-3333-oz-in-nema-23-bipolar-stepper-motor.html
		Other NEMA 23 with lower gearbox ratios can also be used, as well as other Bipolar Stepper Motors
	Arduino: https://www.sparkfun.com/products/11021
	Joystick: https://www.sparkfun.com/products/9032 with breakout board https://www.sparkfun.com/products/9110
	Stepper Motor Driver: https://www.sparkfun.com/products/11611
	LiPo Battery: http://www.hobbyking.com/hobbyking/store/__64436__Multistar_High_Capacity_4S_8000mAh_Multi_Rotor_Lipo_Pack_US_Warehouse_.html 
		other batteries that provide sufficient power can be utilized as well
	L6470 AutoDriver Board:	https://www.sparkfun.com/products/11611

Alternate sites for purchase can be made from http://www.aliexpress.com/ as they are cheaper in cost but
have longer shipping times. Sparkfun has faster shipping and all online documentation can be retrieved
from the product page.
