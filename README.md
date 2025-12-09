Freak Detector — Real-Time Gesture-Controlled Meme Player

Freak Detector is a real-time computer-vision system that detects facial + hand gestures and instantly plays a meme (GIF / video / image) based on your reaction.

Powered by **MediaPipe**, **OpenCV**, and **Python**, this project tracks your face and hands live through your webcam and responds with the perfect meme.

Features

**Face Gestures**

| Gesture                    | Description                                   | Meme              |
| -------------------------- | --------------------------------------------- | ----------------- |
| 😛 Tongue out + head shake | Shake head sideways while sticking tongue out | `freaky-orca.gif` |
| 🟢 Head nod                | Quick up-down movement                        | `ishowspeed.gif`  |
| 😐 Idle stare              | Looking straight at the camera, no movement   | `monkeytruth.jpg` |



**Hand Gestures**

| Gesture                   | Description                        | Meme                 |
| ------------------------- | ---------------------------------- | -------------------- |
| 🤲 Rubbing palms together | Hands close, moving back and forth | `freaky-sonic.mp4`   |
| 😩 Both hands on head     | “Oh no” reaction                   | `ishowspeed-wow.gif` |
| ☝️ One finger up          | Index finger raised                | `monkeyrealize.jpeg` |
| 🤔 Hand on chin           | Thinking pose                      | `monkeythink.jpg`    |
| 👍 Thumbs up              | Positive gesture                   | `thumbsupmonkey.png` |


How It Works

The system uses:
**MediaPipe FaceMesh**

* Tracks 468 facial landmarks
* Detects mouth/tongue, head motions, eye direction, and idle behavior

**MediaPipe Hands**

* Tracks 21 landmarks per hand
* Detects gestures like:
  * rubbing palms (oscillation tracking)
  * one-finger-up
  * hands on head
  * thumbs up
  * hand on chin proximity
  * hand convergence (two-hand gestures)

**OpenCV**

* Webcam capture
* Frame rendering
* GIF/image/video playback side-by-side with webcam

**Custom Gesture Engine**

* Gesture cooldown
* Sustained detection
* Priority system (so only the correct meme plays)



Output Display

The screen is split into two parts:

```
+---------------------------+---------------------------+
|         Webcam            |       Meme/GIF/Video      |
+---------------------------+---------------------------+
```

Whenever a gesture is detected, the right side updates instantly.


Project Structure

```
/freak-detector
│── freakdetector.py
│── /memes
│     ├── freaky-orca.gif
│     ├── freaky-sonic.mp4
│     ├── ishowspeed.gif
│     ├── ishowSpeed-wow.gif
│     ├── monkeyrealize.jpeg
│     ├── monkeythink.jpg
│     ├── monkeytruth.jpg
│     ├── thumbsupmonkey.png
```

---

Installation

1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/freak-detector.git
cd freak-detector
```

2️⃣ Install Python dependencies

```bash
pip install opencv-python mediapipe pillow numpy
```

(You may need `pip install opencv-contrib-python` if using older OpenCV).

---

▶️ Running the Program

```bash
python freakdetector.py
```

Make sure your webcam is enabled.

The right side of the window will change whenever a gesture is detected.



Customization

You can easily:

✔ Add new gestures
✔ Replace memes in the `/memes/` folder
✔ Adjust gesture sensitivity
✔ Change cooldown times
✔ Add speech or audio reactions

Just edit the gesture detector functions or the filepath constants.

Requirements

* Python 3.10+
* OpenCV
* MediaPipe
* Pillow
* Webcam (720p recommended)


Contributing

Pull requests are welcome!

If you'd like to add:

* More gesture types
* Meme packs
* A GUI
* Multi-person support

Feel free to fork and contribute.

License

This project is open-source under the **MIT License**.

Have Fun Freaking Out!

This project reacts to your emotions in real-time —
let the memes fly 

