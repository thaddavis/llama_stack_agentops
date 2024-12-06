# TLDR

How to set up a Llama Stack Server powered by an model running in Ollama

## Links containing the hints of how to run a Llama Stack Server

- https://llama-stack.readthedocs.io/en/latest/distributions/index.html
- https://llama-stack.readthedocs.io/en/latest/getting_started/index.html
- https://github.com/meta-llama/llama-stack/blob/main/llama_stack/templates/ollama/run.yaml
- https://llama-stack.readthedocs.io/en/latest/references/llama_cli_reference/download_models.html

## STEPS

### 1

```sh
touch run.yaml
```

### 2

Copy the following yaml files content into the run.yaml file

https://github.com/meta-llama/llama-stack/blob/main/llama_stack/templates/ollama/run.yaml (ORIGINAL)
https://github.com/AgentOps-AI/agentops/pull/530/files#diff-e8267b2aa8eb164ea65f848e73127026d0c5391bdb04e3ca39415fcc9899b197 (tweaked but works)

### 3

Make sure model is running...

- `ollama run llama3.2:1b-instruct-fp16 --keepalive 60m`
- `CTRL + D`
- `ollama ps`

### 4

```sh
docker run \
  -it \
  -p 5001:5001 \
  -v ~/.llama:/root/.llama \
  -v ./run.yaml:/root/run.yaml \
  llamastack/distribution-ollama \
  --yaml-config /root/run.yaml \
  --port 5001 \
  --env INFERENCE_MODEL=meta-llama/Llama-3.2-1B-Instruct \
  --env OLLAMA_URL=http://host.docker.internal:11434
```