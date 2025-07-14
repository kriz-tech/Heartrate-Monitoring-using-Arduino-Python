# Heartrate-Monitoring-using-Arduino-Python
A real-time simple heart rate-measuring biomedical system via a Pulse Sensor attached to an Arduino UNO and plotted via a GUI with a Python foundation. Real-time BPM, noise-removal signal processing, health class, and emoji-driven dynamic UI in response to the patient's state are aspects included in the project.
components required:

Component	    Quantity	           Description
Arduino UNO	      1	           Microcontroller for reading sensor data
Pulse Sensor	  1	           Measures heartbeat via light reflection
USB Cable	      1	           For serial communication with PC
Jumper Wires	Several	       To connect the sensor to Arduino
Computer	      1	           Runs Python GUI and processes data
Python Libraries   -	       pyserial, numpy, tkinter, emoji, PIL


Workflow:

Start GUI – User enters the patient’s name.

Calibration Phase – Sensor stabilizes for 5 seconds.

Measurement Phase – 20 seconds of heart rate data is collected.

Signal Smoothing – Raw data is filtered using moving average.

Peak Detection – Peaks corresponding to heartbeats are identified.

BPM Calculation – BPM is computed from time intervals between peaks.

Display Results – Final BPM and health status are shown in GUI.


User Input → Calibration → Data Collection (Arduino) → Serial Transfer → Signal Smoothing → Peak Detection → BPM Calculation →

Condition Classification → GUI Display
How the Sensor will work?

The pulse sensor operates using Photoplethysmography (PPG):

It consists of an LED and a photodiode.

The LED emits light onto the skin.

The amount of reflected light changes with blood volume in the tissue.

The photodiode detects these changes, producing an analog signal.

This analog waveform is processed to determine heartbeats.
circuit
![443129336-c6659e35-6423-4325-a319-dec7d01d65bb]

(https://github.com/user-attachments/assets/705c5e3c-ee37-4b69-8ebc-4c744c701a0d)


Connections:

Pulse Sensor Wire	Connects to Arduino UNO Pin	Description
Red	5V	Powers the pulse sensor
Black	GND	Common ground
Purple	A0	Reads analog signal from sensor
pins in sensor

Based on the BPM, the program determines the heart condition:

    BPM = 0 → No pulse detected → ❌

    BPM < 60 → Low Heart Rate → ⚠️

    60 ≤ BPM ≤ 100 → Normal → ✅

    BPM > 100 → High Heart Rate → 🚨
Prerequisites

Python 3.8+

Arduino IDE

Pulse Sensor connected to Arduino (A0 pin)

Arduino must be flashed with the serial sending sketch
