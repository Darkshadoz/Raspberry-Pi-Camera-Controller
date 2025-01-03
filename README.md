# Controlling Sony A6000 with Raspberry Pi
**CMPT 2200 Project - October 24 2024**

## Functionality Ideas:
- Take photos using set timer with physical button to 
- Display and set time from 3-9s
- Buzzer beep to countdown set timer.
- Take photos after a certain distance.
- Take photos after focused.
- Calculate focus distance and adjust camera focus accordingly
- Assume manual focus).
- Controllable using tkinter or PySide6 UI.
- RGB Led and buzzer to indicate in focus or not.
- White Led and buzzer beep to countdown set timer.
- Red Led and buzzer to indicate photo being shot.
- Recommended Camera Focus for manual mode.
- Image filter

## Hardware Ideas:
- Controller Interface to control camera functionality
- Distance sensor to detect subject distance.

## GUI Ideas:
- Different GUI options available depending on camera mode (autofocus vs manual)
	
## Library Used:

[Libgphoto2 (C Library)](http://www.gphoto.org/doc/)

[Python-gphoto2 (Python interface or binding to gphoto2)](https://pypi.org/project/gphoto2/)

PIL

Tkinter

## Library Installations:
```
sudo apt install libexif12 libgphoto2-6 libgphoto2-port12 libltdl7
```
```
sudo apt-get install gphoto2 
```

## Useful Commands
```
gphoto2 --list-config
```
```
gphoto2 --get-config <setting>
```


## Components:
- 1x Buzzer
- 1x Ultrasonic Sensor
- 3x 2 Pin Button
- 1x RGB LED
- 1x Red LED
- ?x Male-to-Male Cable
- ?x Male-to-Female Cable
- 1x Sony A6000 Camera (Supported Cameras: http://www.gphoto.org/proj/libgphoto2/support.php)
- 1x Usb cable

## Implementation Ideas:

- CalculateDistance function: calculate distance from the ultrasonic sensor to the subject
- TakePhoto: Standard countdown of 3. Take picture and save to a folder on the desktop? Or sd not sure
- CountdownTimer: Countdown timer function, use forloop and time.sleep(1). TakePhoto after countdown.
- Countdown is a global variable! Can be adjusted at anytime. Default is 3. Basis for all takePhoto function.
- TakePhotoAfterFocused: Press button on UI -> Run to distance -> Get that distance ->Focus base on distance ->countdown -> -takephoto
- TakePhotoAfterDistance: Press button on UI with set distance -> walk to distance ->beep to notify -> focus -> countdown -> takephoto
