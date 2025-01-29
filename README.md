## Arduino-Button-Send-Signal
![image](https://github.com/user-attachments/assets/811c278d-93e1-401d-9315-c6b227d0a63a)

### Arduino
1. Variable Declaration
   - `const int buttonPin = 12;`: This line defines a constant integer `buttonPin` that represents the digital pin number (12) to which the button is connected.
   - `int buttonState = 0;`: This variable will hold the current state of the button (pressed or not pressed).
2. Setup Function
   -  `pinMode(buttonPin, INPUT);`: This sets the button pin as an input. When the button is not pressed, the pin reads HIGH due to the pull-up resistor, and when pressed, it reads LOW.
   -  `Serial.begin(9600);`: This initializes serial communication at a baud rate of 9600 bits per second.
3. Loop Function
   -  `buttonState = digitalRead(buttonPin);`: This reads the current state of the button pin. It will return HIGH if the button is not pressed (due to the pull-up resistor) and LOW if it is pressed.
   -  The `if` statement checks the button state:
     -  If `buttonState` is HIGH, it sends "1" over the serial connection, indicating the button is pressed.
     -  If `buttonState` is LOW, it sends "0", indicating the button is not pressed.

### Python
1. Imports
   - `import serial`: Imports the pyserial library, which allows for serial communication in Python.
   - `import time`: Imports the time module for time-related functions.
2. Serial Connection Setup
   - `arduino_port = "COM5"`: Specifies the serial port to which the Arduino is connected.
   - `baud_rate = 9600`: Sets the baud rate to match the Arduino's serial communication speed.
   - `ser = serial.Serial(arduino_port, baud_rate)`: Establishes a serial connection to the specified port at the defined baud rate.
   - `time.sleep(2)`: Waits for 2 seconds to allow the connection to initialize properly.
3. Reading Data
   - `print("Connection established. Reading button state...")`: Informs the user that the connection is ready.
   - The `try` block contains an infinite loop (`while True:`) that continuously checks for incoming data from the Arduino.
   - `if ser.in_waiting > 0:`: Checks if there is any data waiting to be read from the serial buffer.
   - `data = ser.readline().decode('utf-8').strip()`: Reads a line of data from the serial port, decodes

This code allows a computer to monitor the state of a button connected to an Arduino. When the button is pressed, the Arduino sends a "1" to the computer; when it is not pressed, it sends a "0". The Python script reads this data and prints the corresponding message to the console.
