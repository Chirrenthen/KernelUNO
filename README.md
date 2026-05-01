# KernelUNO v1.0 - a Ram filesystem emulator and simple shell for your arduino UNO R3 

# Features

- Unix-like Shell with 24 commands

- GPIO support

<img width="769" height="634" alt="1" src="https://github.com/user-attachments/assets/5d9940bc-8b05-48c4-92f6-c0d2b9dccbed" />


# Commands
## Filesystem
``` bash
- `uname`      # OS and Platform info
- `cd`         # Change directory
- `ls`         # list files in directory
- `pwd`        # Print current working directory
- `mkdir`      # Create new directory in current path
- `touch`      # Create empty file in current path
- `cat`        # Display conents in a file
- `echo`       # Write into a text file
- `rm`         # Remove a file or dirctory
- `info`       # Show metadata of a file or directory
```
## Hardware Control
``` bash
- `pinmode`    # Configure pins as INPUT/OUTPUT
- `write`      # Write a pin HIGH/LOW
- `read`       # Read value of a pin
- `gpio`       # Set pin HIGH, LOW, or flip its current state
- `gpio vixa`  # LED disco mode(flashes for count cycles)
- `pwm`        # Analog write a pwm value
```
## System Commands
``` bash
- `sh`         # Runs script stored in a file
- `uptime`     # Uptime of the board
- `dmesg`      # Shows the last 6 kernel log messages with timestamps
- `df`         # Print current free RAM
- `free`       # Print current free RAM
- `whoami`     # Prints user
- `clear`      # Visually clears the screen
- `reboot`     # Performs a reset
```

# TODO

- [ ] eeprom
- [ ] i2c
- [ ] pwm (done)
- [ ] date cmd
- [ ] alias cmd
- [ ] 'slots' cmd

# LICENSE

BSD3 ([Arc1011](https://github.com/Arc1011/KernelUNO))

