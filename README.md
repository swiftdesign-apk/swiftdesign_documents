# swiftdesign
Welcome to the SwiftDesign repository, your go-to tool for creating and managing Android UI designs.

# swiftdesign
learn videos
https://www.youtube.com/@Sswiftdesign0985
# swiftdesign

swiftdesign
Please manually enable 'All File Access' in settings if the app does not run for Android 13 and above.

swiftdesign is an adaptable app for creating and managing custom UIs. Features include web views, PDF handling, image viewing, HTML editing, and serial data transmission via Bluetooth. Customizable buttons and startup options enhance user experience.

swiftdesign offers object-oriented programmable buttons (40 in total) and 10 sliders with serial Bluetooth transmission capabilities. Create and summon custom menus, build and manage PDF libraries, edit HTML files, and turn them into libraries for further use. swiftdesign can send and receive server APIs as well.

Receipts can be displayed in two formats:

Textual

Addressed values, where each address can have a defined maximum value.

This feature allows the creation of various effects on the buttons, including rotation, resizing, moving, color changes, and graphics. For example, you can create a rotating analog needle with input values from 0 to 1000, a graphical thermometer with size change effects, or a balancer with moving effects. You can even create a battery icon that changes color with voltage drop. Remember, to achieve noticeable changes, you should consider minimum input values; for instance, values from 0 to 5 won't show significant effects, but higher values like 0 to 500 or 1000 will. For a complete rotation, at least values from 0 to 360 should be applied, or for proper color changes, remember that color values range up to 255.

swiftdesign also supports copy-paste for repetitive tasks. Just create a detailed button and paste its properties to other buttons.

Additionally, swiftdesign allows for navigation between created pages. You can create numerous menus and pages, adding sound and vibration to buttons for a pleasant feel. You can share your designs by sharing the text files of the pages. If documents, images, and PDFs are included, it's better to share the related folders as well.

Notes in swiftdesign do more than just note-taking. They also serve various tasks such as saving notes, recalling notes, converting to HTML in HTML file editing, and sending commands in serial output in two ways: line by line or with a command line followed by a timer. This enables you to create programmable processes. You can write scenarios as notes and send them to the microcontroller in Note Out to execute your desired operations.

ESP8266 Project

The ESP8266 WiFi module creates a two-way connection between swiftdesign and the microcontroller with a local server. If needed, you can extract the package and server files from the server folder and upload them to your online server for a remote online control experience. The source files of the ESP8266 server project are available and unrestricted for you to enhance and improve.

Rangmang Project

Rangmang is a project designed to control RGB LED strips via Bluetooth serial commands using swiftdesign. This project allows users to program and control WS2812B LED strips to create stunning lighting effects. swiftdesign acts as the interface to send commands to the microcontrollers, enabling dynamic color changes and patterns. The source files of the Rangmang project are available and unrestricted for you to enhance and improve.

To download swiftdesign, you can visit the following resources:

GitHub

YouTube (which includes Google Drive download links)

APKPure market for quick access to updates

Example of Sending Commands or Custom Messages to the Serial Terminal in swiftdesign
Open swiftdesign: Click on the play icon in the top right corner. From the play page, switch to the stop or edit page; the icon will display as a stop symbol. Locate the design icon (a 6-grid icon) in the top right and click on it. Choose the third option to summon a button.

Summon a Button: Click on the button, and now the button design icon will appear. Click on the design icon and choose the sixth option, "Behavior." A light blue label will appear on the page; click on it. Then, select the sixth option, "Note." Choose the initial note "hello" and confirm, so a note appears.

Switch to Play Mode: Now, you can switch from stop to play mode by clicking on the edit icon. Click on the icon whose behavior you set to the note.

Notes Can Be Converted to Output Commands for Bluetooth and Server
To enable this, follow the instructions below:

For Bluetooth Mode:

Ensure Bluetooth sending is enabled in the settings.

When Bluetooth is connected, the "Note Out" or sending icon will be displayed. Long-click on it to access the Bluetooth sending settings.

In Serial Bluetooth Mode: There are two writing modes: dellay

Without Custom Wait:

- Value 1
- Value 2
- Value 3

- Example:

- LED1_ON
- LED1_OF
- LED2_ON
- LED2_OF
- LED3_ON
- LED3_OF
- LED4_ON
- LED4_OF
- LED5_ON
- LED5_OF
- LED6_ON
- LED6_OF
With Custom Wait:

- Value
- Timer (in seconds, between 0 to 3600)
- Value
- Timer

- Example:
  
- LED1_ON
- 3
- LED1_OF
- 2
- LED2_ON
- 1
- LED2_OF
- 6
- LED3_ON
- 4
- LED3_OF
- 2
- LED4_ON
- 1
- LED4_OF
- 8
- LED5_ON
- 2
- LED5_OF
- 1
- LED6_ON
- 1
- LED6_OF
- 2
Note: An empty line will terminate the program.

Settings:

Delay: Set a delay between 0 to 1000 milliseconds for line-by-line sending.

