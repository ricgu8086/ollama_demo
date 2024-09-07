Ollama Demo
-----------

- [About](#about)
- [Requirements](#requirements)
- [Installing Ollama](#installing-ollama)
- [Launch Python examples](#launch-python-examples)
  - [Prepare Python environment](#prepare-python-environment)
  - [Prepare Ollama](#prepare-ollama)
  - [Notebooks](#notebooks)


# About

This repository shows how to use open source LLMs in local, leaning on Ollama.
Ollama is an inference server that makes it very easy to use many different LLMs.
We can use it both as a CLI tool or as a library in a python script.

Here we will use the Microsoft's Phi 3 model, a very powerful Small Language Model (SML) that takes only 2.2 Gb of disk and can run in laptops with no GPU.

# Requirements

You need to have docker installed in your system, otherwise please follow [these instructions](https://docs.docker.com/engine/install/).

While Anaconda is not a hard requirement, this guide will use it for creating a virtual environment to install Python dependencies. However, feel free to replace it with virtualenv, venv, etc if you prefer.

# Installing Ollama

With just 3 lines of code you can download ollama and start talking to the model using the CLI.

```bash
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama


docker exec -it ollama /bin/bash

ollama run phi3
```

For testing purposes you can use this:
> Dime en menos de 20 palabras tu actor favorito

Note: although Phi 3 is not multi-lingual and is mainly based in english, it may complete some tasks in other languages with decent results.


# Launch Python examples

## Prepare Python environment

You can install the environment like this:

```bash
conda create -n "ollama_demo" python=3.11
conda activate "ollama_demo"
pip install ipykernel
pip install ollama
```

## Prepare Ollama

You need to have Ollama running. There is a specific *serve* command available to expose an HTTP server with a REST API. However this is automatically launched every time you run Ollama as a CLI Tool, so to launch it you just need to execute the 2 commands listed above (docker run... and docker exec...) and that's all.

## Notebooks

Now is the time to check that everything is in place. For this you just need to open the **test.ipynb** notebook and execute it. If the model responds, everything is OK and you can continue with more fun experiments such as the **llm_classifier.ipynb** notebook.
