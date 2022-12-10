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
   - rpi:
      - hat_eeprom: pass / fail
      - driver_caribou: pass / fail
   - fpga:
      - programming: pass / fail
      - reset: pass / fail
      - communication: pass / fail
      - versions: pass / fail
      - pmod: pass / fail
      - switch: pass / fail
      - leds: pass / fail
      - smi: pass / fail
   - modem:
      - reset: pass / fail
      - version: pass / fail
      - leds: pass / fail
      - configuration: pass / fail
      - communication: pass / fail
      - interrupt: pass / fail
   - mixer:
      - reset: pass / fail / na
      - communication: pass / fail / na
      - version: pass / fail / na
   - power_measurements: pass / fail
   - power:
      - fpga_only: [value]
      - modem_rx_no_mixer: [value]
      - modem_tx_no_mixer: [value]
      - mixer_no_modem: [value]   
   - rf:
      - loopback: pass / fail
      - tx_power: pass / fail
      - rssi: pass / fail
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
Production events contain:
 - Production day initiation
 - Failing board

The file here is a simple output log file for each tester RPI.
