# Lego Tamagotchi!

This is a tamagotchi (a virtual pet) modeled after a lego piece! Created for Hack Club's #Fallout YSWS. It's my first larger-scale hardware project! 

<img width="2547" height="3296" alt="AssemblyLego2" src="https://github.com/user-attachments/assets/5fd01492-54c8-4692-bd4c-1e7b4385e37f" />

_He says hello! And also asks you to help him find a name! (Because I'm not creative)_


## Motivation 
As a complete beginner in hardware, I was absolutely lost on what hardware was. I had looked at a few KiCad tutorials, but each time I was confused -- what the hell was ground? What's the difference between 5V and 3.3V? Why are some things wired like that? But on a trip back from NYC with Tanishq, he gave me a good explanation on what hardware was, and how to get started with it. I was surprised to hear that he made his very own full-fleshed tutorial for those beginning in hardware, and honestly, I'll credit Tanishq and this tutorial for truly teaching me what hardware is. I'm still a beginner, but at least I've made that first step from zero to... one! Yay! 

Anyways, this is my first completed hardware project that uses both PCBs and CAD. Thank you Tanishq! 

## How It Works / How It's Used

### Components: 


| **Designator** | **Part** | **Wiring** | **Purpose** |
|-------|---|-------|---------------|
| U1 | Seeed Studio XIAO ESP32-C3 | N/A | Made by Seeed Studio, it's a miniature ESP32 that uses a USB-C for power; it's a microcontroller capable of WiFi and Bluetooth. Everything else on the PCB gives this module inputs, outputs, and power | 
| BT1 | Single-cell battery | N/A | This powers the whole board, connected to the XIAO BATT+ charging input pins | 
| SW1 , SW2, SW3 | 3 push buttons | GPIO2 (D0), GPIO3 (D1), and GPIO4 (D2), respectively | These push buttons allow the user to interact with the tamagotchi | 
| U2 | 0.96 inch OLED display (SSD1315) | SDA is wired to GPIO6 (D4) and SCL is wired to GPIO7 (D5), while VCC takes in 3.3V | This is the display for the pet -- it's the area that allows you to actually play and interact with your tamagotchi | 
| BUZZER1 | A piezoelectric buzzer | GPIO10 (D10) (MOSI) | This is the sound output. Whenever you press an action, the tamagotchi responds by buzzing with the buzzer to provide feedback. |


### Hardware: 


- **Tool:** KiCad 10
- **Board:** 2-layer PCB with a custom outline
- **Microcontroller:** The Seeed Studio XIAO ESP32-C3
- **Display:** A 0.96" 128x64 OLED display with a SSD1315 driver
- **Audio:** A piezoelectric buzzer approximately 12 millimeters in diameter
- **Input:** 3 push buttons embedded onto the PCB 

---

<img width="1410" height="2000" alt="Lego Tamagotchi Shelley Zine Fallout" src="https://github.com/user-attachments/assets/cfb26b5b-1810-4723-88ca-163711b7f1bd" />

_My zine!_


---
## PCB Design

<img width="1368" height="767" alt="image" src="https://github.com/user-attachments/assets/b43e3f8e-b6d8-407d-ba06-0843539667c8" />

_View of the schematic_


<img width="862" height="629" alt="image" src="https://github.com/user-attachments/assets/cae4dacb-41fa-40fe-abf6-781c160e430d" />

_View of the PCB (if you notice the little design in the middle, you should dm me on slack @shelx with a Matt Rose furby picture)_


<img width="1350" height="872" alt="image" src="https://github.com/user-attachments/assets/4fe8e0ef-e1c1-4332-a80b-445470f97f4b" />

_3D view_ 

...furbies...

anyways! 

---
## CAD 

This tamagotchi project got me to finally start learning how to CAD so wow! 

| <img width="722" height="724" alt="image" src="https://github.com/user-attachments/assets/96f545e6-ac49-42f4-b2f2-09e8d1e887ba" /> | <img width="456" height="698" alt="image" src="https://github.com/user-attachments/assets/79e03f14-d164-4df2-9e99-7a1609969d55" /> | 
|---|---| 
| Exploded View | Frontal View | 
| <img width="454" height="604" alt="image" src="https://github.com/user-attachments/assets/4192712f-d684-41ef-9e4d-00c435de0bd8" /> | <img width="522" height="724" alt="image" src="https://github.com/user-attachments/assets/d803c561-1d85-4b0c-8523-094e64c4fcfb" /> | 
| Back View | Side (Right) View |


The PCB is screwed in after the 3D printing is finished. 


---

## Bill of Materials (BOM) 

| Item |	Description |	Reference |	Qty |	MOQ |	Value |	Per Unit Price ($) |	Total Price ($) |	Footprint |	MPN |	URL |
|------|--------------|-----------|-----|-----|-------|--------------------|------------------|-----------|-----|-----|
| Battery |	Single-cell battery |	BT1 |	1 |	1 |	Battery_Cell |	3.87 |	3.87 |	Connector_PinHeader_2.54mm:PinHeader_1x02_P2.54mm_Vertical |	N/A |	[Link](https://www.aliexpress.us/item/3256808925172396.html?spm=a2g0o.productlist.main.11.6e1523a2T5o5mT&algo_pvid=a7f5d709-8287-4bd9-877e-4b7454d07aea&algo_exp_id=a7f5d709-8287-4bd9-877e-4b7454d07aea-10&pdp_ext_f=%7B%22order%22%3A%22115%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&pdp_npi=6%40dis%21USD%215.38%213.87%21%21%2136.32%2126.15%21%4021032f3717820018898186181ef57d%2112000047954562112%21sea%21US%217756416958%21X%211%210%21n_tag%3A-29911%3Bd%3A882c3b75%3Bm03_new_user%3A-29895&curPageLogUid=gVBhZCgn1w6G&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A1005009111487148%7C_p_origin_prod%3A) |
| Buzzer |	Audio buzzer |	BUZZER1 |	1 |	10 |	1207-P6.5MM |	0.0572 |	0.57 |	easyeda2kicad:BUZ-TH_BD12.5-P6.50-D1.4 |	1207-P6.5MM |	[Link](https://www.lcsc.com/product-detail/C49246964.html?s_z=s_p_1207-P6.5MM&spm=wm.fly.bg.0.xh&lcsc_vid=QQVaAVJeTlJdUVBVE1hcBVFWEwcNBVxeQwAPA1YHFQMxVlNeRVFeVVRXQ1laUDsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D) |
| Buttons |	Push button switch, generic, two pins |	SW1,SW2,SW3 |	3 |	10 |	SW_Push |	0.053 |	0.53 |	easyeda2kicad:SW-TH_4P-L4.5-W4.5-P3.00-LS4.8 |	TS-1088-AR02016 |	[Link](https://www.lcsc.com/product-detail/C720477.html?s_z=s_q_p_PUSH%2520BUTTON%2520SWITCH&spm=wm.ssy.bg.0.xh&lcsc_vid=QQVaAVJeTlJdUVBVE1hcBVFWEwcNBVxeQwAPA1YHFQMxVlNeRVFeVVRfQVlaXzsOAxUeFF5JWBYZEEoKFBINSQcJGk4NBhADEA4cHktfQVlADxALGw%3D%3D) |
| MCU |	XIAO-ESP32-C3 |	U1 |	1 |	1 |	XIAO-ESP32-C3-SMD |	2.95 |	2.95 |	Seeed_Studio_XIAO_Series:XIAO-ESP32-C3-SMD |	N/A |	[Link](https://www.aliexpress.us/item/3256808694624250.html?spm=a2g0o.productlist.main.2.7bf11671FvH8Ua&algo_pvid=71c252e5-18c7-4c17-801d-9350ae77c1f5&algo_exp_id=71c252e5-18c7-4c17-801d-9350ae77c1f5-1&pdp_ext_f=%7B%22order%22%3A%22718%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&pdp_npi=6%40dis%21USD%217.34%212.95%21%21%2149.50%2119.89%21%402101e62517820022180805568ecf92%2112000047069200692%21sea%21US%217756416958%21X%211%210%21n_tag%3A-29911%3Bd%3A882c3b75%3Bm03_new_user%3A-29895%3BpisId%3A5000000209196075&curPageLogUid=46Mmlu4FUmrg&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A1005008880939002%7C_p_origin_prod%3A) |
| OLED Display |	Display screen |	U2 |	1 |	1 |	HS96L03W2C03 |	2.24 |	2.24 |	easyeda2kicad:OLED-TH_L27.8-W27.2-P2.54_C9900033791 |	HS96L03W2C03 |	[Link](https://www.lcsc.com/product-detail/C5248080.html?s_z=n_q_HS96L03W2C03&spm=wm.fly.bg.0.xh&lcsc_vid=QQVaAVJeTlJdUVBVE1hcBVFWEwcNBVxeQwAPA1YHFQMxVlNeRVFeVl1TQFBZUzsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)
| PCB Build |	JLCPCB |	N/A |	1 |	1 |	N/A |	2 |	2 |	N/A |	N/A |	N/A |
| PCB Shipping |	JLCPCB |	N/A |	1 |	1 |	N/A |	2.5 |	2.5 |	N/A |	N/A |	N/A |
| Total |		| |	9 |	25	|	|	| 14.66			




Credits: 
- For the tutorial: [@TaniWanKenobi's](https://github.com/TaniWanKenobi) tamagotchi guide [linked here](https://fallout.hackclub.com/docs/guided-projects/tamagotchi) (it's amazing!)
- A screw import: https://grabcad.com/library/screw-06-1
- Hack Club Fallout mentors! 
