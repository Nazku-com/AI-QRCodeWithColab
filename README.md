<h1 align="center">How to Create an AI-QRCode</h1>

<p align="center">
  <img src="https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/9a0a32ed-dc43-424b-9f3d-1aff054ae59e" alt="Generated QR Code"/>
</p>

<p align="center">This repository provides a comprehensive guide on how to create anime-inspired QR codes using Stable Diffusion.</p>

## 📚 Table of Contents

- [Prerequisites](#prerequisites)
- [Open WebUI](#open-webui)
- [QR Code Generation](#qr-code-generation)
- [Others](#others)


## ⚙️ Prerequisites

1. Download this repository and open `AI-QRCode.ipynb` with Google Colab.
   ![Setup](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/a47dcd53-7a99-4f62-8749-f9120dd9560a)
2. Open `Resources` and set the Hardware accelerator to `GPU`.
   ![Resources](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/2a87ea9e-a058-4ec7-9ba0-ab2476045bd7)

## 🕸️ Open WebUI

Follow the steps in the code to open the `Public URL`.
![Public URL](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/812cb998-c6d7-413a-a09e-c0748fbe9367)

Navigate to `Settings` and `ControlNet`. Make sure `Multi ControlNet: Max models amount` is set to more than 2 (default is 3), then click `Apply settings` and `Reload UI`.
![ControlNet](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/92401190-ec87-492b-b0aa-3fdbb4ada2a2)

## 🎨 QR Code Generation

Follow the steps below to generate your anime-inspired QR code:

1. Open `ControlNet` -> `ControlNet Unit 0` and upload your QRCode.
   ![ControlNet Unit 0](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/f78bf5eb-4492-47da-9421-12f9bfdc2db1)
2. Adjust your settings as follows:
   - `set the preprocessor to [invert] if your image has a white background and black lines` to `Enable`
   - Set `Preprocessor` to `inpaint_global_harmonious`.
   - Set `Model` to `control_v1p_sd15_brightness [5f6aa6ed]`.
   - Set `Control Weight` to `0.35`.
   ![ControlNet Unit 0 Settings](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/5d6e1bbe-1ae5-4502-a868-87b38b568641)
3. Open `ControlNet` -> `ControlNet Unit 1` and upload your QRCode, then adjust your settings as follows:
   - `set the preprocessor to [invert] if your image has a white background and black lines` to `Enable`
   - Set `Preprocessor` to `inpaint_global_harmonious`.
   - Set `Model` to `control_v11f1e_sd15_tile [a371b31b]`.
   - Set `Control Weight` to `0.55`.
   - Set `Starting Control Step` to `0.35`.
   - Set `Ending Control Step` to `0.75`.
   ![ControlNet Unit 1 Settings](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/0f97d288-ceb5-496f-b5e4-adee5aaa066d)
4. Prompt your QR Code image to be generated.
   For instance:
   - Prompt: masterpiece, best quality, Japanese house, tree, and city background
   - Nagative Prompt: UnrealisticDream, FastNegativeEmbedding

![Prompt](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/2f98ca26-54e0-4d2b-8d75-5318b499d3fc)

## 📌 Others

The style of the generated image heavily depends on the Stable Diffusion checkpoint. You can change the checkpoint to generate a QR code image with a different style.

![Checkpoint](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/033f2adb-2d71-41c5-aaae-793fd589fcf2)

You can add more checkpoints by modifying these lines of code:
![Code](https://github.com/Nazku-com/AI-QRCodeWithColab/assets/52348220/3a842c79-1472-46e5-a93a-1b73e0197ff2)

To download checkpoints, run `curl -Lo filename.safetensors downloadLink` and move the downloaded file into the `/content/microsoftexcel/models/Stable-diffusion` folder.

---

This repo is inspired by [sd-misc-colab](https://github.com/nolanaatama/sd-misc-colab) and [Rowan Cheung's Twitter post](https://twitter.com/rowancheung/status/1669402190757367809?s=46).
