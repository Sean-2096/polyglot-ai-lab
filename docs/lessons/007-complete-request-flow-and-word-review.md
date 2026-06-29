# Complete Request Flow and Word Review

## AI

- Question: How do we send a complete API request and read the assistant's answer?
- My answer:

```python
response = requests.post(URL, headers=headers, json=body)
data = response.json()
answer = data["choices"][0]["message"]["content"]
print(answer)
```

- What I learned:
  - `requests.post(...)` sends a request to the server and gets the server's response.
  - We pass `URL`, `headers`, and `body` into `requests.post(...)`.
  - `URL` tells the request where to go.
  - `headers` tell the server authorization and metadata.
  - `body` contains the user's data sent to the server.
  - `response.status_code == 200` usually means the request was successful.
  - `401` usually means unauthorized.
  - `404` usually means the requested URL or resource was not found.
  - `response.json()` converts the response body into Python data.
  - In Python dictionaries, use bracket access such as `data["choices"][0]["message"]["content"]`.
  - `[0]` means the first item in a list.
  - Reading `data["choices"][0]["message"]["content"]` can fail if a key is missing or if `choices` is an empty list.

## English

Original:

> Requesting the server and getting the server's response.

Natural expression:

> `requests.post(...)` sends a request to the server and gets the server's response.

Original:

> The URL, headers and body had passed into requests.post() here.

Natural expression:

> The URL, headers, and body are passed into `requests.post(...)` here.

Original:

> The python dict missing key or choices is a empty list.

Natural expression:

> The Python dictionary may be missing a key, or `choices` may be an empty list.

New words:

- status code
- successful
- resource
- response body
- index
- missing key
- empty list

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

Learned:

- `くつ` — shoes
- `とけい` — clock / watch

Recall result:

- First wrote `かきこけこ` for the K-row, then corrected it to `かきくけこ`.
- Correctly recalled all four rows after one correction: `あいうえお、かきくけこ、さしすせそ、たちつてと`.
- Recalled `した` after the hint `shi + ta`.
- First wrote `てと` for `した` and `くこ` for `くつ`, then corrected them to `した` and `くつ`.
- Final word recall was correct: `かお、こえ、あさ、した、くつ、とけい`.

## Next step

- Add simple error handling around `response.status_code` before reading JSON.
- Review the four kana rows and known words before learning the N-row.
