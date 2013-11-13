The definitions
***************


The commands for control the leds are show below.

.. code::

 // Define the commands for the Red, Blue Led OFF and ON
 #define BLed_OFF GPIO_ResetBits(GPIOC, GPIO_Pin_8) // Blue LED OFF
 #define BLed_ON GPIO_SetBits(GPIOC, GPIO_Pin_8) // Blue LED ON
 #define GLed_OFF GPIO_ResetBits(GPIOC, GPIO_Pin_9) // Green LED OFF
 #define GLed_ON GPIO_SetBits(GPIOC, GPIO_Pin_9) // Green LED ON
 #define RLed_OFF GPIO_ResetBits(GPIOC, GPIO_Pin_6) // Red LED OFF
 #define RLed_ON GPIO_SetBits(GPIOC, GPIO_Pin_6) // Red LED ON

.. warning::

 There are also two commands for flashing the LEDs that are in section variables and are:
 
 | uint8_t LBflash=0; // Led Blue 0==FlashOFF 1==FlashON
 | uint8_t LGflash=0; // Led Green 0==FlashOFF 1==FlashON

This variables are used in the file **stm32f0xx_it.c** under systick interrupt, see below.

.. code::

 /**
 * @brief This function handles SysTick Handler.
 * @param None
 * @retval None
 */
 void SysTick_Handler(void)
 {
   TimingDelay_Decrement();
   // Used by Delay(nnnn);
   // Routine for Flasing LED ****************************************************
   TLampeggio++;
   if (TLampeggio >= rifTLampeggio)
   {
     if (LBflash==1) // Toggle BLUE LED
       GPIOC->ODR ^= GPIO_Pin_8;
     if (LGflash==1) // Toggle GREEN LED
       GPIOC->ODR ^= GPIO_Pin_9;
     TLampeggio=0;
   }
 }


Also there are two variable used for remember the status of Green and Blue LEDs that are:

.. code::

 uint8_t LedG=0; // Led Greem 0==OFF 1==ON
 uint8_t LedB=0; // Led Blue 0==OFF 1==ON

The custom commands (implemented on STM32F0-Discovery) for control the

STM WiFi module are:


* **lgon** – TurnON the green LED

* **lgoff** – TurnOFF the green LED

* **lbon** – TurnON the blue LED

* **lboff** – TurnOFF the blue LED

* **X** – Clear RxBuffer

* **reset** – reset the STM WiFi module, it reload the WiFi configuration


The definitions are show below.

.. code::

 #define RxLBOFF "lboff" // Led Blue OFF
 #define RxLBON "lbon" // Led Blue ON
 #define RxLGOFF "lgoff" // Led Green OFF
 #define RxLGON "lgon" // Led Green ON
 #define RxClrBuf "X" // Clear RxBuffer
 #define RxReset "reset" // Reset the STM WiFi module,it reload the WiFi config.
 			 // received from STM32F0-Discovery.
 			 // During the reset the Blue Led is flashing.

The received strings used for test the status of STM WiFi are below

.. code::

 #define WiFi_IP "WiFi Up" // This means that STM WiFi is connected to WiFi Network
 #define WiFi_OK "OK" // This is the answer STM WiFi if a command is successful

The defines below are in the file: **Definizioni.h**

.. code::

 #define RXBUFFERSIZE 0x7FE // 2Kbyte
 #define rifTLampeggio 500 // 500 == 500mS is flashing time
 #define DlyAttesaRx 200 // 200 == 200mS is time that the SW waiting before to analyze the RxBiffer
 #define DlyUpLoadHTMLcode 5000 // 5000 == 5sec Delay time for waiting the upload of html page
 #define DlyBeforeClrRxBuffer 1000 // 1000 == 1sec Delay time to waiting before clear the RxBuffer
 #define FAIL 0
 #define PASS 1

