# Local Test

# docker

```bash
docker build -t nanobot -f ./Dockerfile_nouv .
```


# first config

```bash
# Initialize config (first time only)
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot onboard

# Edit config on host to add API keys
vim ~/.nanobot/config.json
```


# run

```bash
# Run gateway (connects to enabled channels, e.g. Telegram/Discord/Mochat)
docker run -v ~/.nanobot:/root/.nanobot -p 18790:18790 nanobot gateway

# Or run a single command
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot agent -m "Hello!"
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot status

# Interactive chat with logs
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot agent --logs

# for test
docker run -it -v ~/.nanobot:/root/.nanobot --rm --entrypoint bash nanobot
```