CR LF or NULL Character: Configure the end character of the sent value as needed.

Auto or Manual Sending: In manual mode, an icon will appear for line-by-line sending.

Check-In: To verify received confirmation. For example, send "123" and if "123" is received, it proceeds to the next line. Otherwise, it repeats a few times and stops if "123" is not received. This is similar to serial echo, ensuring correct receipt.

Next Reception: Sensitive to the word "next" in the reception. Useful when the microcontroller's operation time is unknown. For example, a motor moving a load may take different times to reach the destination based on the load. If a micro switch at the destination sends "next" to the Bluetooth module upon completion, swiftdesign will send the next line. Each "next" waits for up to 600 seconds; if exceeded, the program stops.

Custom Wait: Previously mentioned for setting custom stops between lines.

Loop: Enables continuous cyclic operation.

To start sending, click the Note Out icon. For additional settings, long-click on the icon. To stop, you can click "Close" or press the phone's back button.

Important:

If you add a new command to the note, ensure you save it by clicking the info icon in the top left and selecting save. Unsaved commands will not execute and will not be saved upon closing the note.

In manual sending mode, avoid using the timer value or custom wait as it will result in improper output.

Server Mode:

Similar to Bluetooth mode with slight differences.

In initial settings, select the server sending mode.

Two Writing Modes:

Without Custom Wait:

- Address
- Value
- Value
- Value

- Example:

- http://192.168.1.104:3000/GET123
- LED1_ON
- LED1_OF
- LED2_ON
- LED2_OF
- LED3_ON
- LED3_OF
- LED4_ON
- LED4_OF
- LED5_ON
- LED5_OF
- LED6_ON
- LED6_OF

With Custom Wait:

- Address
- Value
- Timer (in seconds, between 0 to 3600)
- Value
- Timer

- Example:

- http://192.168.1.104:3000/GET123
- LED1_ON
- 3
- LED1_OF
- 2
- LED2_ON
- 1
- LED2_OF
- 6
- LED3_ON
- 4
- LED3_OF
- 2
- LED4_ON
- 1
- LED4_OF
- 8
- LED5_ON
- 2
- LED5_OF
- 1
- LED6_ON
- 1
- LED6_OF
- 2



Note: An empty line will terminate the program.

Note: No check-in or next reception in server mode.

Settings:

Delay, Auto/Manual Sending, Custom Wait, and Loop are similar to Bluetooth mode.

Important:

Save new commands by clicking the info icon in the top left and selecting save. Unsaved commands will not execute and will not be saved upon closing the note.

In manual sending mode, avoid using the timer value or custom wait as it will result in improper output.

''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
Setting Up the ESP8266 Module
Download and Extract Files:

Download the ESP8266_json.zip file and extract it.

Open the Arduino Code:

Go to the folder Arduino code for programming the module ESP8266.

Open the esp8266.txt file and copy the code.

Install Libraries and Paste Code:

Open the Arduino software.

Download the ESP8266 library.

Paste the copied code into the Arduino software.

Configure Board and Port:

In Arduino, set the board to ESP8266.

Configure the USB-to-Serial adapter port (baud rate should be 115200).

Connect Pins:

Connect the adapter pins to the module (ensure the module uses 3.3V).

Reset the Module:

Connect the GPIO0 pin to GND.

Connect the module's reset pin to GND for one second and then disconnect it to reset the module.

Compile the code into the module (ensure the password, server address, modem name, and port match your server and specifications).

Reconnect and Display MAC Address:

After compiling, disconnect the GPIO0 pin and reset the module.

The module’s MAC address will be displayed initially.

Program the Microcontroller:

Program the microcontroller using the bascom folder.

If you do not wish to use Bascom, program the microcontroller with the Atmega16_report.hex file.

Activate the external crystal fuse bit.

Use the Proteus Folder:

Go to the proteus folder for connections, schematics, and additional help.

Start the Local Server:

After assembly, click on Start server.bat in the server folder to start the local server.

Go Online:

For real online use, utilize the two package and server files in the server folder (this method is JSON-based).

Set Up Android Software:

All these steps are explained on YouTube.

https://youtu.be/PV-M5d7y2hA

Paste the main file into the page folder of the Android software to display the swiftdesign program

''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

## Keywords
- swiftdesign
- swift-design
- custom-html
- android-app
- bluetooth-serial
- apk
- Programmable Buttons
- android
- swift
- custom-ui
- Bluetooth-microcontrollers
- Bluetooth Serial Interface to Send data to microcontrollers
- HC-05
- Bluetooth UART
- RGB program
- WS2811
- WS2812
- Arduino Bluetooth
- HC-06
- ESP32
- Bluetooth Serial
- WS2812B
- Rangmang
- Bluetooth Serial Communication
-Control RGB LED strips wirelessly.
-Customize buttons to send specific commands
-Dynamic Lighting Effects
-Create and save custom lighting patterns
-Integration with swiftdesign
-Seamlessly integrates with swiftdesign for enhanced functionality
