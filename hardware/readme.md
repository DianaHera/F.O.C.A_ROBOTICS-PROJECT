**Detailed Hardware Functionality Description**

The robot is designed to combine motion, arm articulation, and communication capabilities while being controlled remotely via Bluetooth. Below is a comprehensive breakdown of the hardware components, connections, communication interfaces, and relevant specifications.




**2.Hardware Interconnections**
| **Component**               | **Pin**         | **ESP32 Pin / Other**       |
|-----------------------------|-----------------|-----------------------------|
| **LED Matrix Module**       | VCC             | 5V                          |
|                             | GND             | GND                         |
|                             | DIN             | GPIO 23                     |
|                             | CS              | GPIO 5                      |
|                             | CLK             | GPIO 18                     |
| **Micro Servo 1 (SG90)**    | VCC             | Step Down **OUT+**          |
|                             | GND             | GND                         |
|                             | Signal          | GPIO 13                     |
| **Micro Servo 2**           | Signal          | GPIO 12                     |
| **Micro Servo 3**           | Signal          | GPIO 28                     |
| **Micro Servo 4**           | Signal          | GPIO 27                     |
| **PAM8403 Amplifier**       | VCC             | Step Down **OUT+**          |
|                             | GND             | GND                         |
|                             | L-IN / R-IN     | GPIO 25                     |
|                             | Speaker Output  | Speaker terminals           |
| **DC-DC Step Down**         | IN+             | Battery Positive            |
|                             | IN-             | Battery GND                 |
|                             | OUT+            | Servos / PAM8403 / LED Matrix Module VCC        |
|                             | OUT-            | Common GND                  |
| **18650 Batteries**         | Positive        | Step Down **IN+**           |
|                             | Negative        | Step Down **IN-**           |
