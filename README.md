# STM32 PGM Memory Header
## Overview
Arduino Amtel AVR architecture microcontrollers use the PGM library <pgmspace.h> to access flash memory. A large number of Arduino libraries depend on this library. This library is generally not distributed with other Microcontroller architectures such as STMicroelectronics. See this [Wikipedia](https://en.wikipedia.org/wiki/List_of_Arduino_boards_and_compatible_systems) link for detailed on non Amtel AVR Arduino supported Microcontroller architectures.
## Installation
Deploy pgmspace.h to your Microcontroller library. Typically in a directory structure ./arduno/packages/$Board Manufacturer$/hardware/$Microcontroller Architecture$/$Version$/cores/arduino/.
## Usage
Most Arduino libraries typically have an architecture check in their header file that often looks something like:
```c
#if (defined(__AVR__))
  #include <avr/pgmspace.h>
#else
  #include <pgmspace.h>
#endif
```
If this is not the case with a particular library, then you have an option of revising a variant of the library or importing <pgmspace.h> in your main code.
## Tests
This header file has only been tested on a STM32407. Though the approach is generic enough for most non Amtel AVR architectures.
