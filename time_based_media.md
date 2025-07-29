---
category: "time_based_media"
category_description: "Make audio and video accessible with captions, transcripts and descriptions."
---

### Overview

Audio and video content should be usable by people who are deaf, hard of hearing or cannot watch the screen. Provide captions for speech and relevant sounds, transcripts for audio-only media and audio descriptions for important visual events.

### Relevant WCAG 2.1 success criteria

- **1.2.1 Audio-only & Video-only** (Level A) – Audio-only media has transcripts; video-only media has descriptions.【755185167370695†L552-L596】
- **1.2.2 Captions (Pre-recorded)** (Level A) – Provide captions for speech and sounds in pre‑recorded video.【755185167370695†L552-L596】
- **1.2.3 Audio Description or Media Alternative** (Level A) – Offer audio description or alternative presentation for visual information.【755185167370695†L552-L596】
- **1.2.4 Captions (Live)** (Level AA) – Provide captions for live multimedia.【755185167370695†L552-L596】

### Technical guidance

* Use the `<track>` element with `kind="captions"` and a WebVTT file in `<video>` elements.  
* Offer transcripts alongside audio files; include descriptions of non-verbal sounds.  
* Provide audio descriptions or text descriptions for visual-only media.  
* Choose media players with keyboard controls and caption toggles.

### Code example

#### Video with captions
```html
<video controls>
  <source src="lecture.mp4" type="video/mp4">
  <track kind="captions" srclang="en" src="lecture.en.vtt" label="English" default>
</video>
```

#### Audio with transcript
```html
<audio controls>
  <source src="podcast.mp3" type="audio/mpeg">
</audio>
<p><a href="podcast-transcript.html">Read transcript</a></p>
```
