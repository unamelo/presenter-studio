# Presenter Studio

Record a presentation with your slides and your face in one video, in the browser. No editing, no account, no subscription.

- **Slides + camera in one video:** your face sits in a corner of the slides (circle or rounded box) and you can move and resize it
- **Beauty filter:** skin smoothing that keeps eyes and hair sharp, plus brighten, warmth and colour
- **Background blur:** runs on your own computer with Google's MediaPipe selfie model
- **High resolution:** 1080p, 1440p or 4K at 30 fps, saved as MP4 (or WebM in browsers without MP4 recording)
- **Speaker notes that are never recorded:** a floating notes box, or presenter view (small slide preview, next slide, timer, big notes)
- **Import notes** from a written script (`Slide 1: …` headings) or from a PowerPoint `.pptx`
- **Timer that is never recorded:** total time against your target length (e.g. 9–11 min) and time on the current slide against cues like "(About 45 seconds.)" in your notes, plus a practice mode
- **Redo a slide:** each slide is recorded as its own take. Made a mistake on slide 6? Press `Z` and only slide 6 is recorded again. A timeline shows every take, and you can delete and re-record any of them, even earlier ones.
- **Pause and continue later:** takes are saved in the browser as you record, so you can pause, close the browser, and continue another day. **Save video** joins the takes into one MP4.

Everything happens on your own computer. Slides, video and notes are never uploaded anywhere.

## Use it

**Online:** open <https://unamelo.github.io/presenter-studio/> in **Chrome** or **Edge**.

**Locally** (Mac, Windows or Linux):

```sh
git clone https://github.com/unamelo/presenter-studio.git
cd presenter-studio
python3 -m http.server 8000
```

Then open <http://localhost:8000> in Chrome or Edge. The camera only works over `http://localhost` or `https://`. It does not work if you double-click the file.

On a **Mac**, the first time you use it, allow Chrome to use the camera and microphone in *System Settings → Privacy & Security → Camera / Microphone* (restart Chrome afterwards). To use **Share window**, Chrome also needs *Screen & System Audio Recording* permission.

## Workflow

1. Export your slides as **PDF** (PowerPoint: File → Export → PDF. Google Slides: File → Download → PDF). PDF slides are drawn sharply at the full recording resolution. If you need animations or embedded video, use **Share window** on a PowerPoint slideshow instead.
2. Click **Open PDF**.
3. Add notes: **Import script (text)**, **Import from .pptx**, or click ✎ on the notes box and type.
4. Set up the camera bubble, beauty filter and blur, then press **R**. After a 3-2-1 countdown it's recording.
5. Present as normal. Each slide becomes a separate take.
   - Mistake? Press **Z** to throw away this slide's take and record the slide again (3-2-1 countdown).
   - Tired? Press **R** to pause, and **R** again to continue. You can even close the browser and come back later.
   - To redo an earlier slide, pause, then click **✕** on its take in the timeline and press **R**. The new take goes back in the same place.
6. Click **Save video** and choose where to save the finished MP4. Your takes are kept, so you can still fix a slide and save again. **New recording…** clears them.

### Script format for import

```
Slide 1: Title of slide 1 (Look at the camera. About 40 seconds.)

What you'll say on slide 1…

Slide 2: Title of slide 2 (About 35 seconds.)

…
```

Markdown bold (`**Slide 1: …**`) is fine. The bracketed part at the end of a heading becomes a cue at the top of the note. If the text contains several versions of the script (the slide numbers start again at 1), you can choose which version to import.

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| `→` `Space` `Page Down` | Next slide (clickers work too) |
| `←` `Page Up` | Previous slide |
| `R` | Start recording / pause / resume |
| `Z` | Redo this slide |
| `C` | Show / hide camera |
| `B` | Background blur on / off |
| `T` | Start / pause practice timer |
| `N` | Floating notes |
| `V` | Presenter view |
| `+` / `−` | Notes text size |
| `H` | Hide the side panel |

## Good to know

- Notes and settings are saved in the browser for the address you use (for example `localhost:8000` and the GitHub Pages site each keep their own). Use **Back up all notes** to move them to another browser or computer.
- Keep the tab open while recording. Switching to other windows is fine.
- Recording needs a recent Chrome or Edge (it uses WebCodecs to encode each take). Takes are stored in the browser for the address you use, until you click **New recording…**.
- 10 minutes at 1080p "High" is about 1.2 GB. Use "Standard" for smaller files.
