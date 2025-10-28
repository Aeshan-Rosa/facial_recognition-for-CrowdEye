
# 🧠 facial_recognition-for-CrowdEye

Facial recognition module for the **CrowdEye Smart Passenger Monitoring System**.  
This Python application performs **real-time identification** using webcam video feed and a directory of known face images.

---

## 🚀 What This System Does

✅ Detects faces using webcam (OpenCV)  
✅ Recognizes known individuals using deep learning encodings  
✅ Marks labels directly on the live video stream  
✅ Shows **Unknown** for unmatched faces  
✅ Easy to update — just add images to `known_faces/`  
✅ Supports multiple people in a single frame  

---

## 🧩 Project Structure

facial_recognition-for-CrowdEye/
├── facial_recognition.py      # Main script
└── known_faces/               # Image database of known users

> 📝 To add a new person, simply drop 1 or more of their photos into `known_faces/`.

---

## 🖥️ Live System Workflow

Webcam Feed → Face Detection → Face Encoding → Matching → Display with Labels

A 128-dimensional facial encoding is generated and compared against known encodings in memory.

---

## 🔧 Installation

Ensure Python 3.8+ is installed.

Install dependencies:

```bash
pip install --upgrade pip
pip install opencv-python face_recognition numpy

⚠️ If installation errors occur for face_recognition, install CMake & C++ Build Tools:
	•	Windows: Visual Studio Build Tools
	•	macOS/Linux: cmake g++ packages

⸻

▶️ Run the Program

python facial_recognition.py

	•	A webcam window opens
	•	Press Q to exit

⸻

👤 Adding New Faces

Add images into known_faces/ using either method:

✅ All images in the root folder

known_faces/
 ├── Aeshan_1.jpg
 ├── Aeshan_2.jpg
 └── John.jpg

OR

✅ Separate folders per person

known_faces/
 ├── Aeshan/
 │   ├── 1.jpg
 │   └── 2.jpg
 └── John/
     └── 1.jpg

Better results come from front-facing images with good lighting.

⸻

⚙️ Performance & Matching Settings

You can modify these inside the script:

Config	Purpose
tolerance	Lower = stricter match (0.4–0.6 recommended)
model	hog (CPU-fast) or cnn (GPU-accurate)
Frame resize	Improves FPS during livestream


⸻

🔄 Updating the System

Pull the latest version:

git pull origin main

To update face profiles:
✅ Add/remove images in known_faces/
✅ Re-run program — it automatically re-encodes

⸻

🐛 Troubleshooting

Issue	Solution
Black screen / no camera	Change webcam index (0 → 1)
Slow performance	Resize frames, use hog model
Incorrect recognition	Add more photos per person / adjust tolerance
dlib failing to install	Install CMake & C++ build tools


⸻

🔐 Ethical & Privacy Considerations

This system processes biometric identity data.
Use responsibly:

✅ Obtain consent
✅ Protect stored face images
✅ Follow local data protection rules

⸻

🌱 Future Improvements (Planned)
	•	Face encoding caching (faster startup)
	•	Live backend sync with CrowdEye central system
	•	Liveness / anti-spoofing detection
	•	Full hardware deployment for bus entry validation
	•	GPU support for high throughput

⸻

💡 Credits
	•	face_recognition (dlib encodings)
	•	OpenCV (video capture)
	•	NumPy (array operations)

⸻
