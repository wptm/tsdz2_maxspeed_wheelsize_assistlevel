# tsdz2_maxspeed_wheelsize_assistlevel
How to update your stock firmware to have different factory default Max Speed, Wheel Size and Assist Level

Change in stock firmware is related to following default(without display) values:
max speed to 45Km/h
-------------------------
```
Original - 0x19(25):
	0x8210:	 a6 19	ld A, #$19
New - 0x2D(45):		
	0x8210:	 a6 2d	ld A, #$2d
```
wheel size to 20inch
-------------------------
```
Original - 0x1a(26):
	0x8214:	 a6 1a	ld A, #$1a
New - 0x14(20):
	0x8214:	 a6 14	ld A, #$14
```
assist to level 3
-------------------------
```
Original - jumps to $a860 as default (assist level 4):
	0xa801:	 24 5d	jrnc $a860  (offset=93)
	...
	0xa81c:	 20 42	jra $a860  (offset=66)	
New - jumps to $a84a as default (assist level 3):
	0xa801:	 24 47	jrnc $a84a  (offset=93)
	...
	0xa81c:	 20 2c	jra $a84a  (offset=66)
```
    
VOAMCA firmware can be updated as well. I use it like so. Therefore I switch the motor on with the switch and I can ride my bike immediatelly.
I only need my mobile with bluetooth connection if I would like to see the Voltage, Watts, Speed, etc.

Part One, to change default(without display) Max Speed and Wheel size:
