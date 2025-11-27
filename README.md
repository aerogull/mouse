# beat - a mouse designed for any case
I've wanted to design my own mouse for the longest time. I've built my own keyboard, so it was just the next logical step, right? Well, the complexity from a keyboard run off a microcontroller powered by qmk, to a custom programmed mouse with a proprietary mouse sensor and a nRF52 chip, was quite the leap. This is a v1, it's not going to be light, it's not going to be very small, the side button connectors will likely be changed, and the case will not be ergonomic in any way that isn't comfortable to me. The firmware will be slower than most modern mice, and I probably won't be able to bring out the full speed of the PAW3395 sensor used (if I use ESB). But this is a testing board, and changes will be made to improve it in the future! With that, onto the specs and design!
## PCB
- nRF52840
- PAW3395
- 11mm compatible Alps scroll (w middle click)
- 4 Omron Switches (1 other switch for middle click)
- Lipo battery (500mAH)
- Dongle (nRF52840 + USBC) (COMING SOON)
- USBC charging
## Case
## Firmware
_**Warning: The PAW3395 Driver is Propiretiary, and Can Not Be Provided by Me**_ 