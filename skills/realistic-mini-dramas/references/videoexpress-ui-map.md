# VideoExpress UI map

Observed live in the signed-in editor at https://app.videoexpress.ai/ on 2026-10-23. Labels are shown **bold**, exactly as they appear. If the UI changes, find the control by its visible text and keep going.

## Top bar
**New** · **Open** · **Save** (its arrow opens **Save Project As** / **Export Project**) · **My Videos** · **Public Gallery** · **Workflows** · orange **Export Video** button.

## Right sidebar
**Media Library** · **Create with AI** · Import Media / Text to Speech · Text Animations · Filters · Fast Cut · Automatic Captions · Audio Cutter.

## Create with AI → Create Video From Prompt (the generation dialog)
Menu entries include: **Create Video From Prompt** (Image to Video · Lipsync HD · Narrate · Consistent Character, "3.5" badge), Text To Video, First Frame Last Frame, Smart Edit, Stylize Character, Image To Video (Old Algorithm), Lipsync Video (Old Algorithm), Outpainting, Change Aspect Ratio, AI Sound Maker. **Always use Create Video From Prompt.** The "3.5" badge is a version label. It is not a model name you need to check.

| Control | Default | Set it to |
|---|---|---|
| **Landscape 16:9** / **Vertical 9:16** | Vertical | **Vertical 9:16** |
| **Image Prompt** (textarea) | keeps last value | select all, delete, type the new prompt |
| **Video and Audio Prompt** (textarea, "New – Multi-Shot" label) | keeps last value | select all, delete, type a new prompt starting with `S## —` |
| **Image Type** (select) | Human | Realistic → **Photorealistic (Cinematic)**; 3D → **3D**; 2D → **2D**; other → **Other** |
| **Use Creative mode** | off | Realistic **OFF**; every other style **ON** |
| **Automatically enhance my image prompt** | **on** | **OFF** (it rewrites your character text) |
| **Use Consistent Character** + **Use from Library** | off | ON plus the character(s) in this shot, if you saved any |
| **Lipsync HD Video** / **Narration Video (Choose my Audio)** | off | OFF |
| **Share this in the public gallery** | **ON** | **uncheck** on every shot (it turns back on when the dialog reopens) |
| **Advanced Mode** | off | **ON** |
| → **Automatically enhance my video prompt** | off | OFF |
| → **Video Only (No Sound)** | off | OFF |
| → **Manual Video Length, sec** (slider 3–10) | off / 5 | ON, then set the slider to **4** (no dialogue) or **5** (dialogue) |
| Buttons | | **Enhance Prompt** (don't use) · **Create Image** · **+ Consistent Character** · **Create Video** |

### Dialog quirks
- The dialog **remembers every field and image** between opens. Overwrite both prompts and re-set every checkbox on every shot.
- Ticking **Manual Video Length** resets the slider to **10**. Set the slider after ticking, then re-read it. Click the handle and use Arrow Left/Right if dragging misses.
- **Create Video** is often below the fold. Scroll inside the dialog with the mouse wheel.
- The **Close** button is unreliable. Use the top-right **X**.
- Element references go stale after every change. Re-read the page before each click so you don't toggle the wrong checkbox.
- Generated images are 1088×1920 (vertical) and appear in a carousel. Make sure the new one is selected before you click Create Video.
- Creative mode and the image enhancer both rewrite the Image Prompt text in the box. That's expected with Creative mode ON.

### Submission results
- Success: toast *"Your video will appear in your Media Library under the My Media tab when it's ready."* plus *"Video: <id>"*.
- *"You can generate up to 5 AI videos in parallel…"*: nothing was created. Wait 60 s and click **Create Video** once more.
- Login / Terms / upgrade / payment screen: the user must click it. Ask them, wait for "done", then continue.

## Media Library
**Media Library** → **My Media** tab → double-click the **My AI Videos** folder (sort **Newest**). Each card is titled with the start of its video prompt, which is why every prompt starts with `S## —`. Rendering clips show a **% ring**. Leave and re-enter the folder to refresh. Thumbnails can look cropped, so trust the title.

## Timeline editor
- **Preview** top-left, with the canvas buttons **Landscape 16:9** / **Vertical 9:16** above it. Player buttons: **Step backward**, **Play**, **Step forward**. The time readout shows whole seconds only.
- **Timeline toolbar:** Undo · Redo | **Zoom out** · **Zoom in** | Add track below · Add track at top | Copy · Paste · **Cut** (scissors, which splits the clip under the playhead; no selection needed) | Save current frame.
- **Track row, left side:** **Auto Align Clips** (`+|+`, packs clips together and closes gaps) · Fast Cut Toggle · Mute · Disable video · trash. ⚠️ The trash icon deletes the whole TRACK. Never use it for a clip.
- **Adding clips:** drag a thumbnail from My AI Videos onto track 1. It lands where you drop it, so click Auto Align Clips afterwards.
- **Selecting:** left-click a clip. There's no properties panel and there are no numeric start/end/duration fields.
- **Right-click a clip:** Properties (volume only), Resize and move, Voice Changer, Save Audio, Separate Audio and Video, Transition In/Out/Between, Add voiceover, **Delete**.
- **Deleting a clip piece:** right-click → **Delete**. The keyboard Delete/Backspace keys do nothing. Deleting leaves a gap (no ripple), so click **Auto Align Clips**.
- **Trimming by edge:** both clip edges are drag handles (about 8 px wide, full clip height). Right edge leftward trims the end. Left edge rightward trims the start but shifts the clip and leaves a gap, so click Auto Align Clips. Minimum clip width is 10 px.
- **Playhead:** click the ruler strip above the tracks, or use Step forward/backward (about 0.1 s per press after 3 zoom-ins), or focus the playhead handle and press Arrow Left/Right (1 px per press). There's no timecode input.
- **Scale:** after clicking **Zoom in** 3 times from the default, the ruler labels every 3 s, 120 px apart: **40 px = 1 s**, **1 px = 25 ms**.
- **No audio waveform** on the timeline. Judge cut points from the preview frame and by playing the audio.
- **Fast Cut** adds transitions only. Don't use it for dead-air removal.

## Save and export
1. **Save** (name the project; use **Save Project As** to rename).
2. **Export Video** → **High** / **FullHD** / **mp4** → server queue ("number N in the queue").
3. **My Videos** lists the finished file with a download link. Files are hosted for 40 days.
