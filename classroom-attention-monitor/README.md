# Classroom Attention Monitor

A single-file web app that uses a webcam and a Teachable Machine image model to estimate how engaged a student is during a lecture, live in the browser.

## Features

- Live webcam classification with per-class confidence bars
- Attention score ring showing the share of time spent in "good" behaviors
- 60-second timeline (green = attentive, amber = neutral, red = needs attention)
- Alert when a "bad" behavior lasts 5+ seconds
- Time-per-behavior table
- Runs fully in the browser; no video leaves the device

## Quick start

1. Train an image model at https://teachablemachine.withgoogle.com/ (for example: attentive, raising hand, taking notes, using phone, sleeping, looking away).
2. Click **Export Model**, then **Upload my model**, and copy the shareable link.
3. Open `index.html` in a browser (or serve it with any static server).
4. Paste the link, press **Start camera**, and allow camera access.

## Configuration

Edit the constants at the top of the script:

| Setting | Default | Purpose |
|---|---|---|
| `MIN_CONFIDENCE` | `0.70` | Below this, the result shows "Not sure" |
| `ALERT_AFTER_SEC` | `5` | Seconds before the alert appears |
| `GOOD` | attentive, raising, hand, notes | Keywords that mark a class as attentive |
| `BAD` | phone, sleep, head, empty, away, talking, yawn | Keywords that mark a class as needing attention |

## Tech

HTML, CSS, vanilla JavaScript, TensorFlow.js 1.3.1, and @teachablemachine/image 0.8.

## Privacy

All inference runs locally in the browser. Only the model files are fetched from Teachable Machine.

## Notes

Use this only with the consent of the people being monitored. Attention estimates from a webcam are rough and should not be used for grading or discipline.
