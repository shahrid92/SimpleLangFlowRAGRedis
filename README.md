
# Simple Langflow RAG Setup with Redis
> For my learning purpose only

This RAG is designed for quick deployment and privacy, making it ideal for summarizing my private documents, such as agreements. So far with my current setup 12 Threads 16GB RAM RTX4060 mobile 8GB VRAM performance not too bad,I dont feel any slowness.

## Installing / Getting started

### Install Docker Desktop

```
https://www.docker.com/products/docker-desktop/
```

### Install Ollama

Embeddings models I'm using models with 768 dimension dense vector space such as `nomic-embed-text` or `all-mpnet-base-v2`. Also can use higher dimensions which depends on your local specification. Text generation will `llama3.2 3B`.

Once pull the modules then serve ollama api for langflow ollama component.
```shell
Ollama serve
```
### Redis configuration 
  Before running docker services. make sure `redis.conf` file include the redisearch modules. (MODULES section). Once you ruuning docker compose file on docker logs you will see below logs:
  ```
  Module 'search' loaded from /opt/redis-stack/lib/redisearch.so
  ```

### Initial Configuration

Simply run the services (docker-compose.yaml) via docker desktop or cli.
```shell
docker-compose up -d
```
2 servcies will created. langflow and redis server

## Features

* Chat History
* Any text documents files e.g. txt,pdf. (so far only plain text)
* Upload & Embed bulk documents using PyPDFLoader (Next lesson)

## Lesson Learnt
- [x] Basic understanding how RAG workflow.
- [x] Semantic query using redis vector.
- [x] Using inference Ollama. (Recomended for quick setup)
- [x] Langflow basic components. (Good for beginner who trying to understand RAG)
- [x] LLM Chat memory using system prompts.

## My References Links

- RAG with RedisVL: https://redis.io/blog/from-zero-to-rag-building-your-first-rag-pipeline-with-redisvl/
- Langchain Community vector store redis documents:
https://api.python.langchain.com/en/latest/vectorstores/langchain_community.vectorstores.redis.base.Redis.html
- READMe Templates: https://github.com/jehna/readme-best-practices
- Im sharing also the langflow RAG setup for anyone to refer. (Simple RAG prompting.json)