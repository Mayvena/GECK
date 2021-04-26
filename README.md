# GECK
Mixed software/hardware project to create a Garden of Eden Creation Kit. I.e. post-apocalyptic survival laptop


# Initial notes
This project is inspired by a number of places - one is the Fallout game franchise, in which there's a device called G.E.C.K., or Garden of Eden Creation Kit. It is the MacGuffin of the second game in the franchise, and according to the ingame description "_The kit included seed and soil supplements, a fusion power generator (referred to as cold fusion in briefing materials), matter-energy replicators, atmospheric chemical stabilizers and water purifiers._". Further in the description it is mentioned that the device contained large quantities of survival information, encyclopedias and all other data that could be vital for rebuilding society after a catastrofic event.

Another source of inspiration are a few actual similar devices, built by enthusiasts: The Division themed "SHD Cyberdeck" - https://youtu.be/JvbIEimqd0Y; Jay Doscher's "Off Grid Cyberdeck" - https://back7.co/home/raspberry-pi-recovery-kit, and Evan Meaney's "Crash Recovery Device" - https://evanmeaney.com/_recpi.html


# Design considerations
For obvious reasons my GECK cannot include a fusion powered generator or matter-energy replicators. What it __can__ include is survival information, methods of communication interface to control machines and various software tools (programming IDEs, runtimes, compilers, libraries, recovery tools etc.) that would help a competent and/or motivated individual to use the GECK to create, repair and recover various types of machinery, needed for long-term survival and resettlement effort. 
As for hardware - it needs to be durable, power-efficient, lightweight, water, dust and EMP proof; it needs to contain ways to recharge in many various ways, it needs to allow communication via various means, it needs to provide hardware interfaces to connect various peripherals; those interfaces need to be protected (as in some cases the user might be unaware of possible short cirquits and/or overvoltages) (https://projects-raspberry.com/raspberry-pi-gpio-protection/); it needs to be modular to an extent (i.e. being able to use an external monitor if the built-in display fails, external keyboard, mouse; being able to easily replace the memory card of the RPi and load another with a different image, etc.

A list of all aims:
1. Waterproof durable housing
2. EMP shielding
3. A way to switch on or off any of the built-in peripheral devices in order to conserve power
4. Rechargeable batteries having as large capacity as possible
5. A method for recharging the batteries
6. Built-in display
7. Built-in keyboard
8. Built-in network capabilities - both wireless and wired
9. GPS
10. Software defined radio
11. USB hub
12. Encyclopedia
13. Survival/engineering guides/articles/tutorials
14. GPIO shielding 


## 1. Housing

Other similar projects are using a Pelican 1200 case. While definitely a great case in terms of durability and level of protection it has its limitations. One is its size - being a bit over 230mm wide it is extremely hard to find a suitable for it keyboard in a sensible price range. Another con is the steep price tag of this case. Given that I'm operating on a budget, it was only logical to look for a more cost-effective solution which also offers a larger width. The chosen case is https://itt-shop.bg/hermetichen-kufar-za-instrumenti-yato-339-h-292-h-152-mm-10038422. It is 339mm wide with useable internal width of 

I have decided to use copper tape for EMP shielding of the case. This would mean however that it would be effectively shielded from WiFi as well. This means that there needs to be an external antenna for the WiFi. It is mounted on the display bezel and needs to be lifted upon opening the case. 

To provide effective shielding, the copper insulation needs to be grounded. For this purpose a part of the waterproofing gasket has been lifted, a strip of copper foil - glued in the gasket bed in a way that leaves it partially outside when lid is closed, and the gasket is glued back on top of it, effectively restoring the waterproof seal. 

Both bezels are machined out of sheet aluminum. This way they act as internal structural supports for the case, all while serving as heat radiators for those components that produce some significant quantities of heat. Those components are glued directly onto the aluminum panels. 

## 2. Input devices

All input devices are going to be wired. The reason is that wireless ones would require additinal batteries which might not be easily available. Also wireless devices tend to require more energy overall than wired ones. 

### Keyboard


### Mouse

There are a few ways to provide a graphical interface input. The simplest way is to use an actual mouse. Convenient for use, however it is rather inconvenient for storing due to its shape and size. 

Second option is to just use a touchscreen display. This might require a bit of getting used to, but the main issue in this case is price. Touchscreen panels tend to be between 30 and 50 percent more expensive than ordinary displays. 

Third option is to use an external usb touchpad. Its slim form factor makes it convenient to store in the case of the GECK while it is closed, it's rather intuitive to use. Here again the issue is the price, together with low availability. Adding its price to the price of the LCD screen might exceed the price of a touchscreen panel.

Fourth option is a DIY solution, utilizing an analog joystick through an MCP3008 ADC/SPI (https://grantwinney.com/connecting-an-analog-joystick-to-the-raspberry-pi-and-using-it-with-an-rgb-led-to-simulate-a-color-wheel/) This solution is a bit unconventional, but as far as cool factor goes it is the total winner. Also it is the cheapest solution, cheaper even than a conventional mouse. 
