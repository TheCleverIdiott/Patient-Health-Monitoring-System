# ESP32 Patient Health Monitoring System

This project is an ESP32-based patient health monitoring system that measures room temperature, room humidity, body temperature, heart rate (BPM), and blood oxygen levels (SpO2). The system sends the data to a web server hosted on the ESP32, making the information accessible through any web browser connected to the same network.

## Features
- Measure and display room temperature and humidity using the DHT11 sensor.
- Measure and display body temperature using the DS18B20 sensor.
- Measure and display heart rate (BPM) and blood oxygen levels (SpO2) using the MAX30100 Pulse Oximeter.
- Host a web server on the ESP32 to display the collected data in a user-friendly web interface.

## Hardware Required
- ESP32 Development Board
- DHT11 Temperature and Humidity Sensor
- DS18B20 Temperature Sensor
- MAX30100 Pulse Oximeter
- Breadboard and Jumper Wires
- 4.7kΩ Resistor (for DS18B20)

## Software Required
- Arduino IDE
- ESP32 Board Manager (installed via Arduino IDE)
- Required Libraries:
  - `WiFi.h`
  - `WebServer.h`
  - `Wire.h`
  - `MAX30100_PulseOximeter.h`
  - `OneWire.h`
  - `DallasTemperature.h`
  - `Bonezegei_DHT11.h`

## Circuit Diagram
Connect the sensors to the ESP32 as follows:

| Component            | ESP32 Pin      |
|----------------------|----------------|
| DHT11                | 18             |
| DS18B20              | 5              |
| MAX30100 Pulse Oximeter | I2C (SDA, SCL)|
| 4.7kΩ Resistor       | Between DS18B20 Data and 3.3V |

## Installation and Setup

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/ESP32-Patient-Health-Monitoring.git
   cd ESP32-Patient-Health-Monitoring
   ```

2. **Open the Arduino IDE:**
   - Install the ESP32 Board Manager.
   - Install the required libraries mentioned above.

3. **Update Wi-Fi Credentials:**
   - Open the `ESP32-Patient-Health-Monitoring.ino` file.
   - Update the `ssid` and `password` variables with your Wi-Fi network credentials.

4. **Upload the Code to ESP32:**
   - Connect your ESP32 board to your computer.
   - Select the correct board and port from the Arduino IDE.
   - Click on the upload button.

5. **Open the Serial Monitor:**
   - Set the baud rate to 115200.
   - Observe the connection status and IP address assigned to your ESP32.

6. **Access the Web Server:**
   - Open a web browser and enter the IP address displayed on the Serial Monitor.
   - View the real-time patient health monitoring data.

## Code Explanation

The code consists of the following main parts:

- **Library Inclusions and Definitions:**
  - Include necessary libraries for Wi-Fi, web server, and sensors.
  - Define sensor pins and variables to store sensor data.

- **Setup Function:**
  - Initialize serial communication and sensor objects.
  - Connect to Wi-Fi and start the web server.
  - Initialize the pulse oximeter sensor.

- **Loop Function:**
  - Handle client requests and update sensor readings.
  - Read data from sensors and periodically report it to the Serial Monitor.
  - Serve the HTML page with sensor data when a client connects.

- **HTML Page Generation:**
  - Generate an HTML page with embedded sensor data to be displayed in a web browser.

## Contributions

Feel free to fork this repository and contribute by submitting a pull request. Any improvements, bug fixes, or enhancements are welcome.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- This project is inspired by various open-source health monitoring systems and tutorials available online.
- Special thanks to the authors of the libraries used in this project.


For any questions or suggestions, please open an issue or contact [Aritra](https://github.com/TheCleverIdiott).

