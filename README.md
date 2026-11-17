# Seedance 2.5 Flash API: cURL, Python, and Node.js Examples

[![Seedance 2.5 Flash on PoYo](https://img.shields.io/badge/Try%20on%20PoYo-seedance--2.5--flash-84cc16)](https://poyo.ai/models/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api) [![API docs](https://img.shields.io/badge/API-docs-22d3ee)](https://docs.poyo.ai/api-manual/video-series/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api) [![Check](https://github.com/PoyoAPI/Seedance-2.5-Flash-API/actions/workflows/check.yml/badge.svg)](https://github.com/PoyoAPI/Seedance-2.5-Flash-API/actions/workflows/check.yml)

Runnable examples for ByteDance **Seedance 2.5 Flash** through PoYo's async video API: 4–30 second 480p or 720p videos with synchronized audio from text, first and last frames, or image, video, and audio references.

**Answer:** To use the Seedance 2.5 Flash API, send a server-side request to `POST https://api.poyo.ai/api/generate/submit` with model `seedance-2.5-flash` and a PoYo API key, then poll `GET https://api.poyo.ai/api/generate/status/{task_id}`. The examples in this repository run with Python 3.9+, Node.js 22+, or cURL.

Last verified against the live PoYo schema and pricing on **November 16, 2026**.

## Seedance 2.5 Flash at a glance

- **Model ID:** `seedance-2.5-flash` on `POST https://api.poyo.ai/api/generate/submit`
- **Released:** November 12, 2026 by ByteDance; live on PoYo since November 16, 2026
- **Output:** 480p or 720p (default 720p), 4–30 seconds, with synchronized audio on by default
- **Inputs:** text, a first frame with an optional last frame, or up to 10 reference images, 5 reference videos, and 5 reference audio clips
- **Aspect ratios:** auto, 21:9, 16:9, 4:3, 1:1, 3:4, 9:16
- **Price:** from 18.5 credits ($0.0925) per second at 480p and 41 credits ($0.205) per second at 720p
- **Speed:** nearly twice as fast as Seedance 2.5, according to ByteDance

## Seedance 2.5 Flash API examples (video)

Real Seedance 2.5 Flash outputs generated through PoYo. The previews are silent GIFs; click one to open the MP4 with its generated audio.

<table>
<tr>
<td align="center" valign="top"><a href="https://storage.poyo.ai/models/seedance-2-5-flash/examples/text-to-video-paper-boat-480p-96257f2cfcbe.mp4"><img src="assets/text-to-video-paper-boat.gif" width="400" alt="Seedance 2.5 Flash API text-to-video example: paper boat in a rainy street at dusk"></a><br><b>Text-to-video · 480p · 4 s · 74 credits</b><br><sub>The output of <code>payloads/seedance-2.5-flash-text-to-video.json</code></sub></td>
<td align="center" valign="top"><a href="https://storage.poyo.ai/models/seedance-2-5-flash/examples/default-rainy-violinist-720p-1d863c9c28ee.mp4"><img src="assets/rainy-violinist.gif" width="400" alt="Seedance 2.5 Flash API example: Close-up to pull-back with rain ambience and violin"></a><br><b>Text-to-video · 720p · 8 s · 328 credits</b><br><sub>Close-up to pull-back with rain ambience and violin</sub></td>
</tr>
<tr>
<td align="center" valign="top"><a href="https://storage.poyo.ai/models/seedance-2-5-flash/media/thirty-second-timestamp-story-720p-1cca18e01872.mp4"><img src="assets/thirty-second-story.gif" width="400" alt="Seedance 2.5 Flash API example: Five timestamped beats with dialogue, waves, and piano"></a><br><b>30-second single take · 720p · 1,230 credits</b><br><sub>Five timestamped beats with dialogue, waves, and piano</sub></td>
<td align="center" valign="top"><a href="https://storage.poyo.ai/models/seedance-2-5-flash/examples/vertical-bakery-480p-ee25429845a4.mp4"><img src="assets/vertical-bakery.gif" width="224" alt="Seedance 2.5 Flash API example: Handheld shot with spoken line and kitchen sounds"></a><br><b>Vertical 9:16 · 480p · 10 s · 185 credits</b><br><sub>Handheld shot with spoken line and kitchen sounds</sub></td>
</tr>
</table>

<details>
<summary>Prompt: paper boat (text-to-video, 480p, 4 s)</summary>

```text
A paper boat drifts down a rain-filled street gutter at dusk, neon reflections rippling on the water, soft rain sounds.
```

</details>

<details>
<summary>Prompt: rainy violinist (720p, 8 s)</summary>

```text
A street violinist in a dark wool coat plays under an old lamppost on a rainy cobblestone street at dusk. Close-up of fingers pressing the strings and the bow catching the warm light, then a slow pull-back reveals glowing shop windows, reflections on wet stones, and passersby with umbrellas slowing down to listen. Natural rain ambience and a gentle, expressive violin melody.
```

</details>

<details>
<summary>Prompt: 30-second timestamped story (720p, 30 s)</summary>

```text
One continuous 30-second story of the same young woman in a yellow raincoat delivering a handwritten letter across a small seaside town at dawn. 0-6s: wide aerial shot of the sleepy harbor town, fishing boats rocking, soft morning light; she rides an old bicycle down a cobblestone hill. 6-12s: tracking shot beside her as she weaves past a fish market, seagulls lifting off, a vendor waves at her. 12-18s: low-angle shot as she climbs a steep stone staircase carrying the bicycle, breathing hard, the letter tucked in her pocket. 18-24s: she knocks on a blue door at the top; an elderly man opens it and she hands him the letter. 24-30s: close-up of the man reading, his eyes filling with tears; he smiles and says softly, "She remembered." Camera slowly pulls back to reveal the sunrise over the sea. Natural ambient sound: waves, gulls, bicycle bell, footsteps, gentle piano music. No subtitles, no on-screen text.
```

</details>

<details>
<summary>Prompt: vertical bakery (9:16, 480p, 10 s)</summary>

```text
Vertical handheld shot: a young baker in a small morning bakery pulls a tray of golden croissants from the oven, steam rising in the warm light, then turns to the camera with a proud smile and says, "Fresh out of the oven." Gentle kitchen sounds and soft acoustic background music.
```

</details>

## What is Seedance 2.5 Flash?

Seedance 2.5 Flash is the faster, lower-cost tier of ByteDance Seedance 2.5. According to ByteDance, it generates nearly twice as fast as Seedance 2.5. It keeps the Seedance 2.5 request shape at 480p and 720p, with synchronized dialogue, sound effects, and music generated in the same pass.

| | Seedance 2.5 Flash | Seedance 2.5 |
| --- | --- | --- |
| Model ID | `seedance-2.5-flash` | `seedance-2.5` |
| Resolution | 480p, 720p (default 720p) | 480p, 720p, 1080p |
| Duration | 4–30 seconds | 4–30 seconds |
| Synchronized audio | On by default | Optional |
| Reference images / videos / audio | up to 10 / 5 / 5 | up to 30 / 10 / 10 |
| 480p, no reference video | 18.5 credits ($0.0925) per second | 28 credits ($0.14) per second |
| 720p, no reference video | 41 credits ($0.205) per second | 63 credits ($0.315) per second |

Choose Flash for drafts, high-volume social clips, and fast iteration. For 1080p delivery or more than 10 reference images, use [Seedance 2.5](https://github.com/PoyoAPI/Seedance-2.5-API).

## Quickstart

1. Create a key in the [PoYo dashboard](https://poyo.ai/dashboard/api-key?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api).
2. Copy `.env.example` to `.env` and replace the placeholder.
3. Run one of the examples. Each submits the task and polls until `finished` or `failed`.

```dotenv
POYO_API_KEY=YOUR_POYO_API_KEY_HERE
POYO_BASE_URL=https://api.poyo.ai
```

### Python

```bash
python python/generate.py
python python/generate.py payloads/seedance-2.5-flash-reference-to-video.json
```

[`python/generate.py`](python/generate.py) uses only the Python standard library.

### Node.js

```bash
node node/index.mjs
node node/index.mjs payloads/seedance-2.5-flash-image-to-video.json
```

### cURL

```bash
curl -X POST "https://api.poyo.ai/api/generate/submit" \
  -H "Authorization: Bearer $POYO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "model": "seedance-2.5-flash",
  "input": {
    "prompt": "A paper boat drifts down a rain-filled street gutter at dusk, neon reflections rippling on the water, soft rain sounds.",
    "duration": 4,
    "resolution": "480p",
    "aspect_ratio": "16:9"
  }
}'
```

Status polling and the other modes are in [curl/generate.md](curl/generate.md).

## Example requests

Every file in [`payloads/`](payloads) is a complete request body with public input media, so it runs as-is.

| File | Mode | Settings | Credits |
| --- | --- | --- | --- |
| [`seedance-2.5-flash-text-to-video.json`](payloads/seedance-2.5-flash-text-to-video.json) | Text-to-video | 480p, 4 s, audio on | 74 ($0.37) |
| [`seedance-2.5-flash-image-to-video.json`](payloads/seedance-2.5-flash-image-to-video.json) | First frame | 480p, 4 s, `aspect_ratio: auto` | 74 ($0.37) |
| [`seedance-2.5-flash-reference-to-video.json`](payloads/seedance-2.5-flash-reference-to-video.json) | `@Image1` + `@Video1` + `@Audio1` | 480p, 4 s + reference video | 69 ($0.345) |

## Input modes

The supplied media selects the mode automatically.

| Mode | Selected when |
| --- | --- |
| Reference-to-video | `reference_image_urls`, `reference_video_urls`, or `reference_audio_urls` is non-empty |
| Image-to-video (first / last frame) | `image_urls` is non-empty |
| Text-to-video | No media is provided |

Send `image_urls` and the reference fields in separate requests. In first/last-frame mode, keep `aspect_ratio` at `auto` so the output follows the first frame, and use a last frame with the same shape. In the prompt, refer to reference media by upload order as `@Image1`, `@Video1`, and `@Audio1`, and give each item a role.

## Writing Seedance 2.5 Flash prompts

- **Long single takes:** split a 30-second prompt into timestamped beats, such as `0-6s: wide aerial shot of the harbor town ... 24-30s: close-up of the man reading`, and keep one subject and setting across beats.
- **Audio in the same pass:** describe dialogue in quotes, plus ambience, sound effects, and music. Add "no background music" to drop a layer, or set `generate_audio` to `false` for a silent clip.
- **References with roles:** name every input by upload order and give it one job, for example "@Image1 is the cat, @Image2 is the scarf, match the rhythm of @Audio1".
- **First and last frames:** describe the change between the two frames, keep `aspect_ratio` at `auto`, and use two images of the same shape.
- **Draft, then render:** iterate at 480p, then render the final cut at 720p, or switch the model ID to `seedance-2.5` for 1080p.

A complete 30-second timestamped prompt is in the [API reference](https://docs.poyo.ai/api-manual/video-series/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api).

## Request fields

| Field | Requirement | Meaning |
| --- | --- | --- |
| prompt | required | Video instructions; reference media as `@Image1`, `@Video1`, `@Audio1`. |
| duration | required | Integer from 4 to 30 seconds. |
| resolution | optional | `480p` or `720p`. Default `720p`. |
| aspect_ratio | optional | `auto`, `21:9`, `16:9`, `4:3`, `1:1`, `3:4`, or `9:16`. Default `auto`. |
| generate_audio | optional | Synchronized audio. Default `true`; `false` returns video only. |
| image_urls | optional | First frame, or first and last frame. JPEG, PNG, or WebP up to 30 MB each. |
| reference_image_urls | optional | Up to 10 images. JPEG, PNG, or WebP up to 30 MB each. |
| reference_video_urls | optional | Up to 5 videos. MP4 or MOV, 2–30 s and up to 200 MB each; 30 s combined. |
| reference_audio_urls | optional | Up to 5 clips with reference images or videos. MP3 or WAV, 2–30 s and up to 15 MB each; 30 s combined. |

## Pricing

Billing is per second. 1 credit = $0.005.

| Resolution | No reference video | With reference video |
| --- | --- | --- |
| 480p | 18.5 credits ($0.0925) per second | 11.5 credits ($0.0575) per billed second |
| 720p | 41 credits ($0.205) per second | 25.5 credits ($0.1275) per billed second |

Without reference video, billed seconds equal the output duration. With `reference_video_urls`, billed seconds are the output duration plus each reference video's duration floored to whole seconds. Confirm current prices on the [model page](https://poyo.ai/models/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api) before a production rollout.

### Cost per clip

Without reference videos:

| Clip length | 480p | 720p |
| --- | --- | --- |
| 5 seconds | 92.5 credits ($0.4625) | 205 credits ($1.025) |
| 10 seconds | 185 credits ($0.925) | 410 credits ($2.05) |
| 30 seconds | 555 credits ($2.775) | 1,230 credits ($6.15) |

Failed generation tasks are not charged credits.

## Async production flow

```text
submit -> persist data.task_id -> poll during development -> receive callback_url webhook in production
```

Treat `finished` and `failed` as terminal states. Accept a webhook only for task IDs your system created, process it idempotently, and reconcile the final state through the status endpoint. Copy output videos to your own storage after the task finishes.

## Common errors

Always read `code` in the response body: parameter errors return HTTP 200 with `code: 400`.

| `code` | `error.type` | Example and fix |
| --- | --- | --- |
| 400 | `validation_error` | `duration must be between 4 and 30` or `resolution must be 480p or 720p`: correct the field and resubmit. |
| 400 | `content_moderation_error` | The prompt or media was declined by safety review: revise and submit a new task. |
| 401 | `authentication_error` | Missing or invalid key: send `Authorization: Bearer <POYO_API_KEY>`. |
| 402 | `insufficient_credits_error` | Top up credits in the [dashboard](https://poyo.ai/dashboard?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api). |
| 429 | `rate_limit_error` | Back off and retry. |

A task that fails after submission returns `status: "failed"` with `error_message`, and is not charged credits. See [error codes](https://docs.poyo.ai/api-manual/error-codes?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api).

## FAQ

**Is Seedance 2.5 Flash free to use?** It is pay-as-you-go on PoYo, with no subscription or minimum spend. Eligible new accounts receive trial credits at sign-up, which you can use in the [Playground](https://poyo.ai/models/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api) before integrating the API.

**How much does Seedance 2.5 Flash cost per second?** 18.5 credits ($0.0925) per second at 480p and 41 credits ($0.205) per second at 720p. With reference videos, the rates are 11.5 and 25.5 credits per billed second, where billed seconds include the reference video length.

**How is Seedance 2.5 Flash different from Seedance 2.5?** Both take the same request fields and produce 4–30 second videos with audio. Flash outputs 480p or 720p and accepts up to 10 images, 5 videos, and 5 audio clips; Seedance 2.5 adds 1080p and accepts up to 30, 10, and 10.

**Can Seedance 2.5 Flash make 1080p or 4K video?** Flash outputs 480p or 720p, with 720p as the default. For native 1080p, switch the model ID to `seedance-2.5`, which takes the same request fields.

**How long does a generation take?** In PoYo testing on November 16, 2026, a 4-second 480p clip finished in about two minutes and a 30-second 720p clip in under three minutes, end to end. Times vary with load and settings.

**Can I turn the audio off?** Yes. Audio is generated by default; set `generate_audio` to `false` for a silent clip, or drop individual layers in the prompt.

**How many reference files can one request use?** Up to 10 reference images, 5 reference videos, and 5 reference audio clips. Reference videos together can last up to 30 seconds, and so can reference audio clips. Audio references are used together with at least one reference image or video.

**Can I use it from an AI agent?** Yes. The [PoYo MCP bridge](https://github.com/PoyoAPI/poyo-devtools) exposes the model as the `poyo_seedance_2_5_flash` tool.

## Repository map

- [`payloads/`](payloads) — complete request bodies for each mode
- [`python/generate.py`](python/generate.py) — standard-library Python example
- [`node/index.mjs`](node/index.mjs) — dependency-free Node.js example
- [`curl/generate.md`](curl/generate.md) — copy-paste cURL requests
- [`docs/production-notes.md`](docs/production-notes.md) — limits and rollout checklist

## Related repositories

- [seedance-2-5-api](https://github.com/PoyoAPI/Seedance-2.5-API) — Seedance 2.5 with 1080p and larger reference sets
- [seedance-2-mini-api](https://github.com/PoyoAPI/Seedance-2.0-Mini-API) — Seedance 2.0 Mini examples
- [poyo-examples](https://github.com/PoyoAPI/poyo-examples) — examples across PoYo models
- [poyo-devtools](https://github.com/PoyoAPI/poyo-devtools) — PoYo CLI, MCP bridge, and Agent Skill (MCP tool `poyo_seedance_2_5_flash`)

## Links

- [Seedance 2.5 Flash API on PoYo](https://poyo.ai/models/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api)
- [Seedance 2.5 Flash API reference](https://docs.poyo.ai/api-manual/video-series/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api)
- [PoYo model catalog](https://poyo.ai/models?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api)

## License

MIT
