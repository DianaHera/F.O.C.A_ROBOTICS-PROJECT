**<h2>Detailed Hardware Functionality Description</h2>**

The robot is designed to combine motion, arm articulation, and communication capabilities while being controlled remotely via Bluetooth. Below is a comprehensive breakdown of the hardware components, connections, communication interfaces, and relevant specifications.

**<h2>1. Components and Modules</h2>**

- Microcontroller: ESP32

     - The ESP32 acts as the central processing unit of the robot, managing all peripherals and communication tasks.
     - Features: Dual-core processor, built-in Wi-Fi and Bluetooth 4.2, multiple GPIOs, and PWM capabilities.
- Motors and Motion Components:
   - 2 SG90 Servomotors:
      - Positioned at the shoulders to articulate the robot's arms.
      - Connected via PWM pins to the ESP32 for precise angular control.
   - 2WD Motor Kit (wheels for motion):
      - Enables forward and backward movement of the robot.
      - Motors are controlled using GPIO outputs via an H-Bridge motor driver
- Display Module:
   - 16x2 LCD with I2C Interface:
      - Connected via I2C pins of the ESP32
      - Address: Typically 0x27.
- Bluetooth Communication:
  - Integrated Bluetooth 4.2 on the ESP32 enables remote control of the robot (e.g., from a smartphone or computer).
  - Commands such as forward, backward, and arm movements are sent over Bluetooth and processed by the ESP32.
- Power Management:
  - Power Source: 2S 18650 Lithium-Ion battery pack (7.4V output).
  - DC-DC Step-Down Converter (Mini 360):
  - Regulates the 7.4V battery output down to 5V to supply power to:
      - ESP32
      - Servomotors
      - LCD display.
- Communication with Other Robots:
 
   - Robots communicate wirelessly using the ESP32’s Bluetooth module.
   - Message exchange follows a custom communication protocol, allowing one robot to send commands or status updates to the other.
  
**<h2>2. Hardware Interconnections</h2>**
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
| **LCD Display**             | SDA             | GPIO 21                     |
| **LCD Display**             | SCL             | GPIO 22                     |
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

 - **Communication:**
   - Bluetooth: ESP32 receives control signals (e.g., forward, backward, arm movement) and sends updates to other robots.
   - LCD Display: Displays received operational status.


 **<h2>3. Bill of Components</h2>**
 

| Quantity | Material                                   | Link to shop  										                                                                         | Datasheet     |
|----------|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
|    1| ESP32-WROOM-32D                            | [SHOP LINK](https://www.sigmanortec.ro/placa-dezvoltare-esp32-cu-wifi-si-bluetooth)   										 | [DATASHEET](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32d_esp32-wroom-32u_datasheet_en.pdf) |
|    1     | LED Matrix Module MAX7219                  | [SHOP LINK](https://www.optimusdigital.ro/ro/optoelectronice-matrice-de-led-uri/118-modul-cu-matrice-de-led-uri-max7219.html?search_query=matrice+led&results=51)      | [DATASHEET](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX7219-MAX7221.pdf) |
|    2     | Micro Servomotor SG90 90°                  | [SHOP LINK](https://www.optimusdigital.ro/ro/motoare-servomotoare/26-micro-servomotor-sg90.html?search_query=servomotor&results=116)               			 | [DATASHEET](https://www.friendlywire.com/projects/ne555-servo-safe/SG90-datasheet.pdf) |
|    1     | Speaker (1 W)                              | [SHOP LINK](https://www.optimusdigital.ro/ro/audio-difuzoare/2147-difuzor-de-1-w.html?search_query=difuzor&results=95&HTTP_REFERER=https%3A%2F%2Fwww.optimusdigital.ro%2Fro%2Fcautare%3Fcontroller%3Dsearch%26orderby%3Dposition%26orderway%3Ddesc%26search_query%3Ddifuzor%26submit_search%3D)               															 | [DATASHEET](https://www.farnell.com/datasheets/2827522.pdf) |
|    1     | Miniature Amplifier Module PAM8403(2.2-5 V)| [SHOP LINK](https://www.sigmanortec.ro/modul-amplificator-miniatura-pam8403-22-5v?gad_source=1)               							 | [DATASHEET](https://www.mouser.com/datasheet/2/115/PAM8403-247318.pdf) |
|    1     | DC-DC Step Down Mini-360 Module            | [SHOP LINK](https://www.optimusdigital.ro/ro/surse-coboratoare-reglabile/152-modul-dc-dc-step-down-mini-360.html?search_query=modul+dc-dc+step+down+mini+360&results=1)| [DATASHEET](https://www.matts-electronics.com/wp-content/uploads/2018/06/MINI-360.pdf)|
|    2     | LI-ION Well 18650 battery (3.7V, 2200 mAh) | [SHOP LINK](https://www.dedeman.ro/ro/acumulator-li-ion-well-18650-3-7v-2200-mah/p/1050265)  										 |       X       |
|    1     | PCB board                                  | [SHOP LINK](https://www.sigmanortec.ro/Placa-PCB-prototipare-fata-dubla-7x9cm-p125747328)               								 |       X       |
|    1     | LCD Display I2C                            | [SHOP LINK](https://www.optimusdigital.ro/ro/optoelectronice-lcd-uri/2894-lcd-cu-interfata-i2c-si-backlight-albastru.html?search_query=lcd+i2c&results=17) | [DATASHEET](https://www.makershop.de/download/I2C-LCD-interface.pdf)


**<h2>4. Block Diagram</h2>**

![Captură de ecran 2024-12-18 000626](https://github.com/user-attachments/assets/1a4dcbb4-9ef2-4ca0-85c4-f22e0f116d7d)


**<h2>5. Circuit Diagram</h2>**

![Captură de ecran 2024-12-18 000357](https://github.com/user-attachments/assets/14eeb0a4-47ae-4c8a-b9b2-56eed42f306f)

