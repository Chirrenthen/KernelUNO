# KernelUNO v1.0

A Unix-like shell and RAM filesystem for Arduino UNO R3. Write files, control GPIO pins, read sensors, and run simple scripts all from the serial terminal.

<img width="769" height="659" alt="554" src="https://github.com/user-attachments/assets/82aa5f0c-bf22-4f83-865a-ba3b4258011e" />


# Commands:


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

## Planned Features

- EEPROM support
- I2C interface
- Date cmd
- neofetch cmd

## License

BSD3 - Original by [Arc1011](https://github.com/Arc1011/KernelUNO)

