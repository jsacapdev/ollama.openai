# Ollama Open AI [Compatibility](https://ollama.com/blog/openai-compatibility)

## Application Development

Prerequisites were to create a environment using [Anaconda](https://www.anaconda.com/):

`conda create --name ollama.openai python=3.12`

And then it can be enabled using the following command:

`conda activate ollama.openai`

Load in the dependencies in the `src` folder using the following commands:

```bash
pip install pip-tools

pip-compile ./requirements.in

pip install -r ./requirements.txt
```

## Setting up the engine (in Docker)

To start in a docker container using the following command:

`docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama`

To pull down a model in a container:

`docker exec -it ollama ollama pull mistral`

`docker exec -it ollama ollama pull llama2`

On a container run-up the model in the container:

`docker exec -it ollama ollama run llama2`

And to start the container (if required after restart):

`docker start ollama`

To view the logs in the container:

`docker logs -f ollama`
