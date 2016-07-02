#Attention: This software is not ready for production use, consider it being in alpha state !!!

#homebridge-smarthomeng
Homebridge plugin for SmartHomeNG
##Currently supported
This plugin currently supports:
* LightBulb with on/off and brightness characteristic
* Window Covering with currentposition and targetposition characteristic (state not yet supported)

##Requirements
SmartHomeNG: https://github.com/smarthomeNG/smarthome
homebridge: https://www.npmjs.com/package/homebridge
##Installation
Install nodejs >= 0.12. You have to find out the right way for your OS. The following commands have been tested on Debian Jessie.
<pre>
curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -
sudo apt-get install -y nodejs
</pre>
Install homebridge from NPM repository
<pre>
npm install -g homebridge
</pre>
Install this plugin from NPM repository
*** ATTENTION: NOT YET PUBLISHED ***
<pre>
npm install -g homebridge-smarthomeng
</pre>
##Configuration
You have to create a config.json in .homebridge directory. You'll find that directory in your home folder.
This is an example config file which just uses this plugin and some example SmartHomeNG items.
<pre>
{
    "bridge": {
        "name": "HomebridgeSH",
        "username": "CC:22:3D:E3:CE:32",
        "port": 51826,
        "pin": "031-45-154"
    },

    "platforms": [
        {
            "platform": "SmartHomeNG",
             
            "name": "SmartHomeNG",
            "host": "myshngserver.mydomain",
            "accessories": [
                {
                    "name": "Licht Büro",
                    "type": "Lightbulb",
                    "onoff": "EG.Buero.Licht"
                },
                {
                    "name": "Rollladen Büro",
                    "type": "WindowCovering",
                    "currentposition": "EG.Buero.Rolladen.Position",
                    "targetposition": "EG.Buero.Rolladen.Position"
                }

            ]
        }
    ],
    "description": "This is my development config file."
}
</pre>