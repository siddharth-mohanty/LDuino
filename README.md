# LDuino - (C) 2016 Frederic RIBLE (frible@teaser.fr)

LDuino is a PLC software orignally designed for the "Controllino Maxi".
It could be easily ported to any other Arduino based platform.

It is based on a bytecode interpreter able to run code generated by a modified version LDmicro (https://github.com/f1oat/LDmicro).
LDMicro is a Ladder logic editor.

LDmicro currently supports:
* Ethernet Web interface for configuration management and status
* Static IP address of DHCP
* IP configuration stored in EEPROM
* Ladder logic program bytecode stored in EEPROM
* Digital or analog inputs named 'An'
* Digital or PWM ouputs named 'Dn'
* Relay outputs named 'Rn'
* Most LDMicro Ladder logic blocks including timers and operators
* MODBUS over IP slave mode
  * Coils and Holding registers (MODBUS slave ID = 1)
  * RS485 master gateway (when MODBUS slave ID <> 1 is used)
  * This gateway can be used to access RS485 slave devices connected to the PLC from a master connected by Ethernet

[ MODBUS master ] --- Ethernet link ---- [ Controllino PLC ] --- RS485 bus --- [ Additional slave devices ]
                                         [    local I/O    ]                   [        local I/O         ]

Up to now, the PLC cannot act as a MODBUS master device.
The PLC, as any other device connected to the RS485 PLC port, is a slave device controlled by the MODBUS master equipment
(for example, a PC or a LinuxCNC/Machinekit board).

The ldmicro/LDuino-valid.ld contains a sample Ladder program for LDuino and LDmicro validation.

# Default IP configuration

Buy default, LDuino software will try to get an IP address via DHCP.
In case of failure (after 60 seconds), the following default parameters will be used:
* MAC address = DE:AD:BE:EF:FE:ED
* IP 192.168.1.241
* Netmask 255.255.255.255
* DNS 192.168.1.1
* Gateway 192.168.1.1

All those parameters can be altered and saved in EEPROM.

# References:
* [LDmicro modified for LDuino](https://github.com/f1oat/LDmicro)
* [Official LDmicro software](https://github.com/LDmicro/LDmicro)
* [LDmicro forum](http://cq.cx/ladder-forum.pl)
* [Controllino vendor](http://controllino.biz/)

# LDuino web interface

![LDuino Web interface](/doc/LDuino_web.png)

# LDmicro example 

![LDmicro example](/doc/LDmicro.png)