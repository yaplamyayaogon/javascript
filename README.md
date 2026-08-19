# RunningHub Video Generator

Generate videos from images via [RunningHub](https://www.runninghub.ai/?inviteCode=qlbtubgi) API.

## Generators

| File | Duration | Frames | FPS |
|------|----------|--------|-----|
| [wan22-16fps-8sec.html](https://yaplamyayaogon.github.io/javascript/wan22-16fps-8sec.html) | 8 sec | 141 | 16 |
| [wan22-16fps-6sec.html](https://yaplamyayaogon.github.io/javascript/wan22-16fps-6sec.html) | 6 sec | 97 | 16 |
| [minimax-h3-24fps-15sec.html](https://yaplamyayaogon.github.io/javascript/minimax-h3-24fps-15sec.html) | 15 sec | 360 | 24 |

## Tools

| File | Purpose |
|------|---------|
| [download_and_decode.html](https://yaplamyayaogon.github.io/javascript/download_and_decode.html) | Download and decode an existing task by Task ID |
| [local_decode_video.html](https://yaplamyayaogon.github.io/javascript/local_decode_video.html) | Decode local PNG/ZIP files without API |

## Usage

1. Enter your [API Key](https://www.runninghub.ai/enterprise-api/consumerApi?inviteCode=qlbtubgi)
2. Upload source image (watermark is loaded automatically)
3. Configure LoRA, aspect ratio (MiniMax H3 only)
4. Click "Generate Video"
5. Wait for decoding → preview → download WebM

## MiniMax H3 Features

- **3 LoRA slots** (LoRA 1/2/3) with individual strength
- **Aspect ratio** selector (1:1, 2:3, 3:2, 3:4, 4:3, 9:16, 16:9, 21:9)
- **Audio support** — auto-detects `ComfyUI_*.mp3` in results, FPS calculated from audio duration
- **24 FPS** default (vs 16 FPS in Wan2.2 generators)

## Share Settings

Click "Share Settings" to copy a URL with your current prompt, LoRA, and strength values. Opening the link auto-fills the fields. API Key is not included in the URL.

## Browsers

- **Chrome** — Full support
- **Firefox** — Full support (VP8/VP9 auto-detect)
- **Safari** — Limited