    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
    

SleepTrack
==========

Track your sleeping position
Hardware build guide and full documentation can be found at: http://makeitbreakitfixit.com/2014/02/09/sleeptrack-sleep-apnea-measuring-machine/


/*
Sleep Track v1.2 - Feb 2014
When first powered the serial displays a menu where you can either how previously recorded data or begin recording new data
After you enter the time the device will not track movements until the button is pressed for ~2 seconds. The pin13 LED then
flashes fast for about 10 seconds. After flashing stops and the LED is solid it is calibrating the sensor, during this time
be sure you are lying on your back. Once the LED turns off calibration is complete and recording has begun.
The LED will momentarily blink if a change of direction is detected. The direction change is only detected if user moves to
another direction and stays there for at least 3 seconds (to prevent false positives).

TO DO:
1) Clean up code and create libraries/classes for much of the code to simplify the main code.

2) At the moment the RTC is too bulky to incorporate in to the main design, so the time must be entered manually each time the
device is powered. Future plans to create a docking cradle which will output a constant stream of the current time. So when
the device is plugged in it will automatically sync to the current time.

3) At the moment the device only stores one night of information. This means after every night the device must be connected to
the computer download previous nights recording and clear the memory. Future plans to store multiple days worth of data and
possibly have this data transferred across to the docking station, to then be stored in an SD card.

NOTE:
The current code is fairly stable, however, when I tried to add additional code I saw unexpected behaviour with
how the serial.print behaves. I believe this is related to the Arduino running out of memory (SRAM).
So at this point I need to clean up the code (ie. remove so many global variables, for starters).
*/


CHANGELOG:

v1.2
- Fixed time keeping issues which caused length of times reported on a side to be off
- Increased code efficiency by removing or changing some global variables and changing. There is still much left to do here
