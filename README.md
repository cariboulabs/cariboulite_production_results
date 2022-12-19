# CaribouLite Production Results
This repository contains the production testing results for each and every board that is produced.

# Data Types
The repo contains the following sub-directories
 - boards - A YAML file for each tested board
 - testers - A YAML file for each tester system
 - events - Production events
 - scripts - python automated scripts for visualization and monitoring

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
 ...
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
