# RunningHub Video Generator

A simple and elegant web interface for generating videos from images using the [RunningHub](https://www.runninghub.ai/?inviteCode=qlbtubgi) API.

## Features
- **Dual Dropzone Interface**: Separate zones for Source Image and Watermark Image with live preview thumbnails.
- **Automatic Image Upload**: Images are automatically uploaded to RunningHub cloud storage.
- **Built-in ZIP Decoder**: Automatically downloads and extracts ZIP archive with frames directly in the browser.
- **Watermark Removal**: Pixel-level decoding using `2 * shot - watermark` formula to remove watermarks from generated frames.
- **Canvas Video Player**: Built-in player with frame-by-frame navigation, play/pause controls, and scrubber.
- **WebM Export**: Compile decoded frames into WebM video (16 FPS, VP9 codec) with progress tracking.
- **Real-time Status Tracking**: Step-by-step generation progress indicator.
- **API Key Persistence**: Automatic API key saving in browser's localStorage.

## Usage
1. Open the generator page: [Wan2.2 Generator](https://yaplamyayaogon.github.io/javascript/wan22-16fps-8sec.html).
2. Enter your [RunningHub API Key](https://www.runninghub.ai/enterprise-api/consumerApi?inviteCode=qlbtubgi).
3. Select or drag & drop **Source Image** (node 396) and **Watermark Image** (node 411) — previews will appear instantly.
4. Configure LoRA settings (High/Low) and prompts if needed.
5. Click "Generate Video" and wait for the process to complete.
6. Preview decoded frames in the built-in player.
7. Export as WebM video or download individual frames.

## Workflow
The generator follows a complete pipeline:
1. **Upload** → Source and Watermark images uploaded to RunningHub
2. **Submit** → Task submitted to ComfyUI workflow (ID: 2068017342252146690)
3. **Process** → Polling status until generation completes
4. **Download** → ZIP archive with frames automatically downloaded
5. **Decode** → Frames decoded in browser using watermark subtraction
6. **Play** → Preview decoded frames in canvas-based player
7. **Export** → Compile and download as WebM video

## Technologies
- **Frontend**: Pure HTML/CSS/JavaScript (no framework)
- **Libraries**: JSZip (ZIP extraction), MediaRecorder API (WebM encoding)
- **API**: RunningHub OpenAPI v2
- **Rendering**: HTML5 Canvas with OffscreenCanvas for performance

## Partner Info
This project uses partner invite code `qlbtubgi` — support the development by using [this link](https://www.runninghub.ai/?inviteCode=qlbtubgi) to register on RunningHub.
