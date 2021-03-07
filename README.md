4 separate MQTT sensors on a 20x4 LCD display using Node-RED 

For quite some while I've been trying to display 4 sensorvalues (temparature, humidity, pressure and CO2 ) from MQTT using Node Red on a 20x4 display (connected to my Raspberry Pi Zero W with dietPi running on it). 
On forehand I thought that it would be a nice project for a beginner. 
After some trial and error, debugs where looking ok, I got values quite easily  in an object {msgs: array[4]}, with for each line of the display the correct message. After pushing 'Deploy' the first output to the dispplay was ok, so I had good hopes. But somehow the following outputs where not ok. One ore two values became on and off 'undefined' and de values where randomly placed on 1 of the 4 lines of the display. Probably because de 4 different input with theír flow didn't get 100% synced in the array (by the 'join'-node).
After searching online I read that I wasn't the only one who had this problem. Surprisingly however I nowhere could find the solution to this problem.
After many houres, spread over a few weeks, I now seem to have found the solution Still not sure I understand the logic behind it, but hey, it works.

Used Node-RED nodes:
- node-red : mqtt in
- node-red : function
- node-red : join
- node-red-contrib-lcd20x4-i2c : LCD20x4-I2C

Sensors:
- BME280 for temperature, humidity and pressure_hPa
- MH-Z19 for CO2
