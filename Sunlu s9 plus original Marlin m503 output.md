SENDING:M503
echo:  G21    ; Units in mm (mm)
echo:; Filament settings: Disabled
echo:  M200 S0 D1.75
echo:; Steps per unit:
echo: M92 X80.00 Y80.00 Z400.00 E95.88
echo:; Maximum feedrates (units/s):
echo:  M203 X500.00 Y500.00 Z10.00 E50.00
echo:; Maximum Acceleration (units/s2):
echo:  M201 X500.00 Y500.00 Z100.00 E5000.00
echo:; Acceleration (units/s2): P<print_accel> R<retract_accel> T<travel_accel>
echo:  M204 P500.00 R1000.00 T500.00
echo:; Advanced: B<min_segment_time_us> S<min_feedrate> T<min_travel_feedrate> X<max_x_jerk> Y<max_y_jerk> Z<max_z_jerk> E<max_e_jerk>
echo:  M205 B20000.00 S0.00 T0.00 X8.00 Y8.00 Z0.40 E5.00
echo:; Home offset:
echo:  M206 X0.00 Y0.00 Z0.00
echo:; Auto Bed Leveling:
echo:  M420 S0 Z10.00
echo:  G29 W I0 J0 Z-0.24500
echo:  G29 W I1 J0 Z-0.20500
echo:  G29 W I2 J0 Z-0.15250
echo:  G29 W I3 J0 Z-0.08750
echo:  G29 W I0 J1 Z-0.18250
echo:  G29 W I1 J1 Z-0.15500
echo:  G29 W I2 J1 Z-0.05000
echo:  G29 W I3 J1 Z-0.01000
echo:  G29 W I0 J2 Z-0.14500
echo:  G29 W I1 J2 Z-0.05750
echo:  G29 W I2 J2 Z0.00750
echo:  G29 W I3 J2 Z0.07000
echo:  G29 W I0 J3 Z-0.03500
echo:  G29 W I1 J3 Z0.00750
echo:  G29 W I2 J3 Z0.11000
echo:  G29 W I3 J3 Z0.15750
echo:; PID settings:
echo:  M301 P20.84 I1.96 D55.47
echo:; Power-Loss Recovery:
echo:  M413 S1
echo:; Z-Probe Offset (mm):
echo:  M851 X-28.50 Y4.00 Z-2.90
echo:; Filament load/unload lengths:
echo:  M603 L0.00 U100.00
echo:; Filament runout sensor:
echo:  M412 S3 D6.00
