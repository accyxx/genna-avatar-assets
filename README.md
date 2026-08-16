# genna-avatar-assets
Official production assets for the Genna Talking Head pipeline. Optimized for low-VRAM ComfyUI latent diffusion.

# Genna Avatar - VFX Tutorial Assets

This repository contains the official, verified production assets for the **Genna Talking Head** pipeline by AI/KI NodeCraft. 

These files are optimized for pure latent audio-driven diffusion in ComfyUI on low-VRAM hardware (e.g., NVIDIA Tesla P4 / GTX 1080).

## 📂 REPOSITORY CONTENTS

### 1. `/avatar_image/`
*   **`ComfyUI_00011_.png`** -> The official production-ready 512x512 PNG avatar generated via Z-Image Turbo 6B (clean cybernetic design, frontal symmetry, no headset). Highly optimized for flawless latent diffusion.
*   **`Genna_Headphone_Glitch.png`** -> *[NEW]* A specialized benchmark file featuring a rigid cyber-headset over the ears and jawline. Use this file to replicate the precise structural grid limitations and texture-warping anomalies discussed in the tutorial. You will also find a generated Video! **Genna_Disgust_Headphones_Glitching.mp4**

### 2. `/voice_audio/`
*   **`Genna_Master_Voice.wav`** -> The final 26-second master audio track generated natively via OmniVoice TTS at 24000Hz (32-bit float).
*   **`Genna_26_seconds_Audio_Padding.wav`** -> This master track includes an automated 2.5-second silent **Preroll** at the start and a 2.5-second silent **Postroll** at the end. This structure acts as an acoustic buffer to stabilize the KSampler on Frame 0 and provides clean editing handles for post-production.
*   **`Markdown Note** -> The raw textual script containing our specialized phonetic sentence layers for calibration.

### 3. `/output_preview/`
*   **`Genna_Final_Output_Disgust.mp4`** -> The final 780-frame synchronized video container running at a fluid 30 FPS. Serves as your production baseline.
*   **`Genna_Disgust_Headphones_Glitching.mp4*** -> *[NEW]* A raw reference clip demonstrating how rigid geometric objects (like headphone earcups) deform unnaturally into "gum-like" artifacts when subjected to aggressive latent audio forces without prompt optimization.


## 🛠️ How to Use

### 🛠️ Step 1: Requirements & Model Setup

To run the Genna Talking Head Pipeline, you must install the required ComfyUI extensions and download the model weights into your ComfyUI folders.

#### 1. Required ComfyUI Extensions (Custom Nodes)
Install these via the **ComfyUI Manager** (search for their names) or download them manually into your `ComfyUI/custom_nodes/` directory:
* **[🗣️ ComfyUI-IndexTTS2](https://github.com/snicolast/ComfyUI-IndexTTS2.git))** – Lightweight voice cloning and emotional audio controller.
* **[🎬 ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite.git)** – Essential for loading, processing, and rendering video containers.
* **[🚀 ComfyUI-FLOAT_Optimized](https://github.com/set-soft/ComfyUI-FLOAT_Optimized.git)** – Optimized core engine for audio-driven Generative Motion Latent Flow Matching.
* **[🎙️ ComfyUI-OmniVoice-TTS](https://github.com/Saganaki22/ComfyUI-OmniVoice-TTS
)** – Enables multilingual Zero-Shot Text-to-Speech inside the workflow.

#### 2. Required AI Models & Weights (HuggingFace)
Click the links below to download the models. Move the files into the specified subfolders within your main `ComfyUI/models/` directory:

* **[🧠 Download Z-Image-Turbo (GGUF)](https://huggingface.co/jayn7/Z-Image-Turbo-GGUF/resolve/main/z_image_turbo-Q6_K.gguf)** (Q6_K quantization)   * *Move to folder: `ComfyUI/models/unet/` (or `models/checkpoints/`)*
* **[📝 Download Qwen3-4B Text Encoder (GGUF)](https://huggingface.co/Qwen/Qwen3-4B-GGUF/resolve/main/Qwen3-4B-Q6_K.gguf)** (Lightweight text conditioning)   * *Move to folder: `ComfyUI/models/text_encoders/` (or `models/llm/`)*
* **[✨ Download Z-Image-Turbo VAE]( https://huggingface.co/Comfy-Org/z_image_turbo/resolve/main/split_files/vae/ae.safetensors)** (`ae.safetensors` autoencoder)   * *Move to folder: `ComfyUI/models/vae/`*

---

### 🚀 Step 2: Run the Workflow

You can either **clone** the entire repository using Git or simply **download it as a ZIP file** by clicking the green `<> Code` button at the top of this page (or [click here to download the ZIP directly](https://github.com)).

Once you have the files on your local machine, follow these steps:

1. **Load the Workflow:** Drag and drop the `.json` file from your local `/workflows/` folder directly into your ComfyUI browser tab.
2. **Load the Avatar Image:** Feed `ComfyUI_00011_.png` (from the `/avatar_image/` folder) into your ComfyUI image loader node.
3. **Load the Audio Track:** Feed `Genna_26_seconds_Audio_Padding.wav` (from the `/voice_audio/` folder) into your Float Advanced / Audio loader nodes.
4. **Generate:** Hit **Queue Prompt** and welcome to the lab! 🚀

### If you get an error on the Node - Happens after the Patch!

<fieldset>
  <legend> <strong> 🤖 Screenshot: Node Error Help <strong></legend>
  <img width="808" height="392" alt="grafik" src="https://github.com/user-attachments/assets/f66e65d6-8de9-4e91-b993-56c6839235f7" />
</fieldset>

<br>

start with:<br>
`a_cfd_scale` - 1.0<br>
`e_cfg_scale` - 1.0<br>
`seed` - 123 *(Automatically generates new SEED on RUN)*
