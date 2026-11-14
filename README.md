# SamudrikaLens

A browser-based palm reader that finds the lines on your palm through your webcam, labels them, and saves the result as shareable art. It runs fully in the browser with no backend.

## Features
- Live hand tracking with 21 landmarks per hand
- Palm crease detection drawn directly on the video
- Approximate labels for the Heart, Head and Life lines, each in its own colour
- Playful "estimated age" shown as a range, based on how strong the creases look
- Capture button with three styles: Neon, Blueprint and Ink
- Download your reading as a PNG, or retake it

## How it works
1. **MediaPipe Hand Landmarker** tracks the hand and finds the palm area.
2. The palm is straightened into a fixed square so the lines stay stable as the hand moves.
3. A ridge filter (green channel, lighting flattening, curvature-based line detection) finds the creases, and results are averaged across frames to reduce flicker.
4. Line pixels are grouped into curves, and each curve is named from where it sits on the palm.
5. The result is drawn on an HTML5 canvas and exported as an image.

## Tech stack
HTML, CSS, JavaScript, HTML5 Canvas, MediaPipe Tasks Vision

## Privacy
All processing happens in your browser. Video is never uploaded or stored.

## Limitations
- Line names are approximate guesses based on position, not a real palmistry reading.
- The age estimate is for entertainment only and is not accurate.
- Results depend on lighting and camera quality. Face a light and keep your palm flat and still.

## Run locally
Camera access needs a local server or HTTPS:

    npx serve

Then open the address it prints and allow camera access.

## Author
Hemasri Yamala· https://github.com/hemasriy3-dev
