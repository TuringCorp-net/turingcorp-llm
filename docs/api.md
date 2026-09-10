# API Reference

## Endpoint

```
https://api.turingcorp.net/v1
```

OpenAI-compatible chat completions API.

## Available Models

| Model ID | Product | Tier | Status |
|------|------|:--:|:--:|
| `turingcorp/decider-junior-v1` | Decider | Junior | Preview |
| `turingcorp/decider-senior-v1` | Decider | Senior | Preview |
| `turingcorp/team-junior-v1.1` | Team | Junior | Preview |
| `turingcorp/team-senior-v1` | Team | Senior | Preview |
| `turingcorp/team-principal-v1` | Team | Principal | Preview |

Streaming is not available: requests with `stream: true` return 400. All responses are delivered as
a single JSON body.

## Usage

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.turingcorp.net/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="turingcorp/team-junior-v1.1",
    messages=[{"role": "user", "content": "Hello!"}]
)

print(response.choices[0].message.content)
```

Any OpenAI SDK or compatible client works without modification.

## Decider

Decider answers a judging question rather than an open one. Send the task and the two candidate
answers, and it returns the better option together with a confidence value:

```python
response = client.chat.completions.create(
    model="turingcorp/decider-junior-v1",
    messages=[{
        "role": "user",
        "content": (
            '{"task": "Which answer is better for the question: what is 17 x 23?",'
            ' "option_A": "391", "option_B": "381"}'
        ),
    }]
)

print(response.choices[0].message.content)
# {"betterOption": "option_A", "confidence": "100.0%", "reason": "..."}
```

---

## Preview License Key

The API is currently in a small-scale preview phase. Access is by invitation only.

To request a preview license key, email **iAsk@turingcorp.net** with:

- **Name** — your name or organization
- **Company** — your company or affiliation
- **Use Case** — what you plan to test or evaluate

We review requests promptly and will respond with a key and usage limits.
