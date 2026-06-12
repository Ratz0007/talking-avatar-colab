# Talking Avatar Generator

Generate lip-synced talking head videos from a **photo** and a **script** using free tools.

## Quick Start

1. Open `wan2gp-custom.ipynb` in Google Colab
2. Set runtime to **GPU** (Runtime → Change runtime type → GPU)
3. Run cells in order:
   - Step 1: Confirm GPU
   - Step 2: Install Edge-TTS
   - Step 3: List voices (pick one)
   - Step 4: Write script → generate speech audio
   - Step 5: Upload your photo
   - Steps 6-7: Install Wan2GP → launch Gradio UI
   - Step 8: Follow UI walkthrough to generate video
   - Step 9: Download result

## What You Need

| Item | Requirement |
|------|-------------|
| Google account | Free Colab access |
| GPU | T4 (free tier works) |
| Photo | Square crop, face forward, 50-70% of frame |
| Script | English text, under 30 seconds recommended |

## Photo Requirements

```
+------------------+
|                  |
|    [YOUR FACE]   |  <-- Face: 50-70% of frame
|                  |  <-- Looking at camera
|                  |  <-- Even lighting
+------------------+
     Square crop
```

- **Resolution:** 512x512 minimum (1024x1024 ideal)
- **Orientation:** Face forward, rotation < 30 degrees
- **Lighting:** Even, no harsh shadows
- **Background:** Simple, uncluttered
- **Expression:** Neutral or slight smile

## Voice Options

### Male
| Voice | Accent | Style |
|-------|--------|-------|
| `en-US-GuyNeural` | American | Natural, conversational |
| `en-US-ChristopherNeural` | American | Deep, authoritative |
| `en-GB-RyanNeural` | British | Professional |

### Female
| Voice | Accent | Style |
|-------|--------|-------|
| `en-US-JennyNeural` | American | Clear, professional |
| `en-US-AriaNeural` | American | Expressive |
| `en-GB-SoniaNeural` | British | Warm |

## Audio Settings

```python
voice = "en-US-GuyNeural"  # Pick from list above
rate = "+0%"               # -20% slower, +0% normal, +20% faster
pitch = "+0Hz"             # -10Hz deeper, +0Hz normal, +10Hz higher
```

## Gradio UI Settings (Talking Head)

| Setting | Value | Notes |
|---------|-------|-------|
| Model | `Wan 2.2 TextImage2Video 5B FastWan` | Only one that fits 15GB VRAM |
| Resolution | 480p | Best for free Colab T4 |
| Frames | 81 | ~5 seconds at 16fps |
| Guidance Scale | 5.0-7.0 | Higher = more faithful to audio |
| Steps | 20-30 | More steps = better quality, slower |

## Cost

**100% free.** No credit card required.

| Component | Cost |
|-----------|------|
| Wan2GP | Free (MIT license) |
| Google Colab free tier | Free |
| AI models | Free (open-source) |
| Edge-TTS | Free (no API key) |

### Free Tier Limits
- ~15-30 hours GPU time per week
- Sessions disconnect after ~12 hours
- 15GB VRAM (T4) — fits 5B models at 480p
- Models re-download each session (unless using Google Drive)

## Troubleshooting

| Problem | Fix |
|---------|-----|
| GPU not detected | Runtime → Change runtime type → GPU |
| Out of memory | Lower to 480p, reduce frames to 81 |
| Gradio link not showing | Wait 2-3 minutes, check for errors |
| Mouth not syncing | Try guidance scale 5-7, ensure clear audio |
| Slow model download | Set `USE_GOOGLE_DRIVE = True` in Step 6 |
| Session disconnected | Re-run from Step 1 |
| Video is blurry | Normal at 480p; upgrade to Colab Pro for higher res |

## More Than Talking Heads

Wan2GP also supports:
- Text-to-video generation
- Image-to-video animation
- Voice cloning (SeedVC)
- Video upscaling
- Multi-person lip sync
- Song/lyrics generation (Ace 1.5)

## Links

- [Wan2GP GitHub](https://github.com/deepbeepmeep/Wan2GP)
- [Wan2GP Colab (original)](https://colab.research.google.com/github/Square-Zero-Labs/Wan2GP-on-Colab/blob/main/wan2gp-google-colab.ipynb)
- [Edge-TTS GitHub](https://github.com/rany2/edge-tts)
- [Google Colab](https://colab.research.google.com)
