# Error Handling and the N-row

## AI

- Question: How do we stop early when an API request fails?
- My answer:

```python
response = requests.post(URL, headers=headers, json=body)

if response.status_code != 200:
    raise RuntimeError(f"Request failed: {response.status_code}, {response.text}")

data = response.json()
answer = data["choices"][0]["message"]["content"]
print(answer)
```

- What I learned:
  - `response.status_code != 200` means the status code is not `200`.
  - This condition checks whether the request was not successful.
  - We raise early so the program stops with a clear error message before trying to parse a failed response.
  - The error message includes the server's response status code and error text.
  - If the status code is `401`, the response text may say the request is unauthorized.
  - If the status code is `200`, the `raise RuntimeError(...)` line does not run because the `if` condition is false.
  - After a successful response, the program converts the response to JSON, gets the assistant's answer, and prints it.
  - An f-string such as `f"Request failed: {status_code}"` inserts variable values into a string.

## English

Original:

> response.status_code must be 200.

Natural expression:

> It checks whether the request was not successful.

Original:

> Avoided unknown error.

Natural expression:

> To avoid an unknown error later.

Original:

> This error message includes the server's response status code and response errot text.

Natural expression:

> This error message includes the server's response status code and error text.

Original:

> f"..." is a output format function.

Natural expression:

> `f"..."` is an f-string. It lets us insert variable values into a string.

New words:

- condition
- not equal
- raise early
- parse
- f-string
- insert

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `たちつてと` — T-row
- `かお` — face
- `こえ` — voice
- `あさ` — morning
- `した` — under / below
- `くつ` — shoes
- `とけい` — clock / watch

Learned:

- `なにぬねの` — na, ni, nu, ne, no
- `なに` — what
- `いぬ` — dog
- `ねこ` — cat

Recall result:

- Correctly recalled all four previous rows: `あいうえお、かきくけこ、さしすせそ、たちつてと`.
- First missed `くつ` in the six-word review, then correctly recalled it.
- Correctly typed the N-row: `なにぬねの`.
- Correctly wrote `いぬ` for dog.
- First wrote `ねの` for cat, then corrected it to `ねこ`.
- Final row recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと、なにぬねの`.

## Next step

- Make the response-reading code safer by checking whether `choices` exists before reading `[0]`.
- Review the vowel, K, S, T, and N rows before learning more words with known kana.
