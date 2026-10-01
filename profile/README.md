<p align="center">
  <a href="https://beemotion.app">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
      <img alt="BeEmotion" src="assets/logo-light.png" width="420">
    </picture>
  </a>
</p>

<p align="center">
  <b>Vision AI that understands people.</b><br>
  Faces, emotion, head and body pose, objects, text and speech, from one REST API, an MCP server and an OpenAI-compatible chat endpoint.
</p>

<p align="center">
  <a href="https://beemotion.app">Website</a> ·
  <a href="https://docs.beemotion.app">Docs</a> ·
  <a href="https://docs.beemotion.app/quickstart">Quickstart</a> ·
  <a href="https://api.beemotion.app/v1/openapi.json">OpenAPI</a> ·
  <a href="https://docs.beemotion.app/changelog">Changelog</a>
</p>

<table>
  <tr>
    <td align="center" width="33%"><img src="assets/emotion.png" alt="Faces with emotion labels"><br><sub><b>Emotion</b>: seven labels plus valence and arousal</sub></td>
    <td align="center" width="33%"><img src="assets/body-pose.png" alt="People with whole-body keypoints"><br><sub><b>Body pose</b>: 133 whole-body keypoints</sub></td>
    <td align="center" width="33%"><img src="assets/open-vocabulary-detection.png" alt="Laptops found by name"><br><sub><b>Open-vocabulary detection</b>: find things by name</sub></td>
  </tr>
</table>

## Try it

```bash
export BEEMOTION_API_KEY="be_live_..."   # create one at beemotion.app > Developer > API keys

curl https://api.beemotion.app/v1/image/analyze \
  -H "Authorization: Bearer $BEEMOTION_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"image_url": "https://docs.beemotion.app/images/samples/crew-expedition-14.jpg", "tasks": ["face", "emotion"]}'
```

```python
# pip install beemotion
from beemotion import Client

result = Client().image.analyze("photo.jpg", tasks=["face", "emotion"])
```

New accounts get $5 of free credit. Failed calls are free.

## What it does

| Capability | Task | |
|---|---|---|
| Face detection and head pose | `face` | [docs](https://docs.beemotion.app/capabilities/face-detection) |
| Emotion, valence and arousal | `emotion` | [docs](https://docs.beemotion.app/capabilities/emotion) |
| Whole-body pose | `pose` | [docs](https://docs.beemotion.app/capabilities/body-pose) |
| Object detection | `object` | [docs](https://docs.beemotion.app/capabilities/object-detection) |
| Face recognition against your own consented gallery | `recognition` | [docs](https://docs.beemotion.app/capabilities/face-recognition) |
| Captions, OCR and open-vocabulary detection | `caption`, `ocr`, `open_vocab_detection` | [docs](https://docs.beemotion.app/capabilities/captions) |
| Video tracking and speech transcripts | `POST /v1/video/analyze` | [docs](https://docs.beemotion.app/guides/video-and-webhooks) |
| Questions about images | `POST /v1/openai/chat/completions` | [docs](https://docs.beemotion.app/capabilities/chat-with-images) |

## Use it from your coding agent

```bash
claude mcp add --transport http beemotion https://api.beemotion.app/mcp \
  --header "Authorization: Bearer $BEEMOTION_API_KEY"
```

The MCP server works with Claude Code, Cursor, Codex and any Streamable HTTP client. See [MCP and agent skills](https://docs.beemotion.app/guides/mcp-and-skills).

## Repositories

| Repo | What's inside |
|---|---|
| [beem-python](https://github.com/beem-ai/beem-python) | Python SDK and `beemotion` CLI |
| [beem-skills](https://github.com/beem-ai/beem-skills) | Agent skill (`SKILL.md`) and MCP client configs |
| [beem-cookbook](https://github.com/beem-ai/beem-cookbook) | Notebooks, demo apps and starter templates |
| [beem-docs](https://github.com/beem-ai/beem-docs) | Source of [docs.beemotion.app](https://docs.beemotion.app) |

<sub>Sample photos: NASA, public domain. Annotations drawn from real BeEmotion API responses.</sub>
