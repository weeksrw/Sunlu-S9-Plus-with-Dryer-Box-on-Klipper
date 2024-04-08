# These are the Klipper pinouts that I determined from the Marlin source code.
Based off of this reference: https://reprap.org/forum/read.php?13,837190
```
Digital I/O
Marlin
 |
 |--Klipper
 |----|
 |----|--Marlin Analog
 |----|--|
 v---v---v Marlin Source Pin Name       Klipper Name                                Klipper Pin
D00 PE0
D01 PE1
D02 PE4	    FIL_RUNOUT_PIN              [filament_switch_sensor runout] switch_pin:  ^PE4
D03 PE5	    X_MIN_PIN                   [stepper_x] endstop_pin:                     ^!PE5
D04 PG5	    SERVO0_PIN (BLTouch Servo)  [bltouch] control_pin:                       PG5
D05 PE3	    SERVO2_PIN
D06 PH3	    SERVO1_PIN
D07 PH4	    RAMPS_D9_PIN, FAN1_PIN      [heater_fan fan1] pin:                       PH4	
D08 PH5	    RAMPS_D8_PIN                [heater_bed] heater_pin:                     PH5
D09 PH6	    FAN_PIN                     [fan] pin:                                   PH6	
D10 PB4	    RAMPS_D10_PIN               [extruder] heater_pin:                       PB4
D11 PB5
D12 PB6	    HEATER_DRYBOX_PIN           [heater_generic drybox] heater_pin:          PB6
D13 PB7	    LED_PIN	
D14 PJ1	    Y_MIN_PIN                   [stepper_y] endstop_pin:                     ^!PJ1
D15 PJ0	    Y_MAX_PIN
D16 PH1
D17 PH0
D18 PD3	    Z_MIN_PIN                   [bltouch] sensor_pin:                        ^PD3
D19 PD2	    Z_MAX_PIN
D20 PD1
D21 PD0
D22 PA0	    DRYBOX_PWM_PIN	
D23 PA1
D24 PA2	    E0_ENABLE_PIN               [extruder] enable_pin:                       !PA2
D25 PA3
D26 PA4	    E0_STEP_PIN                 [extruder] step_pin:                         PA4
D27 PA5
D28 PA6	    E0_DIR_PIN                  [extruder] dir_pin:                          !PA6
D29 PA7
D30 PC7	    E1_ENABLE_PIN
D31 PC6
D32 PC5	    Z_MIN_PROBE_PIN
D33 PC4
D34 PC3	    E1_DIR_PIN
D35 PC2
D36 PC1	    E1_STEP_PIN
D37 PC0	    ? BEEPER_PIN
D38 PD7	    X_ENABLE_PIN                [stepper_x] enable_pin:                      !PD7
D39 PG2
D40 PG1	    ?X_SERIAL_TX_PIN
D41 PG0
D42 PL7	    ?Z_SERIAL_TX_PIN
D43 PL6
D44 PL5	    ?E0_SERIAL_TX_PIN
D45 PL4
D46 PL3	    Z_STEP_PIN                  [stepper_z] step_pin:                        PL3
D47 PL2
D48 PL1	    Z_DIR_PIN                   [stepper_z] dir_pin:                         PL1
D49 PL0
D50 PB3
D51 PB2
D52 PB1
D53 PB0	    ? SDSS
D54 PF0 A00 X_STEP_PIN                  [stepper_x] step_pin:                        PF0
D55 PF1 A01 X_DIR_PIN                   [stepper_x] dir_pin:                         !PF1
D56 PF2 A02 Y_ENABLE_PIN                [stepper_y] enable_pin:                      !PF2
D57 PF3 A03
D58 PF4 A04
D59 PF5 A05 ?Y_SERIAL_TX_PIN
D60 PF6 A06 Y_STEP_PIN                  [stepper_y] step_pin:                        PF6
D61 PF7 A07 Y_DIR_PIN                   [stepper_y] dir_pin:                         !PF7
D62 PK0 A08 Z_ENABLE_PIN                [stepper_z] enable_pin:                      !PK0
D63 PK1 A09 X_SERIAL_RX_PIN
D64 PK2 A10 Y_SERIAL_RX_PIN
D65 PK3 A11 TEMP_DRYBOX_PH_PIN
D66 PK4 A12 TEMP_DRYBOX_CENTER_PIN      [temperature_sensor drybox_center] sensor_pin:PK4
D67 PK5 A13 TEMP_0_PIN                  [extruder] sensor_pin:                       PK5
D68 PK6 A14 TEMP_BED_PIN                [heater_bed] sensor_pin:                     PK6
D69 PK7 A15 TEMP_DRYBOX_RTH_PIN         [heater_generic drybox] sensor_pin:          PK7
D70 PG4
D71 PG3
D72 PJ2
D73 PJ3
D74 PJ7
D75 PJ4
D76 PJ5
D77 PJ6
D78 PE2
D79 PE6
D80 PE7
D81 PD4
D82 PD5
D83 PD6
D84 PH2
D85 PH7 DRYBOX_AUTO_FAN_PIN             [fan_generic drybox_fan]pin:                 PH7
```
