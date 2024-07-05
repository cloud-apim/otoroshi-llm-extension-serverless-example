# Data Anonymisation

Here we use a LLM to anonymize sensitive data from the response. In that case, it replaces personnal data with coherent informations.

## Call the API

using javascript 

```js
const response = await fetch("https://${environment.HOST}/gdpr", {
  method: 'post',
  headers: {
    "content-type": "application/json",
  },
  body: JSON.stringify({
    "name": "Mathieu ANCELIN",
    "age": 38,
    "role": "speaker",
    "languages": ["scala", "java", "javascript", "rust"],
    "email": "mathieu.ancelin@cloud-apim.com"
  })
});

const data = await response.json();
console.log(data);
```

or curl

```sh
curl -X POST -H 'Content-Type: application/json' "https://${environment.HOST}/gdpr" -d '{
  "name": "Mathieu ANCELIN",
  "age": 38,
  "role": "speaker",
  "languages": ["scala", "java", "javascript", "rust"],
  "email": "mathieu.ancelin@cloud-apim.com"
}'
```

## Result

```js
{
  "name": "John Doe",
  "age": 30,
  "role": "developer",
  "languages": ["python", "c++", "swift", "ruby"],
  "email": "john.doe@example.com"
}
```