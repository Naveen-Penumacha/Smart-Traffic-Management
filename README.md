# 🚦 Smart Traffic Management System Using Background Subtraction
📌 Overview

Urban traffic congestion is a growing challenge due to rapid urbanization and increasing vehicle numbers. Conventional traffic signals follow static timing, which leads to unnecessary waiting, wasted fuel, and delays — especially problematic for emergency vehicles.

This project proposes an Intelligent and Adaptive Traffic Signal Management System using:

Background Subtraction for real-time vehicle detection and traffic density estimation.

RFID technology for automatic emergency vehicle prioritization.

Raspberry Pi and Arduino Uno for embedded control and signal switching.

By dynamically adjusting traffic signal timing based on real-time vehicle density and prioritizing emergency vehicles, this system aims to reduce congestion, travel time, and environmental impact.

🎯 Key Features

✅ Real-Time Vehicle Detection:
Uses background subtraction algorithms to detect moving vehicles from live camera feeds.

✅ Dynamic Signal Timing:
Allocates signal duration to each lane proportionally to traffic density, with categories for high and low traffic.

✅ Emergency Vehicle Priority:
Detects ambulances and other emergency vehicles using RFID readers and switches signals automatically to clear their path.

✅ Embedded Implementation:
Prototype built using Raspberry Pi, Arduino Uno, webcams, RFID readers/tags, LEDs, and LCD displays.

🧩 System Architecture

The system consists of:

➡️ Camera Module: Captures live video of the intersection.

➡️ Raspberry Pi: Processes video frames, applies background subtraction to detect vehicles, estimates density.

➡️ Arduino Uno: Interfaces with RFID readers to detect emergency vehicle tags and controls signal LEDs.

➡️ RFID Tags and Readers: Emergency vehicles carry passive RFID tags; readers at junctions detect approaching ambulances.

➡️ Traffic Signal LEDs and LCD: Simulates real-world traffic lights and displays lane information and timing.

⚙️ Methodology

🚗 Vehicle Detection

➡️ Initialize webcam on Raspberry Pi.

➡️ Capture video frames.

➡️ Apply background subtraction:

➡️ Use previous frame as background model.

➡️ Subtract current frame to get foreground mask.

➡️ Apply thresholding to detect moving objects.

➡️ Filter contours to count vehicles.

➡️ Categorize lane traffic:

➡️ High density: > threshold → allocate more time (e.g., 20 sec)

➡️ Low density: ≤ threshold → allocate less time (e.g., 10 sec)

🚑 Emergency Vehicle Detection
➡️ Each emergency vehicle carries an RFID tag.

➡️ RFID readers at each lane detect tags.

➡️ If an emergency vehicle is detected:

➡️ Immediately switch signal to green for its lane.

➡️ Pause other lanes until it passes.

📊 Experimental Results

➡️ Prototype: Built using toy vehicles and cardboard intersections.

➡️ Accuracy: Average vehicle detection accuracy ~85% despite shadow interference.

➡️ Emergency Response: RFID-based detection reliably switches signals for ambulances.

➡️ Dynamic Allocation: High-density lanes get longer green signals, minimizing idle time for low-density lanes.

🔧 Hardware Used

➡️ Raspberry Pi (with camera module)

➡️ Arduino Uno

➡️ Passive RFID tags and readers

➡️ LEDs (traffic lights simulation)

➡️ LCD Display (shows timing info)

➡️ Toy vehicles (for prototype)

🧪 Limitations & Future Work

➡️ Shadows and extreme weather can affect detection accuracy.

➡️ Real-world deployment would benefit from advanced background subtraction models.

➡️ Future work may integrate deep learning for improved vehicle and object detection.

📚 References

➡️ The detailed references used for this project are listed in the conference paper and in the REFERENCES.md.
