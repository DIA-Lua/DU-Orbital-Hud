## DU-Orbital-Hud
Dual Universe HUD with orbital information, braking distances, and Rezoix's pitch/roll hud with some fixes
Works with Command Seat and Hover Seat, not Cockpit

If you wish to save your current config, right click your seat and Copy Lua Configuration to Clipboard, and save it somewhere

# Usage
Click on **D_flying_construct_MIN_HUD.conf** or FULL_HUD above.  MIN_HUD gets rid of the extra UI clutter near the cursor on the Rezoix hud.  On the top right, right click the 'RAW' button and click Save Link As...

Save the file to *%ProgramData%\Dual Universe\Game\data\lua\autoconf\custom*, the filename does not matter (as long as it's still .conf)


In-game, right click your seat and go to *Advanced -> Update custom autoconf list*

Then *Advanced -> Run Custom Autoconfigure -> D's Flying Construct with HUD*

This should set everything up and you're good to go

# Warnings
If you are in atmosphere, the Max Brake Distance listed on the Interplanetary widget will be inaccurate, since it will be using your atmospheric brakes to calculate.  Once you enter space, it should be accurate.

## Controls
Alt+1 and Alt+2 (Option1 and Option2) to scroll between target planets for the Interplanetary Helper.  This widget will not display if no planet is selected (ie you must press one of these hotkeys after entering the seat in order to show the widget)

## Customization
You may edit the R,G,B LUA parameters to set the main color of the HUD


### Features
**Rezoix HUD** (i.e. pitch/roll/yaw indicators), with LUA-parameter RGB values so you can set the base color, and with fixes (yaw is displayed in space properly instead of pitch, throttle indicator is fixed, gyro no longer required) - https://github.com/Rezoix/DU-hud

**Orbital Information widget** - Shows apoapsis, periapsis, apogee, perigee, eccentricity for the nearest planet, using these libraries: https://gitlab.com/JayleBreak/dualuniverse/-/tree/master/DUflightfiles/autoconf/custom

**Interplanetary Helper** - Use Alt+1 and Alt+2 to cycle through target planets.  Shows distance, travel time (including acceleration, travel, and braking - absolute total), brake time (current and max).  Note that currently, Brake Time is inaccurate if you're inside atmosphere.  Once you're in space, it will properly read the space brakes and give the correct values

**Auto-Brake** - Use Alt+3 when you have a target selected with the Interplanetary Helper, and it will toggle Auto-Brake.  The script will automatically engage the brake when within the max braking distance for that planet.  This does not guarantee that you will not hit the planet - even with Auto-Brake, do not aim directly at the planet.  It targets an end speed of 0, though you will generally have a much higher end speed, so has some leeway.  It will continue braking until stable orbit is achieved, if possible from the trajectory.

**AutoPilot** - Use Alt+4 when you have a target selected with the Interplanetary Helper, and you are in space with clear line of sight to the target.  The script will align to the optimal vector to place you in a 1SU orbit from the target, accelerate, cut engines when appropriate, and brake until orbit is achieved.  
**NOTE** As of right now, this isn't well tested.  I've used it in one flight, and it seemed to do well, but I don't know how well it does at making an orbit.  In its current state, do not rely on this script to finish braking into orbit while you sleep.  

**Brake Indicator/Toggle** - Brake is now a toggle, and is on by default when entering the seat.  There is an onscreen text indicator to show you when the brake is on
