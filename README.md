# Room Light Control System

## Overview

This project is a Raspberry Pi-based room light control system with a graphical user interface (GUI) created using Python Tkinter. It allows the user to select a room and control its lighting. The Living Room light supports adjustable brightness using PWM, while the Bathroom and Closet lights can be switched on and off.

## Features

* GUI-based room selection using Tkinter.
* Control for three rooms:

  * Living Room
  * Bathroom
  * Closet
* Adjustable Living Room brightness from 0% to 100%.
* PWM control for smooth brightness adjustment.
* Simple radio-button interface for selecting rooms.
* Exit button that safely turns off all lights and cleans up GPIO pins.

## Hardware Requirements

* Raspberry Pi
* 3 LEDs or lights
* Suitable resistors for LEDs
* Jumper wires
* Breadboard
* Power supply

## GPIO Configuration

| Room        | GPIO Pin | Control        |
| ----------- | -------: | -------------- |
| Living Room |  GPIO 18 | PWM brightness |
| Bathroom    |  GPIO 27 | ON/OFF         |
| Closet      |  GPIO 22 | ON/OFF         |

## Software Requirements

* Python 3
* Tkinter
* RPi.GPIO library
* Raspberry Pi OS

## How It Works

When the program starts, all room lights are turned off. The user can select a room using the radio buttons.

* **Living Room:** The brightness can be adjusted using the slider from 0% to 100%.
* **Bathroom:** Selecting the bathroom turns its light ON.
* **Closet:** Selecting the closet turns its light ON.
* Selecting another room automatically turns the previously selected non-PWM light off.
* Clicking **Exit** turns off all lights, stops PWM, cleans up the GPIO pins, and closes the application.

## Running the Program

1. Connect the LEDs to the specified Raspberry Pi GPIO pins.
2. Save the Python code as:

```text
room_light_control.py
```

3. Open the terminal on the Raspberry Pi.
4. Run the program using:

```bash
python3 room_light_control.py
```

5. Use the GUI to select rooms and control the lights.

## Safety and Cleanup

The program uses `GPIO.cleanup()` when exiting to reset the GPIO pins safely. The `Exit` button also turns all lights off before closing the application.

## Learning Outcome

This project demonstrates how Python can be used with Raspberry Pi GPIO to control physical components through a graphical interface. It also provides practical experience with PWM, event-driven programming, Tkinter widgets, and safe GPIO cleanup.
