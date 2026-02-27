# Local Test

# docker

```bash
docker build -t nanobot -f ./Dockerfile_nouv .
```


# first config

```bash
# Initialize config (first time only)
docker run -v ./tests/.nanobot:/root/.nanobot --rm nanobot onboard

# Edit config on host to add API keys
vim ./tests/.nanobot/config.json
```


# run

```bash
# Or run a single command
docker run -v ./tests/.nanobot:/root/.nanobot --rm nanobot agent -m "Hello!"
docker run -v ./tests/.nanobot:/root/.nanobot --rm nanobot status

# Interactive chat with logs
docker run -it -v ./tests/.nanobot:/root/.nanobot --rm nanobot agent --logs

# for test
docker run -it -v ./tests/.nanobot:/root/.nanobot --rm --entrypoint bash nanobot
```
