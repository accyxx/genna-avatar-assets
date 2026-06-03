# genna-avatar-assets
Official production assets for the Genna Talking Head pipeline. Optimized for low-VRAM ComfyUI latent diffusion.

# Genna Avatar - VFX Tutorial Assets

This repository contains the official, verified production assets for the **Genna Talking Head** pipeline by AI/KI NodeCraft. 

These files are optimized for pure latent audio-driven diffusion in ComfyUI on low-VRAM hardware (e.g., NVIDIA Tesla P4 / GTX 1080).

## 📂 Repository Contents
*   `/avatar_image/`: The original 512x512 PNG avatar generated via Z-Image Turbo 6B (clean cybernetic design, no headset).
*   `/voice_audio/`: The 26-second master audio file generated via OmniVoice TTS, along with the raw text script.
*   `/output_preview/`: The final 780-frame synchronized video at 30 FPS for quality benchmarking.

## 🛠️ How to Use
1. Clone this repository alongside our official [ComfyUI-8GB-Pipelines Core Repo](https://github.com).
2. Load the `.json` workflow from the core repo into ComfyUI.
3. Feed `genna_base_512.png` into your image loader and `genna_intro_26s.wav` into your Float Advanced / Audio loader nodes.
4. Hit queue prompt and welcome to the lab!

