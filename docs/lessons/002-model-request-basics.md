# Model Request Basics

## AI

- Question: What are the three main parts of a model request?
- My answer: API key, model, and messages.
- What I learned:
  - The API key is used for authentication.
  - `model` selects which LLM processes the request.
  - `messages` contains the conversation sent to the model.
  - Common message roles are `system`, `user`, and `assistant`.
  - `system` gives instructions, `user` sends a message, and `assistant` contains the model's reply.
  - A missing or incorrect API key causes the API to return an authentication error.

## JSON practice

Valid request rebuilt from memory:

```json
{
  "model": "deepseek-chat",
  "messages": [
    {
      "role": "user",
      "content": "What is an LLM?"
    }
  ]
}
```

Key corrections:

- Use a comma to separate JSON fields.
- Use a colon between a key and its value.
- Put text values inside quotation marks.

## English

Original:

> The system role controls the model's behave.

Natural expression:

> The system role controls the model's behavior.

Original:

> The model will reply error message.

Natural expression:

> The API will return an authentication error.

New words:

- authentication
- behavior
- request
- response

## Japanese today

- あ — `a`

Recall result: recalled `あ` correctly.

## Next step

- Observe a real Python HTTP request and identify its URL, headers, and JSON body.
