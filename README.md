# Able Cursor

Hands-free computer control on the webcam you already own, for people whose hands do not obey them.
Built for **MISSION'26 Experto Innovatum** (Software Solutions for the Specially Abled), VIT Chennai.

**Live site:** https://YOURUSERNAME.github.io/able-cursor/

> A hackathon prototype. Not a certified medical device. Accuracy has not been measured in a formal study.

## The idea
Eye-gaze devices are expensive, and voice control assumes clear speech. Able Cursor uses gaze, voice, scanning and blink or key input, and **checks them against each other**. Webcam gaze is imprecise (roughly 100 to 230 px), so the design never asks it for precision: gaze picks a large zone, scanning or dwell confirms, and when gaze and voice disagree the system asks instead of guessing.

## Pages
| File | What it is |
|---|---|
| `index.html` | Project site: problem, how it works, accessibility settings, simulated demo, feedback form |
| `gaze.html` | **Gaze Mode**: consent, live face/iris tracking, 13-dot calibration with test dots, gaze cursor, dwell clicking, double-blink clicking, workspace, floating panel |
| `app.html` | **Voice + gaze zones**: "Hey Cursor" wake word, 9-zone gaze, scanning, blink select, gaze/voice cross-check, pop-out window |

## What is real and what is not
- **Real:** live webcam, MediaPipe face and iris landmarks on your device, calibration-trained regression, gaze cursor, dwell click, blink detection, browser speech recognition, Picture-in-Picture panel.
- **Simulated (and labelled):** the demo section of `index.html`.
- **Not built:** controlling other desktop apps. A web page cannot do that. It needs a small local helper program, which is future work.

## Run locally
1. Install Python 3.
2. In this folder run: `python -m http.server 8000`
3. Open `http://localhost:8000/gaze.html` in Chrome or Edge. Camera access needs `localhost` or HTTPS.

## Privacy
Camera frames are processed on your device and never uploaded or stored. Only your settings and an "onboarding done" flag are saved in your browser. Chrome's speech recognition sends audio to Google. The tracker files load once from jsDelivr and Google storage.

## Known limits
Glasses, glare, dim light and head movement reduce accuracy. Double-blink detection varies between people, so dwell clicking is the fallback. The pop-out panel works with mouse and keyboard, not gaze. Chrome or Edge only for the pop-out and speech features.

## Credits
MediaPipe Face Landmarker (Apache 2.0). Team of six, MISSION'26, VIT Chennai.
