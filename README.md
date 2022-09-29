# piplates-CodeSys
Library files and hardware description files to enable SPI communication for Pi-Plates in CodeSYS
Supports the following Pi-Plates:
  * PiPlate DAQC
  * PiPlate DAQC2
  * PiPlate RELAY
  * PiPlate MOTOR

Interface cable between Raspberry PI an the Pi-Plates need a small modification to control communication. 
RPI GPIO25 Out are required by Pi-Plates to initiate read from SPI bus. 
Unfortunately GPIO´s cannot be controlled outside a task in CodeSYS eg. within the library, 
so an optocoupler needs to be installed on the interface cable between CS1 (chip select) and GPIO25 wire towards the Pi-Plates.
GPIO25 from Raspberry PI should be cuted and isolated (no connection to Pi-Plates)
  * 1 Optocoupler
  * 1 Resistor
  * 1 GPIO Ribbon Kabel (40 pins F/F) 20cm
