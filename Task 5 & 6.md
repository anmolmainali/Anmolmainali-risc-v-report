# AUTOMATED MOTION DETECTING SYSTEM USING VSDSquadron-mini

# INTRODUCTION
* An Automatic motion detecting System or a automatic light system is a smart lighting solution that automatically turns a light on or off based on certain conditions, such as ambient light levels or motion detection. The system eliminates the need for manual switching, providing convenience and energy efficiency.

# Components used:
* VSDSquadron Mini Board-1
* PIR Sensor-1
* LED-1
* USB Cable-1
* Jumper Wires-5

# Working & Applications:

   * WORKING:
* The PIR sensor is strategically placed in a location where it can detect the movement of individuals within its sensing range.
* The PIR sensor continuously monitors its surroundings for any changes in infrared radiation caused by the movement of individuals.
* When someone enters the detection range of the IR sensor, it detects the change in radiation and triggers an output signal.
* When the IR sensor detects motion, it sends a signal to the microcontroller which then activates the LED lighting system. The LED lights up, providing illumination and the led will blink 3 or more times (depending upon the user how many blinks he wants to give)in the area where motion is detected which gives indication of motion detected.

  * APPLICATIONS:
* Security Lighting : These systems can be used for security lighting in outdoor spaces, such as gardens, driveways, and pathways, to deter intruders and provide visibility at night.
* Home Automation : Automatic light systems can be installed in homes, particularly in areas such as hallways, staircases, and bathrooms, where lights need to be turned on/off based on occupancy.
* Energy Efficiency : Automatic light systems contribute to energy conservation by ensuring that lights are not left on unnecessarily when the area is unoccupied.
* Accessibility : These systems can improve accessibility for individuals with disabilities by providing automatic illumination in response to their movement.
 
  # C CODE USED:
```
#include <ch32v00x.h>
#include <debug.h>

const int IR_SENSOR_PIN = PD4;  // IR sensor connected to PD4
const int LED_PIN = PD6;        // LED connected to PD6

// Constants
const int BLINK_COUNT = 3;      // Number of times to blink(which can be subjected to change)
const int BLINK_ON_TIME = 200;  // LED on time in milliseconds
const int BLINK_OFF_TIME = 100; // LED off time in milliseconds

void setup() {
  // Configure pins
  pinMode(IR_SENSOR_PIN, INPUT_PULLUP);  // IR sensor pin as input with pull-up
  pinMode(LED_PIN, OUTPUT);              // LED pin as output
}

void blinkLED(int times) {
  for(int i = 0; i < times; i++) {
    digitalWrite(LED_PIN, HIGH);
    delay(BLINK_ON_TIME);
    digitalWrite(LED_PIN, LOW);
    delay(BLINK_OFF_TIME);
  }
}

void loop() {
  // Read IR sensor state
  if (digitalRead(IR_SENSOR_PIN) == HIGH) {
    // Motion detected - blink LED
    blinkLED(BLINK_COUNT);
  }
}
```
# CIRCUIT DIAGRAM:
![Screenshot 2025-02-15 103727](https://github.com/user-attachments/assets/02880866-058e-4825-91c9-eeca0d07fe66)
# CONCLUSION:
The Automated Light System project was successfully implemented using the VSDSquadron Mini chip. The system efficiently detects ambient light levels using an LDR sensor and automatically controls a light source based on real-time conditions. This reduces energy consumption and eliminates the need for manual switching. The project demonstrates the practical application of embedded systems and sensor-based automation, making it suitable for home automation, street lighting, and smart buildings.

Through this project, I gained hands-on experience in hardware interfacing, GPIO control, ADC reading, and embedded C programming. The system performed as expected, accurately responding to changes in light intensity. Overall, the project was a success and provided valuable insights into microcontroller-based automation.

# Personal experience:
Working on this project was a great learning experience, as it helped me understand the integration of hardware components and software logic to create a functional system. I learned how to interface sensors, use GPIOs for output control, and apply analog-to-digital conversion (ADC) for real-world sensing. Troubleshooting circuit issues and refining the code improved my problem-solving skills.

One of the biggest challenges was calibrating the LDR sensor to detect optimal light levels, but with testing and adjustments, I was able to achieve reliable performance. This project has enhanced my confidence in embedded systems development and has inspired me to explore more IoT-based automation projects in the future.I kept it a bit simple not trying to complicate it much but I would like to improve my skills more in the days to come.

I would  like to thank my teachers,instructor,and people who helped me during this entire program.
# VIDEO:



https://github.com/user-attachments/assets/0217a273-c351-4ff9-aec2-f23e96b5be83




# END OF STATEMENT






