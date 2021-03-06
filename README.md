# control sk6812 LEDs with node.js on Raspberry pi 4

install manually: 

```
cd node_modules
npm install -g node-gyp
git clone --recursive https://github.com/bighead-sh/node-rpi4-sk6812-native.git
cd node-rpi4-sk6812-native
npm install
node-gyp rebuild
```

### REMEMBER TO USE 

a 3.3V to 5V logic-level converter

### Known Issues

There is a conflict where the internal soundcard uses the same 
GPIO / DMA / PWM functions that are needed to run the LED-drivers. 
As far as I know you can not use both at the same time.

To disable audio, comment out the following line in config.txt contained on the boot partion.

```
#dtparam=audio=on
```

Default is off.


On headless systems you may also need to force audio through hdmi Edit config.txt and add:
```
hdmi_force_hotplug=1
hdmi_force_edid_audio=1
```




### based on pieces of code from
@n-johnson / rpi_ws281x <br>
@rpi-ws281x / rpi-ws281x-python <br>
@beyondscreen / node-rpi-ws281x-native <br>
@n-johnson / node-rpi-sk6812-native <br>