# TLDR

How to set up a Llama Stack Client project

## Setup

```sh
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

## inference_test.py

```sh
python3 inference_test.py
```

## agent_test.py

- https://github.com/meta-llama/llama-stack-apps/blob/main/examples/agents/hello.py
- https://brave.com/search/api/
- https://api.search.brave.com/app/keys

```sh
touch .env
echo  "BRAVE_SEARCH_API_KEY=%API_KEY_HERE%" > .env # get an API key from the Brave Search API console
python3 agent_test.py
```