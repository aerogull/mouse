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

![pcb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/d596facdfb798569c1ca93615b8ead4a7d7a9a30_screenshot_2025-11-26_212758.png)
## Case
## Firmware
_**Warning: The PAW3395 Driver is Propiretiary, and Can Not Be Provided by Me**_ 

### BOM
|Reference|Qty|Value|DNP|Exclude from BOM|Exclude from Board|Footprint|Datasheet|
|-----|-----|-----|-----|-----|-----|-----|-----|
|A1|1|~||||custom:PAW3395||
|C1,C29,C39|	3|	4.7μF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C2,C4,C5,C13,C14,C19,C20,C21,C22,C23,C28,C31,C38|	13|	100nF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C3,C6,C8,C10,C12,C15,C16,C18,C41,C43|	10|	10μF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C7|	1|	33uF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C11,C17,C42|	3|	1μF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C24,C25,C26,C27|	4|	12pF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C30,C32|	2|	1.0μF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C33,C37|	2|	N.C.|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C34|	1|	100pF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C35|	1|	0.8pF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|C36|	1|	0.5pF|	|	|	|	Capacitor_SMD:C_0805_2012Metric_Pad1.18x1.45mm_HandSolder|	~|
|D3,D5|	2|	MBR1020VL|	|	|	|	Diode_SMD:D_SOD-123F|	https://www.onsemi.com/pub/Collateral/MBR1020VL-D.PDF|
|J2|	1|	JSTPH|	|	|	|	custom:JSTPH2PINSMTRIGHTANGLECONNECTOR|	~|
|J3|	1|	USB_C_Receptacle_USB2.0_14P|	|	|	|	Connector_USB:USB_C_Receptacle_Amphenol_12401548E4-2A|	https://www.usb.org/sites/default/files/documents/usb_type-c.zip|
|L1,L4|	2|	10μH|	|	|	|	Inductor_SMD:L_0805_2012Metric_Pad1.05x1.20mm_HandSolder|	~|
|L2|	1|	15nH|	|	|	|	Inductor_SMD:L_0805_2012Metric_Pad1.05x1.20mm_HandSolder|	~|
|L3|	1|	3.3nH|	|	|	|	Inductor_SMD:L_0805_2012Metric_Pad1.05x1.20mm_HandSolder|	~|
|LED1|	1|	SK6812MINI-E|	|	|	|	custom:SK6812MINIE|	http://yushakobo.jp/ds/YS-SK6812MINI-E.pdf|
|R1,R9,R10,R11,R12,R13,R20,R21|	8|	10kΩ|	|	|	|	Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|	~|
|R2|	1|	5.6Ω|	|	|	|	Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|	~|
|R3|	1|	2kΩ|	|	|	|	Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|	~|
|R4,R5,R8|	3|	100kΩ|	|	|	|	Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|	~|
|R6|	1|	5.1kΩ|	|	|	|	Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder|	~|
|SW1,SW2,SW4,SW5|	4|	SW_SPST|	|	|	|	custom:SW_Tactile_SPDT_Omron_D2F|	~|
|SW3|	1|	SW_SPST|	|	|	|	Button_Switch_THT:SW_PUSH_6mm|	~|
|SW6,SW7|	2|	SW_SPST|	|	|	|	Capacitor_SMD:C_0402_1005Metric|	~|
|SW8|	1|	RotaryEncoder|	|	|	|	custom:EC10E1220503|	~|
|SW9|	1|	SW_SPST|	|	|	|	Button_Switch_SMD:SW_SPST_CK_RS282G05A3|	~|
|U2|	1|	SPX3819M5-L-3-3|	|	|	|	Package_TO_SOT_SMD:SOT-23-5|	https://www.exar.com/content/document.ashx?id=22106&languageid=1033&type=Datasheet&partnumber=SPX3819&filename=SPX3819.pdf&part=SPX3819|
|U3|	1|	MCP73831-2-OT|	|	|	|	Package_TO_SOT_SMD:SOT-23-5|	http://ww1.microchip.com/downloads/en/DeviceDoc/20001984g.pdf|
|U4|	1|	TLV70019_SOT23-5|	|	|	|	Package_TO_SOT_SMD:SOT-23-5|	http://www.ti.com/lit/ds/symlink/tlv700.pdf|
|U5|	1|	nRF52840|	|	|	|	Package_DFN_QFN:Nordic_AQFN-73-1EP_7x7mm_P0.5mm|	http://infocenter.nordicsemi.com/topic/com.nordic.infocenter.nrf52/dita/nrf52/chips/nrf52840.html|
|U6|	1|	SPX3819M5-L-5-0|	|	|	|	Package_TO_SOT_SMD:SOT-23-5|	https://www.exar.com/content/document.ashx?id=22106&languageid=1033&type=Datasheet&partnumber=SPX3819&filename=SPX3819.pdf&part=SPX3819|
|Y1|	1|	32.768 Hz|	|	|	|	custom:FC135327680KAA|	~|
|Y2|	1|	32 Hz|	|	|	|	custom:ABM8A32000MHZD2YT3|	~|
