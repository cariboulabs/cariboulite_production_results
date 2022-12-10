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

```
