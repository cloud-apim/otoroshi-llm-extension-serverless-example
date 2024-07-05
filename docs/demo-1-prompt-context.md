# Add context to your API

This demo show how to add context, configuration, etc, to your prompts. Here we use gpt-3.5 turbo for this demo. This model is too old to have informations about Cloud APIM so we added a [context](https://github.com/cloud-apim/otoroshi-llm-extension-serverless-example/blob/main/entities/ai.json#L52) for this prompt and Chat GPT is now able to explain what Cloud APIM is.

## Call the API

using javascript 

```js
const response = await fetch("https://${environment.HOST}/context", {
  method: 'post',
  headers: {
    "content-type": "application/json",
  },
  body: JSON.stringify({
    "messages": [
      {
        "role": "user",
        "content": "Can you tell me more about the Cloud APIM company ?"
      }
    ]
  })
});

const data = await response.json();
console.log(data);
```

or curl

```sh
curl -X POST -H 'Content-Type: application/json' "https://${environment.HOST}/context" -d '{
  "messages": [
    {
      "role": "user",
      "content": "Can you tell me more about the Cloud APIM company ?"
    }
  ]
}'
```

## Result

```js
{
  "generations": [
    {
      "message": {
        "role": "assistant",
        "content": "Cloud APIM is a French company that specializes in providing API Management as a Service solutions. They offer managed Otoroshi instances, which is an open-source API gateway that provides features such as traffic management, security, monitoring, and analytics for APIs.\n\nIn addition to API Management services, Cloud APIM also offers Serverless projects. Serverless computing allows developers to build and run applications without managing infrastructure. This can help reduce costs and improve scalability.\n\nOverall, Cloud APIM aims to help businesses efficiently manage their APIs and streamline their development processes through their various services and solutions."
      }
    }
  ],
  "metadata": {
    "rate_limit": {
      "requests_limit": 10000,
      "requests_remaining": 9999,
      "tokens_limit": 60000,
      "tokens_remaining": 59936
    },
    "usage": {
      "prompt_tokens": 49,
      "generation_tokens": 114
    }
  }
}
```

