# M5StickC_NightscoutMon
## M5StickC and M5StickC PLUS Nightscout monitor

###### M5StickC Nightscout monitor<br/>Copyright (C) 2018, 2019 Martin Lukasek <martin@lukasek.cz>
###### This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
###### This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.
###### You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>. 
###### This software uses some 3rd party libraries:<br/>IniFile by Steve Marple <stevemarple@googlemail.com> (GNU LGPL v2.1)<br/>ArduinoJson by Benoit BLANCHON (MIT License)
<br/>

<img width="320" src="https://raw.githubusercontent.com/mlukasek/M5StickC_NightscoutMon/master/images/M5StickC_Nightscout_w-speaker.jpg">&nbsp;&nbsp;<img width="320" src="https://raw.githubusercontent.com/mlukasek/M5StickC_NightscoutMon/master/images/M5StickC_Nightscout_monitor_watch.jpg">

### Bedside-display additions in this fork

This fork is configured for the **M5StickC Plus v1.1** (`#include <M5StickCPlus.h>`).
Install the M5StickC Plus Arduino library before compiling.

- The screen alternates between the CGM view and a large clock every 3 seconds.
- **Night mode** runs daily from **21:00 to 08:00** in New Zealand local time: dim red text on a black background.
- **Day mode** runs from **08:00 to 21:00**: the normal colour palette and maximum display brightness.
- The firmware uses the New Zealand timezone rule, including automatic daylight-saving transitions.
- The blue Wi-Fi update animation is suppressed; Nightscout requests continue normally in the background.
- Missing, stale, unreachable, or temporarily unavailable CGM data is a display-only condition (`NO DATA`/`STALE`). It does not beep or flash the LED. Low/high glucose alarms remain separate and unchanged.
- The main button cycles the original brightness levels. A manual selection is retained until the next day/night transition.

#### Private Nightscout and Wi-Fi configuration

Do not put personal credentials in committed source files. Copy
`M5StickC_NSconfig.local.h.example` to `M5StickC_NSconfig.local.h`, enter the
Nightscout URL/token and Wi-Fi networks there, then compile normally. The local
file is ignored by Git.

### Revisions:

#### *** 31 January 2021 ***
Support for Sugarmate added.  

#### *** 24 December 2020 ***
Support for M5StickC PLUS added.  

#### *** 27 October 2020 ***
Create a delay between POWER ON and searching for WiFi.  

#### *** 8 September 2020 ***
Fix spacing between IOB and COB values.  

#### *** 5 September 2020 ***
Nightscout token support added.  
JSON unicode characters replacement for Medtronics.  

#### *** 28 October 2019 ***
Key sgv_only (default 0) added to M5NS.INI. You should set it to 1 if you use xDrip, Spike or similar to filter out calibrations etc.  
Maximum password length extended to 63 characters.  

#### *** 8 September 2019 ***
Query for only the SGV records (Sulka Haro).  
Better display cleaning after WiFi symbol display.

#### *** 7 September 2019 ***
JSON query update for Ascensia Diabetes Care Bluetooth Glucose Meter.  
Small changes in SPK HAT speaker routines.  
Removed forgotten alarm test from main button, so it now changes the brightness only, as supposed to do.

#### *** 16 July 2019 *** 
Added support for M5StickC Speaker Hat (SPK, PAM8303).

#### *** 3 June 2019 ***
Alarm/warnign LED frequency changed. 

#### *** 18 May 2019 ***
First test version. Need changes in M5StickC library. IMU must be changed or removed (not needed).<br/><br/>

### M5StickC Nightscout Monitor

M5StickC is smaller brother of M5Stack development kit based on ESP32. It is in a tiny plastic box, equipped with color display, 2 buttons, and internal battery. It can be used to monitor and display something, so I used it to monitor my daughter's glycemia. It is small and cheap solution. For better monitoring with alarms, use bigger M5Stack Nightscout monitor.<br/><br/>


### Buttons

The main button changes the backlight in the 3 steps defined in configuration source file.<br/>
<br/>

### Donations

If you find my project useful, you can donate me few bucks for further development or buy me a glass of wine

https://paypal.me/8bity
