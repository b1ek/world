+++
template = 'custom/blog-post.html'

title = 'duckduckgo ai chat thing'
description = 'its kinda cool'
date = '2024-04-11'
slug = 'duckduckgo-ai-chat'
year = 2024
month = 4
day = 11
lang = 'en'

[extra]
author = 'b1ek <me@blek.codes>'
+++

so, a few days ago i've noticed that duckduckgo has this weird new "ai chat" option:  
![screenshot of duckduckgo page with a red arrow pointing to the "Chat" button](/blog-image/chat-btn.png)

it allows you to select two models: claude 1.2 and chatgpt 3.5. the last one is widely known, however you can find some info on claude [here](https://www.anthropic.com/news/releasing-claude-instant-1-2)

as i've always wondered just how real their claims are that your identity is never attached to the models, i've decided to research into the API.

## chat APIs

| Disclaimer: The following section is of educational purposes only. Please do not scrape DuckDuckGo's APIs, as it would only hurt the company which honestly cares about your privacy. |
| --- |

obviously the first thing i wanted to do see if there is a public chat API. i wasn't suprised when i couldn't find info on any of the public duckduckgo APIs(probably because there isn't any), other than [this stackoverflow answer](https://stackoverflow.com/questions/29346239/duckduckgo-api-how-to-get-more-results)

however i've investigated a bit and turns out that client API is not that complicated as i thought.

now, first of all you need yo obtain the API token via `GET https://duckduckgo.com/duckchat/v1/status` with a header `x-vqd-accept: 1`. the api token will be in the `x-vqd-4` header. it seems a bit tricky to get the right token without it throwing a `ERR_INVALID_VQD` error later, so its best to copy the request as cURL from your browser.

it is quite weird actually that it seems to be accepting only genuine browser-generated headers. however they contain little to no identifying data.

after you got the api key, send a `POST https://duckduckgo.com/duckchat/v1/chat` with a header `x-vqd-4: the-vqd-header-from-previous-request`.

the payload seems to be of this TS type and encoded via JSON:

```ts
type ChatPayload {
    messages: { content: string, role: 'user' }[],
    model: 'claude-instant-1.2' | 'gpt-3.5-turbo-0125'
}
```

then the API will return the response word-by-word in a good ol' streamed http response in chunks like this:
```json
\n
data: {"role":"assistant","message":".","created":1712840811713,"id":"compl_8pC9nVX8QJlN92jUtcJR8TgB","action":"success","model":"claude-instant-1.2"}
```

also the `/duckchat/v1/chat` request gives you the new VQD which you gotta use for the future requests.

i guess someone could fashion a cli program to read data from that API and print it out in the console.

## the verdict
i think its safe to say that no identity data is collected via the chat APIs, other than your IP address, which by itself is not usually enough to identify a user, especially if you're sitting on a public network.

also if someone from the team who made the API reads this, please tell me if i missed some points, and what the hell does VQD even mean.
