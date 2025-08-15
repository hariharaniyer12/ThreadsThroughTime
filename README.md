# Threads Through Time – Interactive AI Heritage Experience

**Threads Through Time** is an immersive AI-powered system that lets users explore India's ancient clothing heritage by virtually "wearing" outfits from historical eras.  
The system integrates **ComfyUI** for AI image generation, **TouchDesigner** for real-time interaction, and **LoRA models** for historically accurate garment rendering.

This repository contains the setup instructions and workflow files needed to run the project.

---

## 📦 Files Provided

From the shared Google Drive link, you will get:
https://drive.google.com/drive/folders/1AQEwKrxuAcIWJmQ9EK49JGef8us5-YaB?usp=sharing
1. **ComfyUI Workflows**
   - `comfy.json` – Workflow for **TouchDesigner integration** (input from base64 image stream).
   - `comfy.json` – Workflow for **manual testing** (input from image upload).
2. **LoRA Models**
   - `indus_valley.safetensors`
   - `paleolithic.safetensors`
3. **TouchDesigner File**
   - `TDfile.toe` project file to control camera input, marker detection, and send data to ComfyUI.
4. Any supporting media or reference files.
---

## 🛠 Installation Guide
### 1️⃣ Install ComfyUI
1. Clone ComfyUI:
   ```bash
   git clone https://github.com/comfyanonymous/ComfyUI.git
   cd ComfyUI
Install dependencies:
pip install -r requirements.txt

(Optional but recommended) Create and activate a Python virtual environment before installation.
Download and place the LoRA models into:
ComfyUI/models/loras/

2️⃣ Install TouchDesigner
Download TouchDesigner (Free or Commercial version) from:
https://derivative.ca/download
Install and open the TDfile.toe file provided in the Drive folder.
Drive Link:https://drive.google.com/drive/folders/1AQEwKrxuAcIWJmQ9EK49JGef8us5-YaB?usp=sharing

3️⃣ Install Stable Diffusion & Models
Ensure you have a supported Stable Diffusion checkpoint installed in:
ComfyUI/models/checkpoints/
You can use any base SD model compatible with LoRA, but we recommend SD 1.5 for optimal results.
The lora was trained on AbsoluteRealisticVision_v20.safetensors downloaded from civitai.com

4️⃣ Setup Google Drive Files
Drive Link:https://drive.google.com/drive/folders/1AQEwKrxuAcIWJmQ9EK49JGef8us5-YaB?usp=sharing
Download all files from the provided Drive link.

Place:
indus_valley.safetensors and paleolithic.safetensors → ComfyUI/models/loras/
The two comfy.json workflows → ComfyUI/custom_nodes/ or load manually from the UI.
TouchDesigner TDfile.toe file anywhere on your system.

**Switching Eras**
Indus Valley Era: Use indus_valley.safetensors
Paleolithic Era: Use paleolithic.safetensors

**Usage**
Option 1: Live Interaction via TouchDesigner
Start ComfyUI: open run_nvidia_gpu file in comfyUI_windows_portable folder
Open the TDfile.toe file in TouchDesigner.
Ensure your webcam is connected.
In ComfyUI, manually select the desired LoRA model in the LoRA Loader node:
  indus_valley.safetensors for Indus Valley attire
  paleolithic.safetensors for Paleolithic attire
choose Webcam in both all mediapipe tops - use OBS virtual camera or SpoutCam.
Run the project — TouchDesigner sends live images to ComfyUI for real-time outfit generation.

Option 2: Manual Testing
Start ComfyUI: open run_nvidia_gpu file in comfyUI_windows_portable folde
open the manual test workflow comfy.json (input from image upload).
Upload an image in ComfyUI’s interface.
Manually select either LoRA model in the LoRA Loader node.
Run the workflow to generate the historical attire output.

💡 Tips
For best results, use a well-lit environment.
Higher VRAM GPUs (>=8GB) will improve generation speed.
