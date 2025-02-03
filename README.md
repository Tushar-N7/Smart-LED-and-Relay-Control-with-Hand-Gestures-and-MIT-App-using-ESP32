This project, **Smart LED and Relay Control with Hand Gestures and MIT App using ESP32**, allows users to control RGB LEDs and a relay using hand gestures and a web interface. The system uses the ESP32 microcontroller, a hand gesture recognition model using Python (with OpenCV and MediaPipe), and MIT App Inventor for remote control.

### Project Overview
The goal of the project is to remotely control two RGB LEDs and a relay connected to an ESP32 via a web server or through hand gestures recognized by the camera. The hand gestures (thumb + index finger, thumb + middle finger, and thumb + ring finger) are used to control the color of the second LED (Red, Blue, and Green respectively). Additionally, the relay can be controlled remotely from the MIT App or via a simple web interface.

### Components Used
1. **ESP32** - A powerful microcontroller with built-in Wi-Fi capabilities.
2. **RGB LEDs** - Two RGB LEDs for visual output control.
3. **Relay Module** - A relay to control external devices (e.g., a fan, lamp, etc.).
4. **WebServer Library** - Allows ESP32 to host a simple web server to control devices.
5. **Python (OpenCV and MediaPipe)** - Used for hand gesture recognition and interaction with the ESP32 for controlling LEDs.
6. **MIT App Inventor** - Used to create a mobile app that communicates with the ESP32.

### Key Features
- **Hand Gesture Control**: Using MediaPipe, the system detects specific hand gestures and maps them to control LED colors.
  - **Thumb + Index Finger**: LED turns red.
  - **Thumb + Middle Finger**: LED turns blue.
  - **Thumb + Ring Finger**: LED turns green.
- **ESP32 Web Server**: The ESP32 serves a simple web page to control both RGB LEDs and a relay via HTTP requests.
- **MIT App Integration**: The MIT App allows the user to control the relay and LEDs from their smartphone, enhancing the project’s usability.

### Hardware Setup
1. **ESP32 Pins**:
   - **LED 1**: Connected to pins 23, 22, and 21 for red, green, and blue colors.
   - **LED 2**: Connected to pins 19, 18, and 15 for red, green, and blue colors.
   - **Relay**: Controlled by pin 27.

2. **Relay Module**: Used to control other devices (e.g., home appliances).

### Software Overview
1. **ESP32 Code**:
   - The ESP32 runs a web server that listens for HTTP requests to change LED colors or control the relay state (ON/OFF).
   - Web server routes:
     - **/led1**: Controls the first RGB LED.
     - **/led2**: Controls the second RGB LED.
     - **/relay**: Controls the relay ON/OFF state.
  
2. **Python Code**:
   - A hand gesture is detected using MediaPipe and OpenCV, and based on the gesture, an HTTP request is sent to the ESP32 to control the second RGB LED.
  
3. **MIT App**:
   - The MIT App sends HTTP requests to the ESP32 to control the relay and the LEDs. It uses a simple UI with buttons to turn the relay on/off and change the LED colors.

### Project Setup
1. **ESP32 Setup**:
   - Connect the ESP32 to your Wi-Fi network.
   - Upload the ESP32 code to the microcontroller.
   - Ensure that the ESP32’s IP address is accessible via the browser or MIT App.

2. **Python Setup**:
   - Install OpenCV and MediaPipe libraries.
   - Connect the camera to the computer.
   - Run the Python code to start gesture detection and control the ESP32 LEDs.

3. **MIT App Setup**:
   - Design a basic app with buttons for controlling the relay and LEDs.
   - The app should communicate with the ESP32 via HTTP to control devices.

### How to Control
1. **Web Interface**:
   - Open a web browser and access the ESP32’s IP address.
   - Use the following URL structure to control devices:
     - **Turn LED 1 on/off**: `/led1?red=255&green=0&blue=0`
     - **Turn LED 2 on/off**: `/led2?red=0&green=0&blue=255`
     - **Turn Relay on/off**: `/relay?state=ON` or `/relay?state=OFF`

2. **Hand Gesture**:
   - Use the webcam to show hand gestures in front of the camera.
   - Based on the gesture, the corresponding LED will change color:
     - **Thumb and Index Finger** = Red
     - **Thumb and Middle Finger** = Blue
     - **Thumb and Ring Finger** = Green

3. **MIT App**:
   - Press the buttons in the app to control the relay and RGB LEDs from the mobile device.

### Code Structure
1. **ESP32 Code**:
   - Setup Wi-Fi and Web Server.
   - Define control routes for LEDs and relay.
   - Handle HTTP requests to control the devices.

2. **Python Code**:
   - Initialize hand gesture recognition.
   - Detect hand gestures and send HTTP requests to ESP32 to control LED colors.

3. **MIT App**:
   - Design buttons for controlling LEDs and relay.
   - Set up HTTP requests to communicate with ESP32.

### GitHub Repository Structure
```
Smart-LED-and-Relay-Control-with-Hand-Gestures-and-MIT-App-using-ESP32/
│
├── ESP32_Code/
│   ├── main.ino
│   └── README.md
│
├── Python_Code/
│   ├── gesture_control.py
│   └── README.md
│
├── MIT_App/
│   ├── MIT_App_Design.aia
│   └── README.md
│
└── README.md
```

### Installation Instructions
1. Clone the repository to your local machine.
2. Follow the instructions in the **ESP32_Code/README.md** file to upload the code to the ESP32.
3. Set up your camera and install required libraries for Python as described in the **Python_Code/README.md** file.
4. Import the MIT App Inventor project from the **MIT_App/** folder and compile the app.

This project provides a practical solution for controlling home automation devices using simple hand gestures and smartphone control, making it a fun and interactive IoT project.
