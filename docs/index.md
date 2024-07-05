# Otoroshi LLM Extension in action - Cloud APIM Serverless

this API demonstrate how to use the [Otoroshi LLM Extension](https://github.com/cloud-apim/otoroshi-llm-extension) in a Cloud APIM Serverless project. The Otoroshi LLM Extension provide tools and plugins to use LLM easily in your projects no matter what provider you're using (on premise, cloud, openai, anthropic, mistral, etc). 

the API hosting this demo is located at

```sh
https://${environment.HOST}
```

## Source code

the source code for this project is available on [Cloud APIM's Github](https://github.com/cloud-apim/otoroshi-llm-extension-serverless-example). You can fork it and modify it for your own needs.

## Demo steps

the project is organized around several steps, one for each possible use case (non exhaustive). The first 2 steps shows how to use otoroshi to consume an LLM API et expose it to your applications in a consistant way no matter what provider is used. The other steps shows how a LLM API can help you configuring your API gateway using natural language.

- [Prompt context](/docs/demo-1-prompt-context.html)
- [Prompt templating](/docs/demo-2-prompt-templating.html)
- [Data mockups](/docs/demo-3-mock.html)
- [UI mockups](/docs/demo-4-ui-mock.html)               
- [Access validation](/docs/demo-5-access-validation.html)                            
- [Data enrichment](/docs/demo-6-data-enrichment.html)                             
- [Data cleanup](/docs/demo-7-data-cleanup.html)                           
- [Websocket validation](/docs/demo-8-websocket-messages-validation.html)                       
- [Data anonymisation](/docs/demo-9-gdpr.html)

## API Spec

the OpenAPI spec of this API is available [here](/docs/openapi.json) and the viewer for this spec is available [here](/docs/api-ref)

## Conference

this project is based on a conference given by [Mathieu](https://github.com/mathieuancelin) at [Breizhcamp 2024](https://www.breizhcamp.org/)

## Otoroshi managed instances

if you want to achieve the same thing using your own otoroshi instance (on Cloud APIM or on premise), you can use the [following configuration file](/docs/otoroshi-managed.yaml) in the `otoroshi resource loader`. Do not forget to change the domain names in the routes to match yours and to add an OpenAI token in the local vault named `openai-token`