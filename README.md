# piplates-CodeSys 
Connect your Pi-Plates to CodeSYS runtime on Raspberry PI

I Started this project back in 2019 developing libraries for Pi-Plates in CodeSYS.
The library and hardware description files enables SPI communication for Pi-Plates in CodeSYS.
Several Pi-Plates can be stacked and addressed in CodeSYS, tested with 5 Pi-Plates.

CodeSYS version:
  * CODESYS V3.5 SP18 Patch 2 + (32-bit)
  * CODESYS Control for Raspberry PI_SL 4.5.0.0

Supports the following Pi-Plates:
  * PiPlate DAQC 
            (https://pi-plates.com/daqcr1/)
    - Reads digital input (8 channels)
    - Reads analogue input (8 channels) AI2-8 range 0..1023 except for AI1 0..255
    - Writes to digital output (7 channels)
    - Writes to analogue output (2 channels)
            
  * PiPlate DAQC2
            (https://pi-plates.com/daqc2r1/)
    - Not completed yet as my board broke down, So still some work to be done here!!
    
  * PiPlate RELAY
            (https://pi-plates.com/relayr1/)
    - Writes digital output (7 channels)
    - Reads the digital outputs status (7 channels)
  
  * PiPlate MOTOR
            (https://pi-plates.com/motorr1/)
    - Dont remember how far i got with this one :)

Interface cable between Raspberry PI an the Pi-Plates need a small modification to control communication. 
RPI GPIO25 Out are required by Pi-Plates to initiate read from SPI bus. 
Unfortunately GPIO´s cannot be controlled outside a task in CodeSYS eg. within the library, 
so an optocoupler needs to be installed on the interface cable between CS1 (chip select) and GPIO25 wire towards the Pi-Plates.
GPIO25 from Raspberry PI should be cuted and isolated (no connection to Pi-Plates)
  * 1 Optocoupler PC817 (https://www.alldatasheet.com/datasheet-pdf/pdf/43371/SHARP/PC817.html)
  * 1 Resistor 1K ohm
  * 1 GPIO Ribbon Cable (40 pins F/F) 20cm

Modified ribbon cable with optocoupler:
![IMG_5109](https://user-images.githubusercontent.com/64552548/193050669-a70e5a71-69af-4d87-b367-62f5f8d08f28.jpg)



Picture from Codesys online mode:
<img width="1303" alt="Codesys-OnlineMonitor" src="https://user-images.githubusercontent.com/64552548/193023778-b9487b74-82be-4bc2-86b5-645439a2bc02.png">


Video of CodeSYS webvisu HMI:

https://user-images.githubusercontent.com/64552548/193028341-41c806b2-f4a2-47df-9bd2-c1bd9728c1eb.MOV


Video of PI-Plates IO when IO-Simulator function block running:

https://user-images.githubusercontent.com/64552548/193028549-745137fe-9472-471a-a130-65dd0721c518.MOV

