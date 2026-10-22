# Teachable Machine Classifier

A minimal, reusable web page that loads any Teachable Machine image model and shows its live predictions from your webcam.

## Features

- Paste any Teachable Machine model link, with no code changes needed
- Live top-class label with confidence percentage
- Per-class confidence bars
- Dark theme, responsive layout, keyboard accessible

## Quick start

1. Train an image model at https://teachablemachine.withgoogle.com/.
2. Click **Export Model**, then **Upload my model**, and copy the shareable link.
3. Open `index.html` in a browser.
4. Paste the link, press **Start camera**, and allow camera access.
5. Show any class from your model to the camera.

## Configuration

| Setting | Default | Purpose |
|---|---|---|
| `MIN_CONFIDENCE` | `0.01` | Minimum confidence threshold (currently unused in display) |

## Use it as a starting point

This works as a template for gesture controllers, object recognizers, or any webcam classification project. Add your own logic inside `showPredictions(preds)`.

## Tech

HTML, CSS, vanilla JavaScript, TensorFlow.js 1.3.1, and @teachablemachine/image 0.8.

## Privacy

Inference runs locally in your browser; video is never uploaded.
