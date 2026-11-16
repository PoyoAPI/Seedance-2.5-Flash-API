# Seedance 2.5 Flash API production notes

## Confirmed contract

- Endpoint: `POST /api/generate/submit`
- Model ID: `seedance-2.5-flash`
- Authentication: `Authorization: Bearer <POYO_API_KEY>`
- Status: `GET /api/generate/status/{task_id}`

## Input limits

| Field | Requirement | Constraint |
| --- | --- | --- |
| prompt | required | Video instructions; reference media as `@Image1`, `@Video1`, `@Audio1`. |
| duration | required | Integer from 4 to 30 seconds. |
| resolution | optional | 480p or 720p; default 720p. |
| aspect_ratio | optional | auto, 21:9, 16:9, 4:3, 1:1, 3:4, or 9:16; default auto. |
| generate_audio | optional | Default true. |
| image_urls | optional | 1–2 frames (first, last); JPEG, PNG, or WebP up to 30 MB each. |
| reference_image_urls | optional | Up to 10; JPEG, PNG, or WebP up to 30 MB each. |
| reference_video_urls | optional | Up to 5; MP4 or MOV, 2–30 s and up to 200 MB each; 30 s combined. |
| reference_audio_urls | optional | Up to 5, with reference images or videos; MP3 or WAV, 2–30 s and up to 15 MB each; 30 s combined. |

Send `image_urls` and the reference fields in separate requests. The combined reference video and audio durations are checked when the task is submitted.

## Operational checklist

- Keep API keys in a server-side secret manager.
- Validate user input before calling the API.
- Persist `data.task_id` immediately after submission.
- Use five-second polling only for development; prefer `callback_url` in production.
- Make webhook processing idempotent and reconcile status before fulfilling an order.
- Copy output files to durable storage after the task finishes.
- Recheck the live model page before hard-coding prices.

## Failure handling

Treat non-2xx HTTP responses and non-success API `code` values as errors. Parameter errors return HTTP 200 with `code: 400` in the body. Preserve the HTTP status, API code, and a redacted response body for debugging.

Schema: [PoYo API documentation](https://docs.poyo.ai/api-manual/video-series/seedance-2-5-flash?utm_source=github&utm_medium=readme&utm_campaign=seedance-2-5-flash-api)
