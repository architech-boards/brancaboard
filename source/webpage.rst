The Web pages
*************

The web pages that I used were put in some strings, see below.

.. code::

 uint8_t TxBuffer_led_pageLVoffLBoff[] = "<html><head><meta content='\22'text/html; charset=ISO-8859-1\0x22 http-equiv=\0x22content-type\0x22><title>Leds.html</title></head><body> <br>Green_Led is OFF <br>Blue_Led is OFF<br></body></html>\r\n";

 uint8_t TxBuffer_led_pageLVonLBoff[] = "<html><head><meta content='\22'text/html; charset=ISO-8859-1\0x22 http-equiv=\0x22content-type\0x22><title>Leds.html</title></head><body> <br>Green_Led is ON <br>Blue_Led is OFF<br></body></html>\r\n";

 uint8_t TxBuffer_led_pageLVonLBon[] = "<html><head><meta content='\22'text/html; charset=ISO-8859-1\0x22 http-equiv=\0x22content-type\0x22><title>Leds.html</title></head><body> <br>Green_Led is ON <br>Blue_Led is ON <br></body></html>\r\n";

 uint8_t TxBuffer_led_pageLVoffLBon[] = "<html><head><meta content='\22'text/html; charset=ISO-8859-1\0x22 http-equiv=\0x22content-type\0x22><title>Leds.html</title></head><body> <br>Green_Led is OFF <br>Blue_Led is ON <br></body></html>\r\n";


| To fit into a character string the character: **"**
| you must use the following syntax: **'\ 22'**

