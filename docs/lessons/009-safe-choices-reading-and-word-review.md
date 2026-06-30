# Safe Choices Reading and Word Review

## AI

- Question: How do we safely check `choices` before reading the assistant's answer?
- My answer:

```python
data = response.json()

if "choices" not in data:
    raise RuntimeError("Missing choices in response")

if not data["choices"]:
    raise RuntimeError("Empty choices in response")

answer = data["choices"][0]["message"]["content"]
print(answer)
```

- What I learned:
  - `"choices" not in data` is true when the parsed JSON dictionary does not contain the key `choices`.
  - We check for the key before reading `data["choices"][0]` to avoid a confusing `KeyError`.
  - If the response is `{"error": "invalid api key"}`, then `"choices" not in data` is true.
  - `if not data["choices"]:` is true when `data["choices"]` is empty or false-like.
  - If the response is `{"choices": []}`, then we should raise `RuntimeError("Empty choices in response")`.
  - Even after checking `choices`, the `message` key or `content` key might still be missing.
  - For this lesson, we chose to keep the code simple and only check missing `choices` and empty `choices`.

## English

Original:

> To avoid program breaking.

Natural expression:

> To avoid the program crashing.

Original:

> It means data["choices"] not None.

Natural expression:

> It is true if `data["choices"]` is empty or false-like.

Original:

> "message" and "content" might still be missing.

Natural expression:

> The `message` key or the `content` key might still be missing.

New words:

- contain
- key
- crashing
- false-like
- parsed JSON
- raw response

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `たちつてと` — T-row
- `なにぬねの` — N-row
- `かお` — face
- `こえ` — voice
- `あさ` — morning
- `した` — under / below
- `くつ` — shoes
- `とけい` — clock / watch
- `なに` — what
- `いぬ` — dog
- `ねこ` — cat

Learned:

- `なつ` — summer
- `おと` — sound

Recall result:

- Correctly recalled all five rows at the start: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの`.
- First wrote `f` for dog, then corrected it to `いぬ`.
- Correctly recalled `なに、いぬ、ねこ`.
- Correctly wrote `なつ` for summer and `おと` for sound.
- First wrote `かけくけこ` for the K-row, then corrected it to `かきくけこ`.
- Final full recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの、いぬ、ねこ、なつ、おと`.

## Next step

- Combine request sending, status-code checking, and safe `choices` reading into one complete function.
- Review the five kana rows and known words before learning the H-row.
