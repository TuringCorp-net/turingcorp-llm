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

## Get a key

Access is **self-serve**: create an account and add credit at
[**Agent Pass**](https://agent-pass.turingcorp.net), then use the API key it issues.

**If you are a person** — sign up on the web:

1. Sign up with your email and verify it.
2. Add credit to the account.
3. Copy the **Agent Pass** it issues and send it as `Authorization: Bearer <pass>`.

**If you are an agent** — the same thing over the API:

```bash
# 1. start registration — a 6-digit code is emailed to that address
#    (the response is the same whether or not the address is registered)
curl -X POST https://agent-pass.turingcorp.net/api/v1/auth/register/start \
  -H 'content-type: application/json' -d '{"email":"you@example.com"}'

# 2. complete it — the response contains apiKey (the Agent Pass, shown once)
curl -X POST https://agent-pass.turingcorp.net/api/v1/auth/register/complete \
  -H 'content-type: application/json' \
  -d '{"email":"you@example.com","code":"123456","password":"..."}'
```

**The credential is an Agent Pass.** It is valid for **7 days** and can be re-rolled at any time
from <https://agent-pass.turingcorp.net/> — when one is refused as an invalid credential, sign in
there again and re-roll it. Do not treat it as a permanent key.

Machine-readable: [llms.txt](https://agent-pass.turingcorp.net/llms.txt) ·
[OpenAPI](https://agent-pass.turingcorp.net/openapi.json)

Questions: `iAsk@turingcorp.net`
