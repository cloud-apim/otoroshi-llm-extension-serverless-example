# Data enrichment

Here with use the LLM to add missing data in an http request before the request hits your API. In this case, it add the country in the request payload based on the city mentionned in the payload.

## Call the API

using javascript 

```js
const response = await fetch("https://${environment.HOST}/enrich", {
  method: 'post',
  headers: {
    "content-type": "application/json",
  },
  body: JSON.stringify({
    "email": "mathieu.ancelin@cloud-apim.com",
    "city": "Poitiers"
  })
});
const data = await response.json();
console.log(data);
```

or curl

```sh
curl -X POST -H 'Content-Type: application/json' "https://${environment.HOST}/enrich" -d '{
  "email": "mathieu.ancelin@cloud-apim.com",
  "city": "Poitiers"
}'
```

## Result

```js
{
  "email": "mathieu.ancelin@cloud-apim.com",
  "city": "Poitiers",
  "country": "France"
}
```