# HomeAssistant-VTR-Modbus
Simple control of Systemair VTR(300) via modbus TCP (Wifi) directly to HA.

Credits to GMTrevis who created the original code for Home Assistant, and then improved it for use via Node-Red.
The Node Red version has full control of the VTR, but I had issues where it overloaded my Node-Red. 
I found his incomplete Home Assistant code, and am working on filling it out for my own experiences.

And a big thanks to cmragnar who branched off and created a package out of this, which I'm now merging in and will continue fixing on that instead.
* https://github.com/cmragnar/HomeAssistant-VSR300-Modbus

With this you currently can:
- Change operation Modes, Auto, Low/medium/high, Crowded/Party, Refresh/Boost, Away, Vacation. Stop seems to need a look at.
- Set duration setpoint for Away, Vacation, Boost/Refresh and Crowded/Party
- See alarm status and filter replacement countdown, and adjust the filter countdown.
- Etc
- See alarm status and filter replacement countdown.
- Set wanted temperature on the VTR thermostat.
- Create automations your own automations using the above. 


Known Issues:
See Issues Tab.


Sources:
* Modbus codes: https://shop.systemair.com/upload/assets/SAVE_MODBUS_VARIABLE_LIST_20190116__REV__29_.PDF
* VTR Installation manual: https://shop.systemair.com/upload/assets/SAVE_VTR_300B_SERVICE_AND_ACCESSORIES_INSTALLATION_NO_V1_20210616_122140836.PDF?31ae5eca
* Older HA code from GMTrevis: https://community.home-assistant.io/t/systemair-savecare-ventilation-unit/229653/2 
* New Node-Red/HA code from GMTrevis: https://github.com/GMTrevis/Homeassistant-NodeRed-Systemair-VTR300

HACS addons used:
https://github.com/piitaya/lovelace-mushroom

![default](https://github.com/user-attachments/assets/aa2a04d6-4e4f-4ca8-87f8-1659b82ea11e)
![show_hidden](https://github.com/user-attachments/assets/f18d5374-40f2-45e3-ac26-86870fb9ec56)




Hardware required: (For my setup)
A modbus tcp converter. I use the EW11 from Aliexpress, via Wifi.
https://www.aliexpress.com/item/33036056772.html?spm=a2g0o.order_detail.0.0.2613f19cZlIBKq

How to install this:
- Copy all my .yaml files to your HA installation folder, and modify the paths in configuration.yaml to match your personal settings if applicable.
- Modify modbus.yaml with your working modbus settings.
- Verify HA configuration is OK and reboot. 
- Copy my HA UI card layouts if you'd like. Take note of the dependency of some HACS addons I've used.

Files explained:
User Interface/* - Copy of my HA card layout
modbus.yaml - Stored in the HA root folder. Contains the system specific settings, and the modbus sensors. NOTE: The addresses has an offset of -1 compared to the VTR user manual linked.
configuration.yaml - Configured paths to the various functions. I have multiple files for various things, therefore I've placed the files under folders in HA as here in github.



