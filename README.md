# RunningHub Video Generator

A simple and elegant web interface for generating videos from images using the [RunningHub](https://www.runninghub.ai/?inviteCode=qlbtubgi) API.

## Features

- **Dual Dropzone Interface**: Separate zones for Source Image and Watermark Image with live preview thumbnails.
- **Automatic Image Upload**: Images are automatically uploaded to RunningHub cloud storage.
- **Multi-File Download**: Automatically downloads 141 individual PNG frames + 1 watermark (no ZIP archive required).
- **Watermark Removal**: Pixel-level decoding using `2 * shot - watermark` formula to remove watermarks from generated frames.
- **Canvas Video Player**: Built-in player with frame-by-frame navigation, play/pause controls, and scrubber.
- **WebM Export**: Compile decoded frames into WebM video (16 FPS, VP8/VP9 codec auto-detection) with progress tracking.
- **Real-time Status Tracking**: Step-by-step generation progress indicator.
- **API Key Persistence**: Automatic API key saving in browser's localStorage.
- **Test Mode**: Separate `download_and_decode.html` tool for testing decoding without regenerating (saves tokens).

## Usage

### Full Generation (wan22-16fps-8sec.html)

1. Open the generator page: [Wan2.2 Generator](https://yaplamyayaogon.github.io/javascript/wan22-16fps-8sec.html).
2. Enter your [RunningHub API Key](https://www.runninghub.ai/enterprise-api/consumerApi?inviteCode=qlbtubgi).
3. Select or drag & drop **Source Image** (node 396) and **Watermark Image** (node 411) — previews will appear instantly.
4. Configure LoRA settings (High/Low) and prompts if needed.
5. Click "Generate Video" and wait for the process to complete.
6. Preview decoded frames in the built-in player.
7. Export as WebM video or download individual frames.

### Test Mode (download_and_decode.html)

Use this tool to test decoding with already generated tasks (saves API tokens):

1. Open: [Download & Decode](https://yaplamyayaogon.github.io/javascript/download_and_decode.html).
2. Enter your API Key and **Task ID** from a previous generation.
3. Click "Download & Decode" — frames will be downloaded and decoded automatically.
4. Preview and export as WebM.

## Workflow

### Full Generation Pipeline (wan22-16fps-8sec.html)

1. **Upload** → Source and Watermark images uploaded to RunningHub
2. **Submit** → Task submitted to ComfyUI workflow (ID: 2068017342252146690)
3. **Process** → Polling status until generation completes
4. **Download** → 141 PNG frames + 1 watermark downloaded individually
5. **Decode** → Frames decoded in browser using `2 * shot - watermark` formula
6. **Play** → Preview decoded frames in canvas-based player
7. **Export** → Compile and download as WebM video (16 FPS)

### Test Mode Pipeline (download_and_decode.html)

1. **Query** → Fetch existing task results by Task ID
2. **Download** → 141 PNG frames + 1 watermark downloaded individually
3. **Decode** → Frames decoded in browser
4. **Play** → Preview in canvas player
5. **Export** → Compile and download as WebM video

## Technologies

- **Frontend**: Pure HTML/CSS/JavaScript (no framework)
- **Libraries**: JSZip (optional), MediaRecorder API (WebM encoding)
- **API**: RunningHub OpenAPI v2
- **Rendering**: HTML5 Canvas with OffscreenCanvas for performance
- **Video Codecs**: VP8, VP9, WebM (auto-detection for browser compatibility)

## Files

| File | Description |
|------|-------------|
| `wan22-16fps-8sec.html` | Full video generator with image upload and ComfyUI workflow submission |
| `download_and_decode.html` | Test tool for downloading and decoding existing tasks (saves tokens) |

## Browser Compatibility

- **Chrome/Chromium**: Full support (VP9, VP8)
- **Firefox**: VP8 codec (VP9 may not be available on some Linux distributions)
- **Safari**: Limited WebM support (consider using Chrome for best results)

## Partner Info

This project uses partner invite code `qlbtubgi` — support the development by using [this link](https://www.runninghub.ai/?inviteCode=qlbtubgi) to register on RunningHub.

## Changelog

### 2026-06-21

- **Fixed**: Workflow now handles 142 individual PNG files instead of ZIP archive
- **Added**: `download_and_decode.html` test tool for token-free decoding tests
- **Fixed**: VP8 codec fallback for browsers without VP9 support
- **Improved**: Detailed logging for download, decode, and encoding progress
- **Fixed**: Auto-detection of frames by `nodeId` (421 = frames, 422 = watermark)
