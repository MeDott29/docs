<div align="center">
 <img alt="bytez" height="250px" src="https://github.com/Bytez-com/docs/assets/9612780/610ae3a1-65b5-4f8a-8ed5-0bae9134ab5f">

[![](https://dcbadge.limes.pink/api/server/https://discord.gg/Zrd5UbMEBA)](https://discord.com/invite/Z723PfCFWf) 
[![](https://img.shields.io/badge/Bytez-000000?style=for-the-badge&logo=x&=logoColor=white)](https://x.com/Bytez)
[![Discord](https://img.shields.io/discord/844731722700816395)](https://discord.com/invite/Z723PfCFWf) 
[![NPM Version](https://img.shields.io/npm/v/bytez.js)](https://www.npmjs.com/package/bytez.js)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1oZ4_yQoryL9a3CCLiY29JpEI1L5uwqO-?authuser=1#scrollTo=3LRTz2egUNh7&uniqifier=3)

</div>

# ✨ Bytez

Evaluate and run large AI models affordably with Bytez – achieve GPU performance at CPU pricing.

# 🚀 Quickstart
Two steps to run inference in minutes:
1. Get your API Key
2. Choose your path: run inference locally via Docker or use our API (javascript, python, REST API)

## 🔑 API Key
Join the [Bytez Discord](https://discord.gg/Zrd5UbMEBA) or go to [Bytez.com](http://bytez.com), sign in, and visit user settings to get your key. 

## Docker 
All Bytez models are available on [Docker Hub](https://hub.docker.com/u/bytez) or our [About](https://bytez.com/about) page 🤙

## Libraries
- [Python](./python/readme.md)
- [Javascript](./javascript/readme.md)
- [Julia](./julia/Bytez/readme.md)

## <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png" height=15 /> Python
Load and run a model after installing our python library (`pip install Bytez`).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1oZ4_yQoryL9a3CCLiY29JpEI1L5uwqO-?authuser=1#scrollTo=3LRTz2egUNh7&uniqifier=3)

### Load and run a model
```python
import os
from bytez import Bytez
client = Bytez(api_key=os.environ.get("YOUR_API_KEY")

# Grab a model
model = client.model('openai-community/gpt2')

# Start a model
model.load()

# Run a model
output = model.run("Once upon a time there was a", model_params={"max_new_tokens":1,"min_new_tokens":1})
print(output)
```

See the [API Documentation](./python/readme.md) for all examples.

## <img src="https://cdn-icons-png.flaticon.com/512/5968/5968322.png" height=15 /> Javascript
Load and run a model after installing our Typescript library (`npm i bytez.js`).
### Load and run a model
```javascript
import Bytez from "bytez.js";
client = new Bytez("YOUR_API_KEY");

// Grab a model
model = client.model("openai-community/gpt2");

// Start a model
await model.load();
console.log(results);

// Run a model
output = await model.run("Once upon a time there was a");
console.log(output);
```

See the [API Documentation](./javascript/readme.md) for all examples.

## <img src="https://upload.wikimedia.org/wikipedia/commons/1/1f/Julia_Programming_Language_Logo.svg" height=15 />Julia
Load and run a model after installing our Bytez library (`add Bytez`).

<img src="https://cdn.jsdelivr.net/gh/fonsp/Pluto.jl@0.15.1/frontend/img/logo.svg" height=15 /> <b>[Interactive Notebook!](#)</b> <i>(Coming Soon)</i>

### Load and run a model
```julia
using Bytez
client = Bytez.init("YOUR_API_KEY");

# Grab a model
# args => modelId, concurrency = 1, timeout = 300 secs
model = client.model("openai-community/gpt2")

# Start a model
model.load()

# Run a model
output = model.run("Roses are")
println(output)

```

## <img src="https://www.svgrepo.com/show/305922/curl.svg" height=15 /> REST API

Bytez has a REST API for loading, running, and requesting new models.

### Load a model
```bash
curl --location 'https://api.bytez.com/model/load' \
--header 'Authorization: Key API_KEY' \
--header 'Content-Type: application/json' \
--data '{
    "model": "openai-community/gpt2",
    "concurrency": 1
}'
```

### Run a model
```bash
curl --location 'https://api.bytez.com/model/run' \
--header 'Authorization: Key API_KEY' \
--header 'Content-Type: application/json' \
--data '{
    "model": "openai-community/gpt2",
    "prompt": "Once upon a time there was a",
    "params": {
        "min_length": 30,
        "max_length": 256
    },
    "stream": true
}'
```

### Request a model 
```bash
curl --location 'https://api.bytez.com/model/job' \
--header 'Authorization: Key API_KEY' \
--header 'Content-Type: application/json' \
--data '{
    "model": "openai-community/gpt2"
}'
```

See the [API Documentation](./api.md) for all endpoints.

# Model Library

We currently support 10,000+ open source AI models across 35+ ML tasks. See our [model library](https://bytez.com/about) for the full list.

Here are some models that can be run - with their required RAM.

| Model Name                                               | Required RAM (GB)       
|----------------------------------------------------------|-------------------------|
| EleutherAI/gpt-neo-2.7B                                  | 2.23                                       
| bigscience/bloom-560m                                    | 3.78                    
| succinctly/text2image-prompt-generator                   | 1.04                    
| ai-forever/mGPT                                          | 9.59                    
| microsoft/phi-1                                          | 9.16                    
| facebook/opt-1.3b                                        | 8.06                    
| openai-community/gpt2                                    | 0.50                                     
| bigscience/bloom-1b7                                     | 7.82                    
| databricks/dolly-v2-3b                                   | 11.09                   
| tiiuae/falcon-40b-instruct                               | 182.21                  
| tiiuae/falcon-7b-instruct                                | 27.28                   
| codellama/CodeLlama-7b-Instruct-hf                       | 26.64                   
| deepseek-ai/deepseek-coder-6.7b-instruct                 | 26.50                   
| upstage/SOLAR-10.7B-Instruct-v1.0                        | 57.63                   
| elyza/ELYZA-japanese-Llama-2-7b-instruct                 | 38.24                   
| NousResearch/Meta-Llama-3-8B-Instruct                    | 30.93                   
| VAGOsolutions/SauerkrautLM-Mixtral-8x7B-Instruct         | 211.17                  
| codellama/CodeLlama-34b-Instruct-hf                      | 186.52                  
| deepseek-ai/deepseek-coder-7b-instruct-v1.5              | 27.05                   
| Equall/Saul-Instruct-v1                                  | 2.44                    
| Equall/Saul-7B-Instruct-v1                               | 10.20                   
| microsoft/Phi-3-mini-128k-instruct                       | 14.66                   
| microsoft/Phi-3-mini-4k-instruct                         | 14.65                   
| victor/CodeLlama-34b-Instruct-hf                         | 127.37                  
| gradientai/Llama-3-8B-Instruct-262k                      | 30.80                   
| gradientai/Llama-3-8B-Instruct-Gradient-1048k            | 30.59                   
| yanolja/EEVE-Korean-Instruct-10.8B-v1.0                  | 54.30                   
| codellama/CodeLlama-13b-Instruct-hf                      | 50.38                   
| deepseek-ai/deepseek-coder-1.3b-instruct                 | 6.16                    
| deepseek-ai/deepseek-coder-33b-instruct                  | 158.74                  
| filipealmeida/Mistral-7B-Instruct-v0.1-sharded           | 27.42                   
| unsloth/llama-3-8b-Instruct                              | 30.77                   
| speakleash/Bielik-7B-Instruct-v0.1                       | 27.52                   
| Deci/DeciLM-7B-instruct                                  | 26.90                   
| tokyotech-llm/Swallow-70b-instruct-hf                    | 242.23                  
| tokyotech-llm/Swallow-7b-NVE-instruct-hf                 | 26.89                                     
| codellama/CodeLlama-70b-Instruct-hf                      | 372.52                  
| togethercomputer/Llama-2-7B-32K-Instruct                 | 25.65                   
| beomi/Llama-3-Open-Ko-8B-Instruct-preview                | 30.81                   
| abhishekchohan/SOLAR-10.7B-Instruct-Forest-DPO-v1        | 15.38                   
| deepseek-ai/deepseek-math-7b-instruct                    | 28.08                   
| occiglot/occiglot-7b-eu5-instruct                        | 28.94                   
| MediaTek-Research/Breeze-7B-Instruct-v1_0                | 29.84                   


# Resources
- [About Us](./about.md)
- [Cold Boot Times and Billing](./cold-boot-billing.md)
