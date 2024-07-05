# Mock Responses

In this example, we use a LLM to generate mock data for an endpoint. This usage could be useful in case you need to start to create an app before an api is available. The LLM will be able to generate structured data based on your specifications written in natural language.

## Call the API

using javascript 

```js
const response = await fetch("https://${environment.HOST}/mock");
const data = await response.json();
console.log(data);
```

or curl

```sh
curl "https://${environment.HOST}/mock"
```

## Result

```js
[
  {
    "email": "user1@example.com",
    "name": "Alice",
    "age": 25,
    "address": "123 Main St"
  },
  {
    "email": "user2@example.com",
    "name": "Bob",
    "age": 30,
    "address": "456 Elm St"
  },
  {
    "email": "user3@example.com",
    "name": "Charlie",
    "age": 35,
    "address": "789 Oak St"
  },
  {
    "email": "user4@example.com",
    "name": "Diana",
    "age": 40,
    "address": "234 Maple St"
  },
  {
    "email": "user5@example.com",
    "name": "Eve",
    "age": 45,
    "address": "567 Pine St"
  }
]
```