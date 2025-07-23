# Cloud based voltage monitoring system

Project Overview :-

The Cloud-Based Voltage Monitoring System is an embedded systems project designed to measure DC voltage in real-time and display it both locally and remotely. It reads the voltage from a custom-built 0–30V power supply, displays the measured value on a 16×2 LCD screen, and simultaneously transmits the data to the ThingSpeak Cloud Platform via Wi-Fi using an ESP32 microcontroller. On ThingSpeak, users can monitor and visualize voltage trends through real-time graphs and analytics.


Tools and Technologies Used :-

ESP32, 16*2 LCD with I2C module, ThingSpeak Cloud (for data visualization and remote monitoring), Arduino IDE (for programming), Custom-designed 0–30V, 1A power supply.


How It Works :-

Power Supply Design:- A 0–30V variable DC power supply was built using standard electronics components. The output voltage can be adjusted via a variable potentiometer.

Voltage Measurement:- The ESP32’s ADC (Analog-to-Digital Converter) reads analog voltage samples from the power supply. The ESP32 supports 0–3.3V ADC resolution, which is better than ESP8266 (0–1V). A voltage divider circuit can be used to scale down the 0–30V range to match the ESP32 ADC input range.

Local Display:- The measured voltage is converted to actual voltage values using a formula and displayed on a 16×2 LCD connected via the I2C module.

Cloud Transmission:- The ESP32 sends the real-time voltage values to the ThingSpeak cloud via Wi-Fi. The data is then visualized on a live graph, allowing remote monitoring.


Real-World Applications :-

1) Remote Power System Monitoring:
Monitor the output of power supplies, solar panels, or batteries in remote or hazardous environments.

2) Industrial Equipment Voltage Tracking:
Used in manufacturing plants to ensure stable operation of voltage-sensitive machines.

3) Educational Demonstrations:
Excellent for demonstrating ADC, IoT, and cloud integration concepts in electronics or embedded systems courses.

4) Lab Bench Power Supply Enhancement:
Add cloud capabilities to traditional lab power supplies for logging and long-term monitoring.


Limitation – ADC Non-linearity :-

While testing the system, one observed limitation is due to the non-linear characteristics of the ESP32 ADC (Analog-to-Digital Converter). Specifically, when measuring higher voltages through the voltage divider  the ESP32 ADC often reports a lower value than actual value.
