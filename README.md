# esphome-modbus-optidriveEco
Esphome YAML configuration to control and gather data from a optidrive Eco pre-programmed for pump control.

The optidrive is pre-configured by the installator to control a wather pump, has a pressure sensor and using the internal pid control can mantain a pressure setpoint.
This configuration aims to gather running data, like pressure and power usage and to control the optidrive remotely.

I used a esp32-c3 board, with max485 transceiver board to comunicate using the modbus protocol to the optidrive. 
On the esphome site ther's a similar example using a RS485 transceiver board https://esphome.io/components/modbus_controller.html

To mantain the pressure setpoint, the primary control of the inverter must be the pid controller, modbus command word can't be used.
With a LR784 module, is possible to open/close the contact between 1-2 of the terminal block, effectively controllign the drive enable status of the optidrive.
Is possible to use a different module, with a mosfet than can support 24V and a 3.3V control signal.
