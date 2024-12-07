# TLDR hack for the YouTube video

```sh
git clone git@github.com:AgentOps-AI/agentops.git
cd agentops
gco tduval/feature/llamaStackClientSupport
pip3 install -e ../agentops # IMPORTANT: agentops editable package must be a sibling project for scoping reasons
python3 inference_test.py
```



