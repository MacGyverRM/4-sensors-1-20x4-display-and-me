4 separate MQTT sensors on a 20x4 LCD display using Node-RED 

For quite some while I've been trying to display 4 sensorvalues (temparature, humidity, pressure and CO2 ) from MQTT using Node Red on a 20x4 display. 
The display is connected to my Raspberry Pi Zero W running dietPi. 
On forehand I thought that it would be a nice project for a beginner. 
After some trial and error, debugs where looking ok, I got values quite easily in an object {msgs: array[4]}, with for each line of the display the correct message. After pushing 'Deploy' the first output to the display was ok, so I had good hopes. But somehow the following outputs where not ok. One or two values became, on and off, 'undefined' and de values where randomly placed on 1 of the 4 lines of the display. Probably because the 4 different input with theír seperste flows didn't get 100% synced in the array (by the 'join'-node).
Searching online I read, that I wasn't the only one who had this problem. Surprisingly however I nowhere could find the solution to this problem.
Many hours later, spread over a few weeks, I now seem to have found the solution. Still not sure I understand the logic behind it, but hey, it works.

Used Node-RED nodes:
- node-red : mqtt in
- node-red : function
- node-red : join
- node-red-contrib-lcd20x4-i2c : LCD20x4-I2C

Sensors:
- BME280 for temperature, humidity and pressure_hPa
- MH-Z19 for CO2

PS
Bare with me if this repository doesn't live up to the github standard. I'm new to this and hope I git the hang of it soon. 
