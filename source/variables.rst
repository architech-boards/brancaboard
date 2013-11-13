The variables
*************


The Leds status

.. code::

 uint8_t LedG=0; // Led Greem 0==OFF 1==ON
 uint8_t LedB=0; // Led Blue 0==OFF 1==ON

The Leds flashing

.. code::

 uint8_t LBflash=0; // Led Blue 0==FlashOFF 1==FlashON
 uint8_t LGflash=0; // Led Green 0==FlashOFF 1==FlashON

| The variables below are used to configure the STM WiFi module.
| **Remember to configure the parameters in according to your WiFi network.**
| In particular, be sure to specify:

*   **RouterName** (see the orange line below)
*   **RouterPW** (see the yellow line below – password)

.. code::

 uint8_t TxBuffer_RouterName[] = "at+s.ssidtxt=U739\n\r";
 uint8_t TxBuffer_RouterPW[] = "at+s.scfg=wifi_wpa_psk_text,Ria1\n\r";
 uint8_t TxBuffer_RouterPotectionMode[] = "at+s.scfg=wifi_priv_mode,2\n\r";
 uint8_t TxBuffer_RouterRadioInSTAMode[] = "at+s.scfg=wifi_mode,1\n\r";
 uint8_t TxBuffer_RouterDHCPclient[] = "at+s.scfg=ip_use_dhcp,1\n\r";
 uint8_t TxBuffer_RouterSaveSettings[] = "at&w\n\r";
 uint8_t TxBuffer_RouterSoftReset[] = "at+cfun=1\n\r";

See also the function: `ConfigureWiFi <#ConfigureWiFi>`_
The variables below are used to test the STM WiFi module.

.. code::

 uint8_t TxBuffer_AT[] = "at\n\r";
 uint8_t TxBuffer_FAIL1[] = "+WIND:42:RX_MGMT:";
 uint8_t TxBuffer_FAIL2[] = "+WIND:43:RX_DATA:";
 uint8_t TxBuffer_FAIL3[] = "+WIND:44:RX_UNK:";
 uint8_t TxBuffer_FAIL4[] = "+WIND:34:WiFi Unhandled Event:";
 uint8_t TxBuffer_FAIL5[] = "ERROR:";

The RxBuffer; contain the characters received (under interrupt) from USART2 that is connect to STM WiFi module.

.. code::

  uint8_t RxBuffer[RXBUFFERSIZE];

The **RXBUFFERSIZE** is define in the file: **Definizioni.h**

Virtual EEPROM emulation address defined by the user:
**not used in this example**
.

I left it because it can be useful for some future application.
For more info see here:
`http://www.emcu.it/STM32F0xx/STM32F0-USART1-USART2-SysTick-IO/STM32F0-USART1-USART2-SysTick-IO.html <http://www.emcu.it/STM32F0xx/STM32F0-USART1-USART2-SysTick-IO/STM32F0-USART1-USART2-SysTick-IO.html>`_

.. code::

 uint16_t VirtAddVarTab[NB_OF_VAR] = {0x5555, 0x6666, 0x7777};
 uint16_t VarDataTab[NB_OF_VAR] = {0, 0, 0};
 uint16_t VarValue = 0;
 uint16_t NumPressBott=0x30;

