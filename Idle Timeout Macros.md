Since the Sunlu S9 Plus must be on for the dryer box to operate. The default idle_timeout is set to 10 minutes, causing the dryer box will shutoff before intended.  Here are some macros you can add to your printer.cfg (or other file) to change the idle_timeout to the value you want.  If you leave the machine unattended, the dryer box will shutoff after the new timeout value that you can set with the macros.

```
#####################################################################
# TIMEOUT MACROS
# Used to increase the idle_timeout so dryer box can continue to operate
#####################################################################

[idle_timeout]  # you may already have this setting in your configuration
gcode:
# This will be your default idle timeout (in seconds) to wait before turning off motors and heaters
# This will also be how long your bed stays heated during a filament runout.
timeout: 600       # 10 minutes (default)
#timeout: 7200      # 2 hours
#timeout: 21600     # 6 hours
#timeout: 29000     # 8 hours
#timeout: 43200     # 12 hours

# These are macros you can add to your Mainsail or Fluidd dashboard to modify the idle_timeout
[gcode_macro Timeout_2]   # 2 hours  (2*60*60)
gcode:
  SET_IDLE_TIMEOUT TIMEOUT=7200

[gcode_macro Timeout_4]   # 4 hours  (4*60*60)
gcode:
  SET_IDLE_TIMEOUT TIMEOUT=14400

[gcode_macro Timeout_6]   # 6 hours  (6*60*60)
gcode:
  SET_IDLE_TIMEOUT TIMEOUT=21600

[gcode_macro Timeout_8]   # 8 hours  (8*60*60)
gcode:
  SET_IDLE_TIMEOUT TIMEOUT=29000

[gcode_macro Timeout_12]   # 12 hours  (12*60*60)
gcode:
  SET_IDLE_TIMEOUT TIMEOUT=43200

[gcode_macro Timeout_Configfile]   # Reset value from configfile
gcode:
  SET_IDLE_TIMEOUT TIMEOUT={printer.configfile.settings.idle_timeout.timeout}

```
