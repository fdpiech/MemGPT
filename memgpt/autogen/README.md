# MemGPT + Autogen examples
[examples/agent_groupchat.py](examples/agent_groupchat.py) contains an example of a groupchat where one of the agents is powered by MemGPT.

**Local LLM support**
In order to run MemGPT+Autogen on a local LLM, go to lines 32-55 in [examples/agent_groupchat.py](examples/agent_groupchat.py) and fill in the config files with your local LLM's deployment details. For example, if you are using webui, it will look something like this:

```
config_list = [
    {
        "model": "dolphin-2.1-mistral-7b",  # this indicates the MODEL, not the WRAPPER (no concept of wrappers for AutoGen)
        "api_base": "http://127.0.0.1:5001/v1"
        "api_key": "NULL", # this is a placeholder
        "api_type": "open_ai",
    },
]
config_list_memgpt = [
    {
        "model": "airoboros-l2-70b-2.1",  # this specifies the WRAPPER MemGPT will use, not the MODEL
    },
]
```

Also be sure to export `OPENAI_API_BASE` and `BACKEND_TYPE` as described in [Local LLM support](../local_llm).
