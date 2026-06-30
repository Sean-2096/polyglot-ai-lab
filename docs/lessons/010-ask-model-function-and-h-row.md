# Ask Model Function and the H-row

## AI

- Question: How do we turn the request flow into a reusable function?
- My answer:

```python
def ask_model(user_text):
    body = {
        "model": "deepseek-chat",
        "messages": [{
            "role": "user",
            "content": user_text
        }]
    }

    response = requests.post(URL, headers=headers, json=body)

    if response.status_code != 200:
        raise RuntimeError(f"Request error: {response.status_code}, {response.text}")

    data = response.json()

    if "choices" not in data:
        raise RuntimeError("Missing choices key in response")

    if not data["choices"]:
        raise RuntimeError("Empty choices list in response")

    answer = data["choices"][0]["message"]["content"]
    return answer
```

- What I learned:
  - `user_text` is the text or question that the user wants to send to the model.
  - `user_text` is a function parameter, not just a temporary variable.
  - Using `user_text` makes the function dynamic, so it can send different user questions each time.
  - The function should return the assistant's answer text, not the whole server response.
  - `answer = data["choices"][0]["message"]["content"]` gets the assistant's answer from the parsed JSON data.
  - We can call the function with `ask_model("Explain what an API is.")`.
  - To see the returned answer, use `print(ask_model("Explain what an API is."))`.
  - A function avoids repeated code and makes the request easier to reuse.
  - One possible failure is a `401 Unauthorized` error.
  - Another possible failure is that the response does not contain `choices`.

## English

Original:

> The user_text means a temp variables.

Natural expression:

> `user_text` is the text or question that the user wants to send to the model.

Original:

> Because we can get dynamic question by user_text.

Natural expression:

> Because `user_text` lets us send a dynamic question.

Original:

> It is convience and simple to use a function.

Natural expression:

> It is convenient and simple to use a function.

Original:

> Maybe will return 401 Unzuthorized.

Natural expression:

> It may return a `401 Unauthorized` error.

New words:

- parameter
- dynamic
- reusable
- return value
- repeated code
- convenient

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `たちつてと` — T-row
- `なにぬねの` — N-row
- `いぬ` — dog
- `ねこ` — cat
- `なつ` — summer
- `おと` — sound
- `くつ` — shoes
- `とけい` — clock / watch

Learned:

- `はひふへほ` — ha, hi, fu, he, ho
- `ふ` is pronounced `fu`, not exactly `hu`
- `はな` — flower / nose
- `ひと` — person
- `ほし` — star

Recall result:

- Correctly recalled all five previous rows: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの`.
- Correctly recalled known words: `いぬ、ねこ、なつ、おと、くつ、とけい`.
- Correctly typed the full H-row: `はひふへほ`.
- Correctly recalled `はな`, `ひと`, and `ほし`.
- Final full recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの、はひふへほ、はな、ひと、ほし`.

## Next step

- Move `URL`, `headers`, and API-key loading into the complete function or a small script.
- Review the six kana rows and known words before learning the M-row.
