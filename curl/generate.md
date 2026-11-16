# Seedance 2.5 Flash API: cURL quickstart

```bash
export POYO_API_KEY="your-api-key"
export POYO_BASE_URL="https://api.poyo.ai"
```

## Text-to-video

```bash
curl -X POST "$POYO_BASE_URL/api/generate/submit" \
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

## First frame (image-to-video)

```bash
curl -X POST "$POYO_BASE_URL/api/generate/submit" \
  -H "Authorization: Bearer $POYO_API_KEY" \
  -H "Content-Type: application/json" \
  -d @payloads/seedance-2.5-flash-image-to-video.json
```

Add a second URL to `image_urls` to set the last frame as well.

## Image, video, and audio references

```bash
curl -X POST "$POYO_BASE_URL/api/generate/submit" \
  -H "Authorization: Bearer $POYO_API_KEY" \
  -H "Content-Type: application/json" \
  -d @payloads/seedance-2.5-flash-reference-to-video.json
```

The prompt names each input by upload order: `@Image1` is the fox, `@Video1` sets the motion and camera, and `@Audio1` sets the mood.

## Check status

Save `data.task_id` from the submit response, then poll:

```bash
curl "$POYO_BASE_URL/api/generate/status/<task_id>" \
  -H "Authorization: Bearer $POYO_API_KEY"
```

For production, add a public HTTPS `callback_url` to the top-level request and make the receiver idempotent.

See the [full README](../README.md) and [production notes](../docs/production-notes.md).
