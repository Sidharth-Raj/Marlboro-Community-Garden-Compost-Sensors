Background:
Marlboro community garden has around 80 plots and 16 composting bins. Resident can reserve a plot and grow their own vegetables. Composting bins are used to make compost and will be re-used as fertilizer in the garden. Composting process requires periodic monitoring of temperature and moisture to ensure optimal conditions for composting. This was being done manually and when I approached my sponsor Ms. Simonetti, who manages the garden, and suggested an automated monitoring system, she enthusiastically agreed. 

Hardware Design
The design is based on Mesh and WiFi modules from Particle Systems. Gateway module (Argon) communicates with a number of Mesh modules (Xenon) and pushes the data to the cloud, which can then be displayed live on a website. Sensors use the Xenon module and connected to a temperature and moisture sensors embedded in a wooden plank inserted in the compost bin. It is powered by three standard AA Lithium batteries. Argon has external antennas for both the WiFi as well as the Mesh network. It is powered by a re-chargeable Lithium Polymer battery charged with a solar panel. All units are housed in water-proof enclosures. The gateway connects to the WiFi network from a nearby Firehouse which is around 150 feet away.

Software Design
Software is designed to conserve batteries, the sensors wake up every one hour, read the temperature and moisture values. Estimated battery life is around 4 years before needing replacement. The gateway is always on on the mesh side, however it keeps the WiFi switched off to conserve power. It wakes up every one hour to transmit the sensor values received from all four sensors to the cloud.
I used Thingspeak.com to connect to the Particle cloud and display the sensor values in real time. You can see the real time values here: Marlboro Community Garden - ThingSpeak IoT The voltage levels of all the devices are also displayed here: voltage - ThingSpeak IoT.
I have also uploaded the code and schematics to Github: 
Sidharth-Raj/Marlboro-Community-Garden-Compost-Sensors (github.com)
Problems faced:
The system was installed in July 2020 and is working continuously since then. After a major storm and cloudy weather, the gateway stopped working. After investigation, it was due to the deeply discharged battery and the small solar panel. I modified the software to continuously monitor the battery voltage and put the gateway to sleep when it goes below a threshold. I also changed the solar panel to a bigger size (from 2W to 6W). With these changes, the system has been working reliably through winter and multiple snow storms.

Conclusion:
The system has been working successfully for the last 5 months and is very useful to the gardeners.

