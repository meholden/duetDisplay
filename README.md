Hey thanks for looking at my project!

# Overview

This project is a strange one but works for me.  
I have a 3D printer that uses the [Duet Wifi](https://duet3d.com/DuetWifi?manufacturer_id=11) control board, which is a great board for controlling 3D printers.
I use the web interface to upload gcode files and monitor progress, and don't *really* need a display at the printer 
(duet does make the [PanelDue](https://duet3d.com/PanelDue) which is overkill for my needs but seems pretty thorough)

But there are a couple of tasks to do at the printer that required me to take out my phone, 
and also occasionally in a long print the wifi would be lost and I would be unable to pause the print to change filament colors.

So this project came about.  It allows you to make a display that costs less than the PanelDue with three screens:
  * Printing status
  * Pre-heat bed and extruder
  * Pause print and load new filament

You of course could implement more functions, these were what I wanted.  

So, if: you have the pricy Duet Wifi *and* you're too cheap to buy the PanelDue *and* you are handy with arduinos, this is your project!

# Duet Data

The data from the duet wifi comes from a serial port.  There is a serial port for the PanelDue, and it uses gcode to communicate.
All the data for my display comes with a single command.  M408 causes the Duet to send a string with many status states.  
Try it at the web interface to see what happens!

# Arduino stuff
First, you need to turn off checksums for the PanelDue serial port
