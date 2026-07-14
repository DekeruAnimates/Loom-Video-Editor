
# Loom

A professional multi-track video editor built for narrative/storytime gameplay videos.

Create "Video..."-style videos with:
- Multi-track editing
- Motion/keyframe animation
- Optical-flow motion tracking
- Rich text captions
- Built-in sound effects
- AI-powered captions
- Flexible video/audio export

<img width="1919" height="1079" alt="Screenshot 2026-07-13 201520" src="https://github.com/user-attachments/assets/5a9b1fb6-c08c-4d6b-9bb3-395218ca9ae3" />

## What's in this folder

- **`Loom Setup <version>.exe`** — the installer. Double-click it, click through (Next → Next →
  Finish), and it adds Start Menu / Desktop shortcuts. This is the easiest way to install Loom.
- **`Loom <version>.exe`** — the portable version. No installation needed, just double-click to run
  it directly (handy for a USB drive or a machine you don't want to install anything on).
- **This README.**

You only need one of the two `.exe` files, not both — pick whichever you prefer.

If Windows SmartScreen warns you ("Windows protected your PC" / "unrecognized app"), that's just
because the app isn't code-signed with a paid certificate — normal for small/independent apps.
Click **More info → Run anyway** to continue.

## Getting started

1. Install (or run the portable `.exe`) and open Loom.
2. **Import** your video/image/gif/audio files into the media bin.
3. Drag clips onto the timeline — add as many tracks as you want, and drop anything on any track.
4. Select a clip to edit it in **Effect Controls** (position/scale/rotation/opacity, crop, volume,
   speed, transitions, Movie Mode) or **Lumetri Color** (grading).
5. Add narration or sound effects, then generate captions from the narration menu (needs a free
   Groq API key — see below).
6. Hit **Export**, choose your resolution, frame rate, and format, and render.

<img width="1919" height="1036" alt="Screenshot 2026-07-13 201032" src="https://github.com/user-attachments/assets/1db5009b-8fc7-4415-baa0-3cbd522c4f9a" />

### One-time setup: Groq API key (for captions only)

Captions are transcribed using Groq's Whisper API. To use them:

1. Get a free key at [console.groq.com](https://console.groq.com).
2. In Loom, open **Settings** (gear icon) and paste it in.

The key is stored locally on your machine and is only ever sent directly to Groq when you generate
captions — nothing else in Loom needs it or sends data anywhere.

<img width="1919" height="1079" alt="Screenshot 2026-07-13 201524" src="https://github.com/user-attachments/assets/5fbcd6bb-fd96-48f9-b147-b8c0e57a45f0" />

## Feature overview

### Timeline
- **Freeform multi-track timeline**: unlimited tracks, each a free-form lane — clips can start/end
  anywhere, overlap, or leave gaps, and any track can hold video, image, gif, audio, or text clips.
  Later tracks composite on top of earlier ones.
- **Multi-select**: Ctrl/Cmd-click to add/remove clips from a selection, or marquee (drag-box)
  select across tracks. Selections can mix clip types (e.g. a video + an audio clip together).
- Drag to reorder/retime, drag edges to trim, snapping (toggleable), zoom slider, click-to-scrub
  ruler, ripple-delete, split-at-playhead, undo/redo.
- Custom scrollbars, a right-click context menu on the timeline and clips, and waveform rendering
  for audio/video-with-audio clips.

### Motion & animation
- **Keyframeable Motion properties**: position, scale, rotation, and opacity — click the ◆ next to
  a field to drop a keyframe at the playhead, move the playhead and adjust the value to add more,
  and it animates smoothly between them.
- **Follow Tracker**: an optical-flow point tracker — track a point across a clip, then bind another
  clip's position to follow it automatically.
- **Movie Mode** (cinematic letterbox bars), **Crop**, per-clip **Volume** and **Speed** (with pitch
  correction), **crossfade transitions**, and an appendable black-screen ending.
- **Lumetri Color**: per-clip brightness/contrast/saturation/sharpen/denoise.

### Text & captions
- **Titles/text clips** with per-character rich text styling — color, font, gradient, glow, and
  stroke on arbitrary character ranges of a single text clip, plus fade in/out and the same Motion
  keyframing as any other clip.
- **Bundled fonts**: Roblox, Minecraft Ten, Minecraft Regular, Brandbe Extra Bold.
- **AI-generated captions**: select one or more audio clips, or video clips that actually have audio
  (silent videos are automatically skipped), then Generate Captions. Mixed selections work — only
  the usable audio source(s) get transcribed, each mapped to its own span on the timeline. You'll
  get a warning if a selected source has no detected speech. Captions render with karaoke-style word
  highlighting and a pop-in animation, and are fully styleable (font, size, color, outline,
  background, highlight color).

### Media & audio
- Media bin with thumbnails and drag-to-timeline.
- **Built-in sound effect library** — 120 royalty-free effects (clicks, whooshes, dings, chimes,
  camera shutter, drumroll, etc.), no internet needed.
- **Extract Audio**: pull the audio track out of any video clip into a standalone audio file (WAV,
  MP3, AAC, or OGG), added straight to the media bin.

### Export
- Pick **resolution** (horizontal/square/vertical), **frame rate**, and independently toggle
  **Video** and **Audio** on/off.
- **Video format**: MP4, MOV, MKV, or WebM (WebM encodes noticeably slower — you'll see a warning).
- **Audio-only format** (when exporting audio with video turned off): MP3, WAV, AAC (.m4a), or OGG.
- A live export preview (sample frame + mixed waveform) before you commit.

## Known rough-pass limitations

- Preview vs. export aren't pixel-identical for every aspect ratio — double-check overlay/title
  placement against a real export if you switch resolutions.
- Transitions are a single crossfade style for now (no wipes/slides yet).
- Caption grouping is fixed at 3 words per chunk.
- WebM export is noticeably slower than MP4/MOV/MKV — that's expected, not a hang.

## Version

Current release: v1.0.0
Status: Beta

## Roadmap

Planned:
- More transition types
- Addon-creator (still being planned.)

## Usage & Redistribution

Loom is free to use, modify, and experiment with. You are welcome to learn from the project, create modifications (if you do that somehow), or build upon it.

The only restrictions are:
- Do not claim Loom or modified versions of Loom as your own original work (pls credit me if you do modify it).
- Do not sell Loom or distribute it commercially without permission from DekeruAnimates.

Credit is appreciated when sharing modifications or derivative projects.

## Download Size

Loom is built with Electron, which includes the Chromium and Node.js runtimes required to run the application. The larger file size is expected and does not indicate unnecessary bundled files.

© 2026 DekeruAnimates. Loom. All rights reserved.
