# Letter Sounds Lab

A phonics practice web app: watch the alphabet-sounds video, then say each
letter's sound into your microphone to get instant feedback, points, streaks,
confetti, and badges.

## What's inside
- `index.html` — the whole app (HTML/CSS/JavaScript, no build step, no server-side code)
- `assets/phonics-alphabet-sounds.mp4` — the study video, compressed for the web (~2.1 MB)

## How to run it
1. Unzip this folder.
2. Double-click `index.html` to open it in a browser (Chrome or Edge recommended).
   - If your browser blocks the microphone when opening a file directly, instead
     serve the folder locally, e.g. from a terminal inside this folder:
     `python3 -m http.server 8000` then open `http://localhost:8000` in your browser.
3. Click "Watch again" to replay the video any time.
4. Tap a letter tile, then tap the microphone button and say that letter's sound
   out loud. Correct answers trigger confetti, points, and streak bonuses;
   milestones unlock badges. Progress is saved in the browser (localStorage) on
   that device only.

## Notes on the voice matching
Speech recognition uses the browser's built-in Web Speech API
(`SpeechRecognition` / `webkitSpeechRecognition`), which currently works best
in Chrome and Edge. It transcribes what you say to text and checks it against
a list of accepted letter names and phonetic sounds (e.g. for "B": "bee", "b",
"buh"). This is a practical approximation of "comparing to the actual sound" —
true audio-waveform matching against the reference recording would need a
server-side ML model, which is out of scope for a static, offline-friendly
web page. If your browser doesn't support speech recognition, the app tells
you and you can still use the video for study.

## Customizing
- Letter sound/name variants: edit the `LETTERS` array in `index.html`.
- Colors, fonts, layout: edit the `<style>` block at the top of `index.html`.
- Swap the video: replace `assets/phonics-alphabet-sounds.mp4` with your own
  file of the same name (or update the `<source src>` path in `index.html`).
