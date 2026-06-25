# API Key Safety and the K-row

## AI

- Question: How should a Python program read and validate an API key?
- My answer:

```python
api_key = os.getenv("DEEPSEEK_API_KEY")
if not api_key:
    raise RuntimeError("DEEPSEEK_API_KEY is missing")
```

- What I learned:
  - `requests` is a third-party package used to send HTTP requests.
  - API keys should not be hard-coded because they may be exposed in Git.
  - A published key should be revoked immediately and replaced.
  - `os.environ["DEEPSEEK_API_KEY"]` raises `KeyError` if the variable is missing.
  - `os.getenv("DEEPSEEK_API_KEY")` returns `None` if the variable is missing.
  - Raising `RuntimeError` stops the program before it sends an invalid request.
  - A missing local environment variable and a server `401 Unauthorized` response are different failures.

## English

Original:

> We should be avoid hard-code.

Natural expression:

> We should avoid hard-coding the API key.

Original:

> Because we used the if sentence.

Natural expression:

> Because the `if` statement raises an exception when the key is missing.

Original:

> The raise stop program execution and return error.

Natural expression:

> `raise` stops normal execution and raises an error.

New words:

- hard-code
- revoke
- environment variable
- exception
- `if` statement

## Japanese today

Reviewed:

- `あいうえお`
- `あお` — blue
- `うえ` — above/up
- `いえ` — house/home

Learned:

- `かきくけこ` — ka, ki, ku, ke, ko
- `かお` — face
- `かき` — persimmon
- `きく` — to listen / to ask
- `こえ` — voice

Recall result:

- Recalled both `あいうえお` and `かきくけこ` without romaji.
- Recalled `かお` and `こえ` from their meanings after one romaji correction.

## Next step

- Build the request headers safely and explain the `Bearer` authentication format.
- Review the vowel and K-rows before learning the S-row.
