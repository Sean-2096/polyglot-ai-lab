# Request Body and the T-row

## AI

- Question: What data does the request body send to the LLM API server?
- My answer:

```python
body = {
    "model": "deepseek-chat",
    "messages": [
        {"role": "user", "content": "Explain what an API is."}
    ]
}
```

- What I learned:
  - The `model` field chooses which LLM to call.
  - The `messages` field contains a list of dictionaries.
  - Each message usually has `role` and `content` fields.
  - The `content` field contains the user's text or prompt.
  - Changing `content` changes what the model should answer.
  - A wrong model name may cause a `404 Not Found`, `400 Bad Request`, or provider-specific model error.
  - Headers describe metadata, such as authentication and content type.
  - The body contains the actual data sent to the server.
  - `json=body` tells `requests` to convert the Python dictionary into JSON and send it as the request body.
  - `data=body` may send data in a different format, so the server might not understand the request.
  - `Content-Type: application/json` tells the server how to parse the request body.

## English

Original:

> The model used to switch different LLMs.

Natural expression:

> The `model` field is used to choose which LLM to call.

Original:

> It contains an list with dict like role and content field.

Natural expression:

> It contains a list of dictionaries with `role` and `content` fields.

Original:

> The model will return the explain of python.

Natural expression:

> The model will return an explanation of Python.

Original:

> json=body tells the requests to convert the python dictionary into json and send it as the request body.

Natural expression:

> `json=body` tells `requests` to convert the Python dictionary into JSON and send it as the request body.

New words:

- field
- dictionary
- prompt
- explanation
- parse
- request body

## Japanese today

Reviewed:

- `あいうえお` — vowel row
- `かきくけこ` — K-row
- `さしすせそ` — S-row
- `かお` — face
- `こえ` — voice
- `あさ` — morning

Learned:

- `たちつてと` — ta, chi, tsu, te, to
- `ち` is pronounced `chi`, not `ti`
- `つ` is pronounced `tsu`, not `tu`
- `とし` — year / age
- `した` — under / below

Recall result:

- Correctly recalled `かお`, `こえ`, and `あさ`.
- Correctly typed the full T-row: `たちつてと`.
- Correctly read `とし` and `した`.
- First wrote `たし` for `とし`, then corrected it to `とし`.
- First wrote `さちすせそ` for the S-row, then corrected it to `さしすせそ`.
- Final row recall was correct: `あいうえお、かきくけこ、さしすせそ、たちつてと`.

## Next step

- Combine `URL`, `headers`, and `body` into one complete `requests.post(...)` example.
- Review the vowel, K, S, and T rows before learning more words with known kana.
