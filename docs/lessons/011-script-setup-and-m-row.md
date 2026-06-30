# Script Setup and the M-row

## AI

- Question: How do we set up a complete script before calling the model?
- My answer:

```python
import os
import requests

api_key = os.getenv("DEEPSEEK_API_KEY")

if not api_key:
    raise RuntimeError("DEEPSEEK_API_KEY is missing")

URL = "https://api.deepseek.com/chat/completions"

headers = {
    "Authorization": f"Bearer {api_key}",
    "Content-Type": "application/json",
}
```

- What I learned:
  - We should load the API key from an environment variable to avoid leaking it in code.
  - `os` is the Python module used to read environment variables.
  - `api_key = os.getenv("DEEPSEEK_API_KEY")` reads the API key from the environment.
  - We check the API key early so the program fails with a clear local error instead of sending an invalid request.
  - `requests` is needed to send the HTTP request.
  - `Authorization` must be spelled correctly; misspelling it may cause a `401 Unauthorized` error.
  - `Content-Type: application/json` tells the server that the request body is JSON.

## English

Original:

> To avoid API key leaked

Natural expression:

> To avoid leaking the API key.

Original:

> It's better to check api_key before send to server

Natural expression:

> It is better to check the API key before sending the request to the server.

Original:

> api_key is unvalid

Natural expression:

> The API key is invalid.

New words:

- leak
- expose
- environment variable
- invalid
- misspell
- local error

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `たちつてと` — T-row
- `なにぬねの` — N-row
- `はひふへほ` — H-row
- `いぬ` — dog
- `ねこ` — cat
- `なつ` — summer
- `おと` — sound
- `はな` — flower / nose
- `ひと` — person
- `ほし` — star

Learned:

- `まみむめも` — ma, mi, mu, me, mo
- `まめ` — bean
- `みみ` — ear

Recall result:

- Correctly recalled all six previous rows: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの、はひふへほ`.
- First missed `なつ` and `おと`, and wrote `こえ` for sound; then corrected them to `なつ、おと`.
- Correctly recalled the full word set: `いぬ、ねこ、なつ、おと、はな、ひと、ほし`.
- Correctly typed the full M-row: `まみむめも`.
- Correctly wrote `まめ` for bean and `みみ` for ear.
- Final full recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの、はひふへほ、まみむめも、まめ、みみ`.

## Next step

- Combine the setup code and `ask_model(user_text)` into one runnable Python script.
- Review the seven kana rows and known words before learning the Y-row.
