gpstime
=======

Script that sets system time through a GPS.

I had a problem with my Raspberry Pi where ntp wouldn't update the clock.  It is intended functionality that ntpd won't update the system clock if it isn't within 4 hours of its ntp server(s).
So I needed something to get the clock set close enough to where it needed to be so that ntp could take over.  I found this script (yay!)


Meant for use with SOC devices that either lack a real time clock or internet connection (such as a raspberry pi), gpstime will work with your GPS through the GPSd (http://gpsd.berlios.de/) utility to access the current time, and will apply that to your system clock.

Usage examples include remote data logging and chartplotters. I use this module to set the time on my raspberry pi which I use as a chartplotter with OpenCPN. In order to ensure that the tide tables are displaying the correct information, the system time must be set correctly.

This script requires the gps python modules included with GPSd to acess the NMEA stream. I have included these modules with the download.

In order to function properly, your GPS must be connected and GPSd must be running (type 'gpsd' in the terminal).

There are far more accurate ways to receive and set time using NTP and PPS. But gpstime has a much lower overhead and is fast to get things going. If you are looking for extreme time accuracy (milliseconds), I recommend looking into NTP/PPS. 



This code was originally forked from http://code.google.com/p/gpstime/
