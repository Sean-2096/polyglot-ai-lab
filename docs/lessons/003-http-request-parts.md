# HTTP Request Parts

## AI

- Question: What are the three parts of `requests.post(URL, headers=HEADERS, json=BODY)`?
- My answer:
  - URL: the API path.
  - HEADERS: authentication and content type.
  - BODY: the data sent to the server.
- What I learned:
  - The URL tells the request where to go.
  - Headers contain authentication and data-format information.
  - The `json` argument contains the request body.
  - Changing `content` changes the question sent to the model.
  - A wrong endpoint may return `404 Not Found`.
  - An invalid domain may cause a connection error.
  - A wrong API key may return `401 Unauthorized`.

## Rebuild

```python
requests.post(URL, headers=HEADERS, json=BODY)
```

Modified message:

```json
{"role": "user", "content": "Explain Python"}
```

## English

Original:

> The model will return what is python.

Natural expression:

> The model will explain what Python is.

Original:

> BODY: the data send to the server.

Natural expression:

> BODY: the data sent to the server.

New words:

- URL
- header
- body
- unauthorized
- connection error

## Japanese today

- あ — `a`
- い — `i`

Recall result: recalled both `あ` and `い` correctly.

## Next step

- Build a small Python script that sends a real model request and inspect the response status and JSON.
