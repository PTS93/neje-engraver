# neje-engraver

thanks to Fredrik Andersson (youtube) for reverse-engineering and sharing

NEJE Laser engraver protocol 

baud 57600
8 data bits
1 stop bit
parity none

0xf9 = stop/reset
0xf1 = start (Once issued incoming data will specify the position, data uses a modulus format.)
0xf2 = pause 
0xf4 = engraving preview (visualizes bounding box)
0xf5 = go up
0xf6 = go down
0xf7 = go left 
0xf8 = go right
0xf3 = go to left corner
<time in hex default= 0x3c (60ms)>  burn time 
0xfa = set motor parameter <hex speed default = 0x23 (35ms)> 
0xfb = go to center
0xfc = fast backward <parameter 0x55> fast forward <parameter 0xaa> recarve <parameter 0x77> // Useful???
0xfe x8 = erase + send picture <picture data bmp> (BMP specification BW; 512x512px)﻿
