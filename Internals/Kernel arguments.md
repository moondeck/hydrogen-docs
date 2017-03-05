#Kernel arguments

This page discusses the (planned) kernel arguments

##root

The root drive ID in the hydrogen format:

    drive:part

For example, a full argument can be:

    root=0:1 //drive 0, partition 1 (zero indexed)

##ro/rw

Mounts the root partition as either read-only or read-write (default rw)

Doesnt take arguments.

##baud

Sets baud rate for the serial port:

    baud=9600 //set the baud rate to 9600 bps

##serial

Set the serial port number

    serial=0 //serial 0, address 0x3F8, zero indexed

##ctype

Console type, 0 = serial, 1 = VGA, 0 is default

    ctype=1 //VGA console