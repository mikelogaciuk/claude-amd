# claude-amd

![Header](./public/img/logo.jpeg)

## Description

This is some battleground for local AI Agents using Gemma4:12B on GPU with 16G of VRAM.

## Setup

You need Ollama first to run this project.

You should (or not) have `Opencode`, `Pi` and `Omp (oh-my-pi)` installed on your system to get some fun.

```sh
git clone https://github.com/claude-amd/claude-amd.git
cd claude-amd
ollama create claude-mini -f ./Modelfile
cp -r ./.dotfiles/. ~/
```

Then copy via shell or manually contents for:

- OpenCode
- Pi
- Oh-My-Pi

## Run

```sh
ollama run claude-mini
```

Or via `agents`:

```shell
pi
omp
opencode
```

## Fine tuning

The model can be fine-tuned using its context window in `Modelfile`.

For example, the context of 12288 was using only 1.5G of VRAM:

```shell
$ ollama ps
NAME                  ID              SIZE      PROCESSOR    CONTEXT    RUNNER      UNTIL              
claude-mini:latest    f4ed661a81f0    1.5 GB    100% GPU     12288      llamacpp    3 minutes from now    
```

## Clean up

In order to remove the setup:

```shell
ollama rm claude-mini
```

```shell
rm ~/.config/opencode/opencode.jsonc 
rm ~/.omp/agent/config.yml          
rm ~/.omp/agent/models.yml 
rm ~/.pi/agent/models.json 
rm ~/.pi/agent/settings.json
```

## License

[MIT](./LICENSE)
