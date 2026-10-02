# 🎵 GesMus (AirBand)

**Play musical instruments with your hands. No pads, no taps, no install. Just a webcam.**

🔗 **Live demo:** https://akshat-neeraj.github.io/GesMus/

<!-- ADD YOUR DEMO HERE: record a 10–20 second screen capture of you playing,
     save it in the repo as demo.gif, then keep the line below. -->
![GesMus demo](demo.gif)

GesMus uses your webcam to track your hands in real time and turns finger and hand positions into music. It runs in the browser.

---

## ✋ How the gestures work

| Gesture | What it does |
|---|---|
| **Right hand: number of fingers held up** | Picks the note or chord |
| **Right hand: fist** | Silence (or replays the pattern on drums, piano, guitar, and bass) |
| **Right hand: height** | Volume (higher is louder) |
| **Left hand: open vs. closed** | Tone / brightness (the same rule for every instrument) |
| **Both hands apart** (Chords) | Spreads and widens the chord |

> 💡 **Tip:** Good, even light on your hands matters most. Face a window or lamp instead of sitting backlit or in the dark.

---

## 🎹 Instruments

Chords, Piano, Drums, Guitar, Bass, and Violin. The composer also supports real-sample piano, strings, brass, and woodwind instruments.

## ✨ Features

- **Practice mode** and **Learn mode** to build your skills
- **Songs:** pick a song, hear it played first, or add your own
- **Record** your playing and **download** the recording
- **Composer:** record a melody or rhythm and layer several instrument parts together
- **Loop** and **metronome**
- **Profile** with badges and progress per instrument
- **Settings:** themes (Brass, Ocean, Sunset, Mono), master volume, reverb
- **Privacy mode:** hides the camera background while hand tracking keeps working
- **Save files:** export and import your progress and compositions
- **Keyboard shortcuts:** `1–9`, `0` switch instrument · `P` practice · `L` learn · `J` loop · `R` record · `M` metronome · `?` help

---

## 🧠 How it works

1. The webcam feed is sent frame by frame to **MediaPipe Tasks Vision (`HandLandmarker`)**.
2. MediaPipe returns **21 landmark points per hand** (fingertips, knuckles, wrist) with fixed positions. For example, point 8 is always the index fingertip.
3. MediaPipe only gives raw points. It has no idea what "three fingers" or "a fist" is, so **GesMus has its own gesture logic** that turns the landmark geometry into finger counts, open/closed hand states, and hand height.
4. Those values are mapped to notes, chords, volume, and tone.

MediaPipe is loaded straight from a CDN as an ES module, so there is no build step and no npm install.

## 🛠️ Tech stack

- JavaScript, HTML, CSS
- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker) (`HandLandmarker`)
- Hosted on GitHub Pages

## 🚀 Run it

Open the **live demo** and click **Enable camera & sound**.

To run it locally, serve the folder over `localhost` (for example with VS Code's Live Server). Browsers only allow webcam access on `localhost` or HTTPS, so opening the file directly may not work.

## 🗺️ Status

Actively developed. Ideas and feedback are welcome. Open an issue.

## 👤 Author

**Akshat Neeraj** · [GitHub](https://github.com/Akshat-Neeraj) · [LinkedIn](https://linkedin.com/in/akshat-neeraj)
