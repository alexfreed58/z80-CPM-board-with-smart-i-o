# z80-CPM-board-with-smart-I/O
<p>This is yet another retro computer running CPM on an actual Z80 CPU with a twist. Instead of using a traditional UART for communications, it uses a RPi pico module that is no bigger and no more expensive than a UART. But it can do a whole lot more. On this board it also generates the CPU clock that can be set to any desired frequency. If you have a 20 MHz Z80, use 20 MHz.</p>
<p>
There is also a provision to add an ESP32 module that allows connecting to the board via WiFi (telnet server) or BlueTooth. Of course you need to load a simple program onto the ESP32 from the ESP32 examples with some  modifications. Arduino works well.</p>
<p>
I use an SD card for disk emulation. I made a lot of design choices to be somewhat compatible with John Winans' z80-retro computer: "disk" geometry and memory management in particular. However my SD interface is quite different. Instead of bit-banging SPI, I use a couple of TTL (or CMOS) chips. The heart of the interface is a 74(LS/HC)299 universal shift register and some glue logic. I have decided to use several off-the-shelf chips rather than  a single CPLD because if anybody decides to use my design, it will be a lot easier if you don't have much experience with programmable logic. As a result the SPI interface runs at the full CPU clock speed  and to transmit and receive a byte via SPI you only need to write one byte to an i/o port and read a byte back.</p> 
<p>
The board design is done with the (fantastic!) open source Kicad. Likely much less than perfect as it is my first Licad project ever. I used mostly Altium Designer for professional work, but since Kicad is free, anyone can modify and improve the board.</p>

