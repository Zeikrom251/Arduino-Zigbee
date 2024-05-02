# Arduino Zigbee Communication

***This Arduino code enables bidirectional communication between two Arduino's boards using Zigbee modules***

## Components Used
- x2 Arduino Uno 
- x2 Zigbee module

## Libraries Used
*None*

## How It Work
**- Setup() :** Initializes two UART serial connections : one on the standard port (UART0) and the other on Serial 1 (UART1), both set at a baud rate of 9600.
Upon startup, it sends the message *Test zigbee* over the standard serial connection to indicate the start of the Zigbee communication testing.

**- Loop() :** The loop() function handles both sending and receiving data via Zigbee in a continuous loop.
  **- Sending :** If data is available on the standard serial connection (Serial), it reads it byte to byte and sends it over the Serial1 connection. Data is stored in an array until a carriage return ('\r') character is received, indicating the end of a message.
  Then, the contents of the array are sent via Serial1, and the array is reset for the next message.

  **- Receiving :** If data is available on the Serial1 connection, it reads it and sends it over the standard serial connection (Serial), allowing for data reception from the other Arduino board.

## Usage
**1.** Upload this code to two separate Arduino boards equipped with Zigbee modules.
**2.** Ensure both Zigbee modules are properly configured.
**3.** Open the serial monitor for each Arduino board to monitor communication.

## Circuit Diagram
![](https://i.ibb.co/cJsPBt3/Zigbee.jpg)

## Note
- Adjust baud rates and other configurations as needed to match your specific hardware setup.
- Ensure proper power supply and connections for reliable communication between the Zigbee modules.

[**Click to watch a demo**](https://youtu.be/P50TZ488H4Q)
