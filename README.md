# RunningHub Video Generator

Generate videos from images via [RunningHub](https://www.runninghub.ai/?inviteCode=qlbtubgi) API.

## Generators

| File | Duration | Output | FPS |
|------|----------|--------|-----|
| [minimax-h3-ref2va-15sec-1img-1audio-3lora-1mp.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-ref2va-15sec-1img-1audio-3lora-1mp.html) | 15 sec | video | 24 |
| [minimax-h3-ref2va-15sec-6img-1audio-3lora-1mp-portrait.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-ref2va-15sec-6img-1audio-3lora-1mp-portrait.html) | 15 sec | video | 24 |
| [minimax-h3-15sec-1img-3lora.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-15sec-1img-3lora.html) | 15 sec | video | 24 |
| [minimax-h3-ref2va-15sec-5img-1audio-3lora.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-ref2va-15sec-5img-1audio-3lora.html) | 15 sec | video | 24 |
| [minimax-h3-24fps-15sec.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-24fps-15sec.html) | 15 sec | 360 frames | 24 |
| [wan22-16fps-6sec.html](https://yaplamyayaogon.github.io/javascript/wan22-16fps-6sec.html) | 6 sec | 97 frames | 16 |
| [wan22-16fps-8sec.html](https://yaplamyayaogon.github.io/javascript/wan22-16fps-8sec.html) | 8 sec | 141 frames | 16 |

## Tools

| File | Purpose |
|------|---------|
| [download_and_decode.html](https://yaplamyayaogon.github.io/javascript/download_and_decode.html) | Download and decode an existing task by Task ID |
| [local_decode_video.html](https://yaplamyayaogon.github.io/javascript/local_decode_video.html) | Decode local PNG/ZIP files without API |

## Usage

1. Enter your [API Key](https://www.runninghub.ai/enterprise-api/consumerApi?inviteCode=qlbtubgi)
2. Upload image(s) and audio (if supported)
3. Configure prompt, LoRA, aspect ratio (if available)
4. Click "Generate Video"
5. Preview → download (result URL valid for 24 hours)

## MiniMax H3 Ref2VA (1 Image + Audio) Features

- **1 image slot** (required) — resolution follows Picture 1
- **1 audio slot** (optional) — audio or mp4
- **Prompt tags** — reference the image as `<Picture 1>` and audio as `<Audio 1>` in the prompt
- **Default prompt** — subject definitions template pre-filled
- **3 LoRA slots** with individual strength
- **1 MP output** — fixed resolution, no aspect ratio selector

## MiniMax H3 Ref2VA (6 Images) Features

- **6 image slots** — Picture 1 (required) + Picture 2–6 (optional, workflow defaults used if not selected)
- **1 audio slot** (optional) — audio or mp4
- **Prompt tags** — reference images as `<Picture 1>`...`<Picture 6>` and audio as `<Audio 1>` in the prompt
- **Default prompt** — subject definitions template pre-filled
- **3 LoRA slots** with individual strength
- **1 MP output** — fixed resolution, no aspect ratio selector
- **Portrait 9:16** aspect ratio
- **Aspect ratio** selector

## MiniMax H3 Features

## MiniMax H3 Ref2VA Features

- **5 image slots** — Picture 0 (required) + Picture 1–4 (optional, workflow defaults used if not selected)
- **1 audio slot** (optional) — audio or mp4
- **Prompt tags** — reference images as `<Picture 0>`...`<Picture 4>` and audio as `<Audio 0>` in the prompt
- **3 LoRA slots** with individual strength
- **Aspect ratio** selector

## MiniMax H3 Features

- **3 LoRA slots** (LoRA 1/2/3) with individual strength
- **Aspect ratio** selector (1:1, 2:3, 3:2, 3:4, 4:3, 9:16, 16:9, 21:9)
- **Audio support** — auto-detects `ComfyUI_*.mp3` in results, FPS calculated from audio duration
- **Frame decoding in browser** — decodes ~360 frames with watermark removal, exports WebM with audio
- **24 FPS** default (vs 16 FPS in Wan2.2 generators)

## Share Settings

Click "Share Settings" to copy a URL with your current prompt, LoRA, and strength values. Opening the link auto-fills the fields. API Key is not included in the URL.

## Browsers

- **Chrome** — Full support
- **Firefox** — Full support (VP8/VP9 auto-detect)
- **Safari** — Limited