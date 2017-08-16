# DADB_Flywheel_77D
Brief:
  This code utilizes two displacement sensors (X and Y axis) to measure where the rotor is, then regulates the active magnetic bearings to correct the position.

Basic Operation:
  This setup utilizes four coils to provide both a positive and negative stabilization force in the x and y axis. If the sensors detects an offset, the coils will be activated to stabilize to a target position.

Pinouts:
  Current Sensors
  	-> Pin 09 (ADCA CH0) For H-Bridge 1 Coil 1
  	-> Pin 11 (ADCA CH1) For H-Bridge 2 Coil 2
  	-> Pin 15 (ADCA CH2) For H-Bridge 3 Coil 3
  	-> Pin 17 (ADCA CH3) For H-Bridge 4 Coil 4
  Displacement Sensor
  	-> Pin 12 (ADCB CH0)
  	-> Pin 14 (ADCB CH1)
  PWM High
  	-> Pin 86 (GPIO 34) For H-Bridge 1 Coil 1
  	-> Pin 88 (GPIO 39) For H-Bridge 2 Coil 2
  	-> Pin 90 (GPIO 44) For H-Bridge 3 Coil 3
  	-> Pin 92 (GPIO 45) For H-Bridge 4 Coil 4
  PWM Low and Dir should be pluged into one of the 3.3V pins on the board to keep them at 	logic high. This garentees that when the PWM High pin is toggled the 

Reference Pins:
  ADCA Clock Signal -> Pin 49 (ePWM1 Compair A)
  ADCB Clock Signal -> Pin 53 (ePWM2 Compair A)

Ussage:
  After the board is plugged in one should be able to debug the code. Both X and Y have individual PID loops that can be tuned. Each coil has a set bias current that can be changed. Each coil also has variable x/y sensor influences. This allows for moving the sensors without having to rewire or rewrite code.

Considerations:
  Very basic setup, only proportial constants and only a set bias current. When this is properly PID tuned it should be rediculously strong.
  