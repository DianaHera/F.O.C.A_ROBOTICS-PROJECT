# F.O.C.A_ROBOTICS-PROJECT

<details>
  <summary>Introduction</summary>
The F.O.C.A. Robotics project involves the design and construction of a robot named F.O.C.A. (Fabricat Original cu Aluminiu), inspired by the beloved animated series 'Robotzi' by Creative Monkeys. In the series, F.O.C.A. is a serious and intelligent character who works alongside his friend MO in an experimental laboratory. F.O.C.A. is the hardworking problem-solver, often stepping in to fix the challenges caused by MO's antics.
  
The robot will have two arms and multiple wheels instead of legs. Its eyes will be made up of an RGB LED matrix with an animated display, while its mouth will feature an LCD screen that lights up when it speaks. The robot will talk and interact with its friend, MO It will be able to move around and articulate its arms, being controlled via Bluetooth using a joystick or remote control.

This project is particularly meaningful as it allows me to bring to life a character from a series I enjoyed watching during my childhood. It combines my passion for robotics with a sense of nostalgia, while challenging me to recreate F.O.C.A.’s personality and functionality in a real-world robotic model.
</details>

<details>
  <summary>General Description</summary>
  
  - Description:
  - Block Scheme:
  TBD
</details>

<details>
  <summary>Hardware Design</summary>
  List of components:

  
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



[hardware](https://github.com/DianaHera/F.O.C.A_ROBOTICS-PROJECT/tree/main/hardware)
</details>

<details>
  <summary>Software Design</summary>
  TBD
</details>

<details>
  <summary>Results</summary>
  TBD
</details>

<details>
  <summary>Conclusions</summary>
  TBD
</details>

<details>
  <summary>Resources</summary>
  TBD
</details>
