# Smart Desk Scanner

Hold an item in front of your webcam and it is recognized and added to a running inventory automatically, using a Teachable Machine image model.

## Features

- Auto-count: an item is added after being held steady for 1.5 seconds
- Requires an empty desk between items to avoid double counting
- Manual **Add current item** button, plus +/− controls per item
- Live inventory list with a running total
- One-click CSV export (`desk_inventory.csv`)
- Per-class confidence bars

## Quick start

1. Train an image model at https://teachablemachine.withgoogle.com/ with one class per item, plus an **Empty** class (a class name containing "empty", "none", "nothing", or "background" is treated as no item).
2. Click **Export Model**, then **Upload my model**, and copy the shareable link.
3. Open `index.html` in a browser.
4. Paste the link, press **Start camera**, and allow camera access.
5. Hold one item steady inside the frame, then show an empty desk before the next item.

## Configuration

| Setting | Default | Purpose |
|---|---|---|
| `MIN_CONFIDENCE` | `0.85` | How sure the model must be before acting |
| `HOLD_MS` | `1500` | How long an item must stay steady to be counted |
| `EMPTY` | `/empty\|none\|nothing\|background/` | Class names that mean "no item" |

## Tips

- Use good, even lighting and a plain background.
- Train the Empty class with the same desk and camera angle you will use.
- Add varied photos of each item (angles and distances) for better accuracy.

## Tech

HTML, CSS, vanilla JavaScript, TensorFlow.js 1.3.1, and @teachablemachine/image 0.8.

## Privacy

Inference runs locally in your browser; video is never uploaded.
