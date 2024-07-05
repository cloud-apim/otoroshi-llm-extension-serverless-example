# Prompt Templating

This demo show how to use a template to create a prompt based on common specifications. Here we make a translator service with a generic prompt that uses expression language to extract informations from the current request (in that case from the request body).


## Call the API

using javascript 

```js
const response = await fetch("https://${environment.HOST}/template", {
  method: 'post',
  headers: {
    "content-type": "application/json",
  },
  body: JSON.stringify({
    "lang": "fr",
    "text": "Hello World !"
  })
});

const data = await response.json();
console.log(data);
```

or curl

```sh
curl -X POST -H 'Content-Type: application/json' "https://${environment.HOST}/template" -d '{
  "lang": "fr",
  "text": "Hello World !"
}'
```

## Result

```js
{
  "generations": [
    {
      "message": {
        "role": "assistant",
        "content": "Bonjour le monde !"
      }
    }
  ],
  "metadata": {
    "rate_limit": {
      "requests_limit": 10000,
      "requests_remaining": 9999,
      "tokens_limit": 60000,
      "tokens_remaining": 59963
    },
    "usage": {
      "prompt_tokens": 23,
      "generation_tokens": 4
    }
  }
}
```