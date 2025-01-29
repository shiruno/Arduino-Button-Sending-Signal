## Arduino-Button-Send-Signal
![image](https://github.com/user-attachments/assets/811c278d-93e1-401d-9315-c6b227d0a63a)

#### Arduino
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

#### Python


This code allows a computer to monitor the state of a button connected to an Arduino. When the button is pressed, the Arduino sends a "1" to the computer; when it is not pressed, it sends a "0". The Python script reads this data and prints the corresponding message to the console.
