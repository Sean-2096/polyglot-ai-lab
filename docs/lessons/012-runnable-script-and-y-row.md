# Runnable Script and the Y-row

## AI

- Question: How do we combine setup code and `ask_model(user_text)` into one runnable script?
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

def ask_model(user_text):
    body = {
        "model": "deepseek-chat",
        "messages": [
            {"role": "user", "content": user_text},
        ],
    }

    response = requests.post(URL, headers=headers, json=body)

    if response.status_code != 200:
        raise RuntimeError(f"Request error: {response.status_code}, {response.text}")

    data = response.json()

    if "choices" not in data:
        raise RuntimeError("Missing choices in response")

    if not data["choices"]:
        raise RuntimeError("Empty choices in response")

    answer = data["choices"][0]["message"]["content"]
    return answer

answer = ask_model("Explain what an API is.")
print(answer)
```

- What I learned:
  - We import modules at the top so Python knows what `os` and `requests` mean before we use them.
  - The string passed into `ask_model(...)` becomes the `user_text` parameter, then becomes the `content` value in the message.
  - We store the result in `answer` so we can reuse it later.
  - `print(answer)` displays the returned answer.
  - A typo like `pritn(answer)` causes a `NameError`.
  - A typo inside a prompt string may not crash the program, but it gives the model a lower-quality prompt.
  - The HTTP header key must be `Authorization`, not `Authentication`.
  - The server expects the header name `Authorization`.

## English

Original:

> To be avoid not found error when use.

Natural expression:

> To avoid a "not defined" error when we use them.

Original:

> It becomes the content value.

Natural expression:

> It becomes the `user_text` parameter, and then it becomes the `content` value in the message.

Original:

> Because the server  expects Authorization.

Natural expression:

> Because the server expects `Authorization`.

New words:

- runnable script
- not defined
- parameter
- prompt
- lower-quality
- header name

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `たちつてと` — T-row
- `なにぬねの` — N-row
- `はひふへほ` — H-row
- `まみむめも` — M-row
- `いぬ` — dog
- `ねこ` — cat
- `なつ` — summer
- `おと` — sound
- `はな` — flower / nose
- `ひと` — person
- `ほし` — star
- `まめ` — bean
- `みみ` — ear

Learned:

- `やゆよ` — ya, yu, yo
- `やま` — mountain
- `ゆめ` — dream
- `やね` — roof

Recall result:

- First wrote `かきくえこ` for the K-row, then corrected it to `かきくけこ`.
- Correctly recalled all seven previous rows after correction.
- First forgot several words, then recovered them with grouped hints.
- Correctly recalled the full word set: `いぬ、ねこ、なつ、おと、はな、ひと、ほし、まめ、みみ`.
- Correctly typed the Y-row: `やゆよ`.
- Correctly wrote `やま`, `ゆめ`, and `やね`.
- First followed the skipped word `よる`, then corrected to `やね` because `る` has not been learned yet.
- First missed the T-row in final recall, then corrected it.
- Final full recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの、はひふへほ、まみむめも、やゆよ、やま、ゆめ、やね`.

## Next step

- Create the first actual runnable Python file for the DeepSeek request.
- Review the eight kana rows and known words before learning the R-row.
