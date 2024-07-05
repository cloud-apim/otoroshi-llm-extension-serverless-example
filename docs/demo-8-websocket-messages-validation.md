# WebSockets message validation

In this demo, we use a LLM to validate message sent over websocket in a chat room or something similar to avoid crude language or hate speech.

## Call the API

```bash
websocat wss://${environment.HOST}/websockets
```

## Result

```sh
Request served by 1781505b56ee58


hello # request
hello # response


how are you ? # request
how are you ? # response


you suck # request
# no response because the plugin filtered it


hello # request
hello # response
```