## Running ollama third-party service

# Server Configuration

```bash
    export LLM_ENDPOINT_PORT=8008
    export LLM_MODEL_ID=llama3.2:1b
    export host_ip=$(hostname -i | awk '{print $1}')
    export no_proxy=localhost
    docker-compose up
```
### pull a model
curl http://localhost:8008/api/pull -d '{
    "model": "llama3.2:1b"
}'

### request ollama model

curl http://localhost:8008/api/generate -d '{
  "model": "llama3.2:1b",
  "prompt": "Why is the sky blue?"
}'

