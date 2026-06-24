<p align="center">
  <a href="https://github.com/runapi-ai/minimax">
    <h3 align="center">MiniMax API Skill for RunAPI</h3>
  </a>
</p>

<p align="center">
  Configure OpenAI-compatible clients to use MiniMax text models on RunAPI.
</p>

<p align="center">
  <a href="https://runapi.ai/models/minimax"><strong>Model Reference</strong></a> | <a href="https://github.com/runapi-ai/minimax"><strong>Skill Repo</strong></a> | <a href="https://runapi.ai/models"><strong>All Models</strong></a>
</p>

<div align="center">

[![skills.sh](https://www.skills.sh/b/runapi-ai/minimax)](https://www.skills.sh/runapi-ai/minimax/minimax)
[![ClawHub](https://img.shields.io/badge/ClawHub-runapi--minimax-111827)](https://clawhub.ai/runapi-ai/runapi-minimax)
[![License](https://img.shields.io/github/license/runapi-ai/minimax)](https://github.com/runapi-ai/minimax/blob/main/LICENSE)

</div>
<br/>

Call MiniMax text models through RunAPI with the official OpenAI SDK or any
OpenAI-compatible client. Point clients at `https://runapi.ai/v1`, send
`MiniMax-M3`, `MiniMax-M2.7`, `MiniMax-M2.7-highspeed`, `MiniMax-M2.5`,
`MiniMax-M2.5-highspeed`, `MiniMax-M2.1`, or `MiniMax-M2`, and pay through one
RunAPI balance. This skill teaches Claude Code, Codex, Gemini CLI, Cursor, and
50+ agents how to wire MiniMax text requests through RunAPI.

The canonical agent file is `skills/minimax/SKILL.md`.

## Install the skill

```bash
npx skills add runapi-ai/minimax -g
```

Or paste this prompt to your AI agent:

```text
Install the minimax skill for me:

1. Clone https://github.com/runapi-ai/minimax
2. Copy the skills/minimax/ directory into your
   user-level skills directory (e.g. ~/.claude/skills/
   for Claude Code, ~/.codex/skills/ for Codex).
3. Verify that SKILL.md is present.
4. Confirm the install path when done.
```

## Use MiniMax on RunAPI

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_RUNAPI_TOKEN",
    base_url="https://runapi.ai/v1",
)

response = client.chat.completions.create(
    model="MiniMax-M3",
    messages=[{"role": "user", "content": "Hello, MiniMax!"}],
)
print(response.choices[0].message.content)
```

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "YOUR_RUNAPI_TOKEN",
  baseURL: "https://runapi.ai/v1",
});

const response = await client.chat.completions.create({
  model: "MiniMax-M2.7-highspeed",
  messages: [{ role: "user", content: "Hello, MiniMax!" }],
});
console.log(response.choices[0].message.content);
```

Get a RunAPI API Key at <https://runapi.ai/api_keys>.

## Supported MiniMax text models

| Model ID | Notes |
|---|---|
| `MiniMax-M3` | Latest MiniMax text chat |
| `MiniMax-M2.7` | MiniMax M2.7 compatibility |
| `MiniMax-M2.7-highspeed` | Faster MiniMax M2.7 requests |
| `MiniMax-M2.5` | MiniMax M2.5 compatibility |
| `MiniMax-M2.5-highspeed` | Faster MiniMax M2.5 requests |
| `MiniMax-M2.1` | MiniMax M2.1 compatibility |
| `MiniMax-M2` | MiniMax M2 compatibility |

## Routing

- MiniMax API on RunAPI: <https://runapi.ai/models/minimax>
- Provider page: <https://runapi.ai/providers/minimax>
- Browse the full RunAPI catalog: <https://runapi.ai/models>
- Skill repository: <https://github.com/runapi-ai/minimax>

## Agent rules

- Keep API keys in `OPENAI_API_KEY` or your secret manager; never inline them in
  commits or shell history.
- Stream long responses (`stream: true`) so the agent can release the
  terminal/IO loop early.
- This skill is for MiniMax text models. Use the Hailuo skill for video.
- For pricing, rate-limit, and commercial-usage answers, link to
  <https://runapi.ai/models/minimax> rather than this README.

## License

Licensed under the Apache License, Version 2.0.
