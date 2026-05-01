# KernelUNO v1.0

A Unix-like shell and RAM filesystem for Arduino UNO R3. Write files, control GPIO pins, read sensors, and run simple scripts all from the serial terminal.

<img width="769" height="634" alt="1" src="https://github.com/user-attachments/assets/5d9940bc-8b05-48c4-92f6-c0d2b9dccbed" />

## Getting Started

Connect your Arduino UNO R3 via USB and open the Serial Monitor at 115200 baud. You'll see the prompt:

```
root@arduino:/# 
```

Type `help` to see all available commands.

## File System Commands

### ls
List contents of current directory.

```
root@arduino:/# ls
home/  dev/  
```

### pwd
Print working directory path.

```
root@arduino:/# pwd
/
```

### cd [directory]
Change directory. Use `..` to go back to root or `/` to return to root.

```
root@arduino:/# cd home
root@arduino:/home/# 
```

### mkdir [name]
Create a new directory.

```
root@arduino:/home/# mkdir mydir
OK.
```

### touch [name]
Create a new empty file.

```
root@arduino:/home/# touch myfile
OK.
```

### cat [file]
Read and print file contents.

```
root@arduino:/home/# cat myfile

```

### echo [text] > [file]
Write text to a file. The `>` redirects output to the file.

```
root@arduino:/home/# echo hello > myfile
Saved.
root@arduino:/home/# cat myfile
hello
```

### rm [name]
Delete a file or directory. Removes recursively if it's a directory.

```
root@arduino:/home/# rm myfile
Removed.
```

### info [name]
Get details about a file or directory (name, type, size in bytes).

```
root@arduino:/home/# info mydir
Name: mydir
Type: Directory
Size: 0 bytes
```

## GPIO Commands

### pinmode [pin] [in/out]
Configure a GPIO pin as input or output.

```
root@arduino:/# pinmode 13 out
Pin set to OUTPUT
```

### write [pin] [high/low]
Set a pin to HIGH or LOW.

```
root@arduino:/# write 13 high
Write OK.
```

### read [pin]
Read the current value of a pin (0 or 1).

```
root@arduino:/# read 13
Pin 13 value: 1
```

### gpio [pin] [on/off/toggle]
Quick way to control a pin. `on` sets it HIGH, `off` sets it LOW, `toggle` switches the state.

```
root@arduino:/# gpio 13 on
GPIO 13 ON
```

### gpio vixa [count]
Fun disco mode. Cycles through pins 2-13, blinking LEDs repeatedly (default 10 times).

```
root@arduino:/# gpio vixa 5
LED DISCO MODE!
Disco finished!
```

### pwm [pin] [0-255]
Set PWM (pulse width modulation) on a pin. Value from 0-255 controls brightness/speed.

```
root@arduino:/# pwm 3 128
PWM pin 3 set to 128
```

## System Commands

### uname
Show kernel and hardware information.

```
root@arduino:/# uname
KernelUNO v1.0
Kernel: Arduino AVR
Hardware: Arduino UNO
RAM: 1234 bytes free
```

### uptime
Show how long the system has been running.

```
root@arduino:/# uptime
up 0h 2m 15s
```

### dmesg
View kernel messages (boot and recent commands).

```
root@arduino:/# dmesg
=== KERNEL MESSAGES ===
[0] Kernel initialized
[0] Filesystem mounted
[1] Pin 13 set to OUTPUT
```

### df / free
Show available RAM in bytes.

```
root@arduino:/# free
Free RAM: 1234 bytes
```

### whoami
Print current user (always root).

```
root@arduino:/# whoami
root
```

### clear
Clear the screen by printing blank lines.

```
root@arduino:/# clear
```

### reboot
Restart the Arduino.

```
root@arduino:/# reboot
Rebooting...
```

## Script Execution

### sh [script_file]
Execute a shell script. Commands in the script must be separated by semicolons (`;`).

```
root@arduino:/# echo "write 13 high;write 12 high" > blink.sh
Saved.
root@arduino:/# sh blink.sh
[sh:1] write 13 high
Write OK.
[sh:2] write 12 high
Write OK.
[sh] done.
```

## How It Works

The code manages a virtual filesystem stored in RAM:
- Maximum 10 files/directories
- Max 32 bytes per file content
- 12 character names
- Automatic `/home` and `/dev` directories created on boot
- `/dev/pin2`, `/dev/pin3`, `/dev/pin4` are special files for GPIO

GPIO control uses standard Arduino functions: `pinMode()`, `digitalWrite()`, `digitalRead()`, and `analogWrite()`.

Input is buffered from the serial connection and parsed line-by-line. Commands are case-insensitive.

## Planned Features

- EEPROM support
- I2C interface
- Date command
- Alias command
- File slot management

## License

BSD3 - Original by [Arc1011](https://github.com/Arc1011/KernelUNO)

