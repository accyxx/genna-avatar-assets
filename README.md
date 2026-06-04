# genna-avatar-assets
Official production assets for the Genna Talking Head pipeline. Optimized for low-VRAM ComfyUI latent diffusion.

# Genna Avatar - VFX Tutorial Assets

This repository contains the official, verified production assets for the **Genna Talking Head** pipeline by AI/KI NodeCraft. 

These files are optimized for pure latent audio-driven diffusion in ComfyUI on low-VRAM hardware (e.g., NVIDIA Tesla P4 / GTX 1080).

## 📂 REPOSITORY CONTENTS

### 1. `/avatar_image/`
*   **`ComfyUI_00011_.png`** -> The official production-ready 512x512 PNG avatar generated via Z-Image Turbo 6B (clean cybernetic design, frontal symmetry, no headset). Highly optimized for flawless latent diffusion.
*   **`Genna_Headphone_Glitch.png`** -> *[NEW]* A specialized benchmark file featuring a rigid cyber-headset over the ears and jawline. Use this file to replicate the precise structural grid limitations and texture-warping anomalies discussed in the tutorial. You will also find a generated Video! **Genna_Disgust_Headphones_Glitching**

### 2. `/voice_audio/`
*   **`Mastervoice_genna_26s.wav`** -> The final 26-second master audio track generated natively via OmniVoice TTS at 24000Hz (32-bit float).
*   **`Audio_Padding_Structure`** -> This master track includes an automated 2.5-second silent **Preroll** at the start and a 2.5-second silent **Postroll** at the end. This structure acts as an acoustic buffer to stabilize the KSampler on Frame 0 and provides clean editing handles for post-production.
*   **`script.txt`** -> The raw textual script containing our specialized phonetic sentence layers for calibration.

### 3. `/output_preview/`
*   **`Genna_Clean_Reference_30fps.mp4`** -> The final 780-frame synchronized video container running at a fluid 30 FPS. Serves as your production baseline.
*   **`Headset_Glitch_Demovideo.mp4`** -> *[NEW]* A raw reference clip demonstrating how rigid geometric objects (like headphone earcups) deform unnaturally into "gum-like" artifacts when subjected to aggressive latent audio forces without prompt optimization.


## 🛠️ How to Use
1. Clone this repository alongside our official [ComfyUI-8GB-Pipelines Core Repo](https://github.com).
2. Load the `.json` workflow from the core repo into ComfyUI.
3. Feed `genna_base_512.png` into your image loader and `genna_intro_26s.wav` into your Float Advanced / Audio loader nodes.
4. Hit queue prompt and welcome to the lab!

