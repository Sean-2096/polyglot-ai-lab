# Request Headers and the S-row

## AI

- Question: What information should request headers send to an LLM API server?
- My answer:

```python
headers = {
    "Authorization": f"Bearer {api_key}",
    "Content-Type": "application/json",
}
```

- What I learned:
  - `Authorization` carries authentication information.
  - `Bearer` is the authentication scheme used before the API key.
  - If `api_key = "abc123"`, then `f"Bearer {api_key}"` becomes `Bearer abc123`.
  - The space after `Bearer` matters because it helps the server separate the authentication scheme from the token.
  - `Content-Type: application/json` tells the server that the request body is JSON.
  - A wrong or missing API key may cause a `401 Unauthorized` error.
  - A malformed URL may cause a `404 Not Found` error.

## English

Original:

> It convennice for the server read api_key.

Natural expression:

> It helps the server separate the authentication scheme from the API key.

Original:

> The server will return 401 Unauthorized error.

Natural expression:

> The server may return a `401 Unauthorized` error.

New words:

- header
- authentication
- scheme
- token
- separate

## Japanese today

Reviewed:

- `あいうえお` — a, i, u, e, o
- `かきくけこ` — ka, ki, ku, ke, ko
- `かお` — face
- `こえ` — voice

Learned:

- `さしすせそ` — sa, shi, su, se, so
- `すし` — sushi
- `あさ` — morning
- `そこ` — there

Recall result:

- Recalled `あいうえお`, `かきくけこ`, and `さしすせそ` without romaji.
- Recalled `かお` and `こえ` after meaning hints.
- Correctly wrote `あさ` for morning and `そこ` for there.

## Next step

- Build the request body and explain how `model` and `messages` become data sent to the server.
- Review the vowel, K, and S rows before learning the T-row.
