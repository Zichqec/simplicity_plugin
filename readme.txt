Put your readme here! Usage instructions are a good idea since plugins are so varied, and are less common than ghosts. Please make sure you add a craftman and replace the name/directory of the plugin in the descript.txt and install.txt files! And especially make sure you set a unique ID, instructions are in the descript.txt file.


This template is based off the YAYA as PLUGIN files, which you can find right here: https://emily.shillest.net/ayaya/index.php?YAYA+as+PLUGIN

I have updated the library slightly to fix the issue with hour12 by adding hour12ex. I have also updated the yaya.dll to Tc571-5. None of what's in yaya_plugin2.dic is my work, the credit for that goes to "yaya develop team". I think that's these folks over here: https://github.com/yaya-shiori

YAYA as PLUGIN is a bit different from YAYA as SHIORI, which is what is used to make ghosts. Here are a few key points:

• Function names are always written exactly as they are; there is no On_ prefix for SHIORI resource events and such.

• In YAYA as SHIORI, you can write references like reference0, reference1, etc. That is not the case here. References are always, *always* an array, and are written like reference[0]. reference[1], etc.

• If you want to raise another event in the plugin, you can't use a normal raise tag, since the ghost is the one that is executing the SakuraScript! You'll need to use raiseplugin, and specify your plugin and what event to raise.


If a value is returned from the plugin, it will be executed as SakuraScript. You can control this with the following variables.

res_event
res_reference[0], res_reference[1], etc...
	res_event is the name of the event to run, and res_reference is an array of references to send and is optional. Note that res_reference must be written like res_reference[0] and cannot be written as res_reference0.
	
res_target
	Specifies which ghost the script or event should be sent to. This is the *sakura name* of the ghost, not the ghost name.
	You can use __SYSTEM_ALL_GHOST__ to send it to all running ghosts.
	If this is omitted, then the event will be sent to the ghost that executed the plugin menu.

res_marker
	Specifies the text to be displayed in the balloon's SSTP text (the status indicator, usually at the bottom).

res_script_option
	If set to "notranslate", it won't be run through the ghost's OnTranslate / MAKOTO, I think.
	If set to "nobreak", it will wait to send the event if a balloon is already open.

res_event_option
	If set to "notify", the event will be sent as NOTIFY instead of GET.
	
For more info on those last two options, see the plugin specifications: https://emily.shillest.net/specwiki/index.php?PLUGIN%2F2.0%2F%E4%BB%95%E6%A7%98%E6%9B%B8


Here is the Ukadoc page for events that are sent to plugins: https://ukagakadreamteam.github.io/ukadoc/manual/list_plugin_event.html
And the page on descript.txt for plugins: https://ukagakadreamteam.github.io/ukadoc/manual/descript_plugin.html

One final note: if you want to quickly reload your plugin, you can do so from the ghost explorer! Open the explorer with Ctrl E, switch the "type" tab to "plugin", then find your plugin in the list. Right click it, click the enable/disable button, then right click it again and click that button again. Then you can double click your plugin to run it and you should see that it has reloaded!

You may need to restart SSP if you do something like change the name of the plugin. Once plugins are loaded in they're a bit difficult to change the details of.

Good luck!


Simplicity Plugin v1.0.0, using YAYA Tc571-5
Made by Zichqec https://ukagaka.zichqec.com/
You are free to use this to create any plugins you like, no need to credit me! But if you'd like to find more by me, including more templates like this, find me at the link above.

The YAYA as PLUGIN library is not mine, I've just written the English usage notes and instructions (which were based on the original ones in Japanese) and made some test events. You can find the original library at the link near the top of the file.