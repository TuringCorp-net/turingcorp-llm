# API Reference

## Endpoint

```
https://api.turingcorp.net/v1
```

OpenAI-compatible chat completions API.

## Available Models

| Model ID | Status |
|------|:--:|
| `turingcorp/team-junior-v1` | Preview |
| `turingcorp/team-senior-v1` | Preview |
| `turingcorp/team-principal-v1` | Preview |

## Usage

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.turingcorp.net/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="turingcorp/team-junior-v1",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

Any OpenAI SDK or compatible client works without modification.
