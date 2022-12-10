# CaribouLite Production Results
This repository contains the production testing results for each and every board that is produced.

# Data Types
The repo contains the following sub-directories
 - boards - A YAML file for each tested board
 - testers - A YAML file for each tester system
 - events - Production events

## Boards sub-directory
This sub-directory contains production files as follows:
- Filename:

  [DATE]_[SERIAL_NUMBER]_[RES].yml
  
  `DATE` - the file writing date and time with the following structure: yyyy_mm_dd_HH_MM_SS
  
  `SERIAL NUMBER` - the boards randomly generated serial number which is based on its uuid (generated and written to the EEPROM upon production).
  
  `RES` - the test result summary. Either 'P' (Pass) or 'F' (Fail)
  
- File internal structure
```
version: 1
file_type: cariboulite_test_results
date: date/time format
product_name: cariboulite_full_r2.8 or cariboulite_ism_r2.8
rpi_serial_number: serial_number
hat_powermon_serial_number: serial_number
summary_test_results: pass / fail
test_results:
   rpi_id_eeprom: pass / fail
   rpi_driver_caribou: pass / fail
   fpga_programming: pass / fail
   fpga_versions: pass / fail
   fpga_communication: pass / fail
   fpga_reset: pass / fail
   fpga_pmod: pass / fail
   fpga_switch: pass / fail
   fpga_leds: pass / fail
   fpga_smi: pass / fail
   mixer_reset: pass / fail / na
   mixer_communication: pass / fail / na
   mixer_version_id: pass / fail / na
   modem_reset: pass / fail
   modem_version: pass / fail
   modem_leds: pass / fail
   model_configuration: pass / fail
   modem_communication: pass / fail
   modem_interrupt: pass / fail
   current_measurement: pass / fail
   rf_loopback: pass / fail
power_measurements_mwatt:
   fpga_only: [value]
   modem_rx_no_mixer: [value]
   modem_tx_no_mixer: [value]
   mixer_no_modem: [value]
```

## Testers
Each tester RPI + hat-powermon have their serial numbers and information.
Each file in this sub-directory contains the decription of the tester setup:
```
version: 1
file_type: cariboulite_tester_setup
date: date / time format
rpi_serial_number: serial_number
hat_powermon_serial_number: serial_number
```

## Events
