- created a Go wrapper for OpenAI's chat completion API

https://github.com/kfatehi/go-openai

- modified Dendrite to provide a /gpt route on the Matrix API

https://github.com/kfatehi/dendrite/tree/openai

- modified matrix-js-sdk client to provide a gpt() function

https://github.com/kfatehi/matrix-js-sdk/tree/openai

- modified matrix-react-sdk to implement the UI

https://github.com/kfatehi/matrix-react-sdk/tree/openai




https://user-images.githubusercontent.com/175305/222951380-8a5c46fa-c7d9-4230-a666-76dae98b3ccf.mp4

## Future consideration

The tightly-coupled approach taken here in which the entire stack has been modified is not tenable. Although the use case being demonstrated here certainly has its merits, yet another first-class user-interface to maintain across the entire client (and server) ecosystems makes little sense especially when the use case can be designed through the use of a bridge bot.

A matrix AS/bridge can detect slash commands in different rooms, which is all that is needed for this idea to be made manifest without UI and server changes. It would be wiser means by which to implement this idea as then any client and any server will be able to access it.

Designing the interaction so that it is at least equal to if not better than what we see in the video above is the challenge now, although I think something like this makes sense:

- you are chatting with user Alice
- you wish to invoke the AI so you type /ai
- the AI bot user messages you with the payload it is about to send to the API
- you confirm the payload (or change settings and then confirm)
- the AI replies with the API response
- you copy-paste from the API response and send it to Alice

I think this user experience works totally fine, if not even better than the one we see in the video above.
