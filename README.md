# Talking Avatar Generator

Generate lip-synced talking head videos from a **photo** and a **script** using free tools on Google Colab.

## Quick Start

1. Open the notebook in Google Colab: [wan2gp-custom.ipynb](https://colab.research.google.com/github/YOUR_USERNAME/talking-avatar-colab/blob/main/wan2gp-custom.ipynb)
2. Set runtime to **GPU** (Runtime → Change runtime type → GPU)
3. Run cells in order
4. Follow the Gradio UI walkthrough in Step 8

## What This Does

**Pipeline:** Script → Speech audio → Animated talking head video

- **Text-to-Speech:** Edge-TTS (free, 300+ voices, no API key)
- **Video Generation:** Wan2GP with LTX 2.3 lip-sync model
- **Cost:** 100% free on Google Colab (T4 GPU)

## Files

| File | Description |
|------|-------------|
| `wan2gp-custom.ipynb` | Colab notebook — run this |
| `README_usage.md` | Detailed usage guide |

## Requirements

- Google account with Colab access
- GPU runtime (free T4 works)
- A photo of a face (square crop, face forward)

## License

MIT
