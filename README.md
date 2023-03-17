# Chatbot

A Python chatbot implemented with official OpenAI API using model `gpt-3.5-turbo`.

## Setup
1. Clone code from github and cd into directory

2. Setup and activate venv

```bash
# This app was built with Python v3.11.1.
python3 -m venv .
source bin/activate

# To deactivate the virtual env
deactivate
```

3. Install required packages

```bash
python3 -m pip install -r requirements.txt
```

4. Get your OpenAI API Key <a href="https://platform.openai.com/account/api-keys" target="_blank">here</a>

Once you have an API key create a .env file and set OPEN_AI_API_KEY environment variable.
```
touch .env
echo 'OPEN_AI_API_KEY = "your key here"' >> .env
```

5. Run the program with
```
python3 chatbot.py
```

## GPT-3.5 Turbo Prompts

The API takes a collection of messages. Messages have 3 possible roles: `system`, `user`, and `assistant`.

`system` role: used to write the chatbots instructions

`user` role: this is the input from the user.

`assistant` role: this is how the chatbot responded to the previous `user` message.

To keep the context of the conversation going we add all interactions to the `messages` list. The max tokens we can send is about 4k so as the conversation grows it becomes more costly and eventually we would have to prune messages.

Documentation on arguments which `ChatCompletion` takes can be found [here](https://platform.openai.com/docs/api-reference/chat/create).
