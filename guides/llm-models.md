[← Return](../README.md)

## Models Setup

This guide shows how to install Ollama on Linux using their automated shell
script and install specific models.

### Install Ollama

Run the following command in your terminal:

```
curl -s https://ollama.com/install.sh | bash
```

> This script will automatically detect your system architecture and install the
> latest version of Ollama.

After installation, verify it with:

```
ollama version
```

---

### Install Models

To install models use the `ollama pull` command.

Required models:

```
ollama pull deepseek-r1:8b

# and

ollama pull qwen2.5-coder:7b-instruct-q4_0
```

Check the installed models with:

```
ollama list
```

---

### Running the Models

After installation, you can run the models locally:

```
ollama run deepseek-r1:8b

# and

ollama run qwen2.5-coder:7b-instruct-q4_0
```

---

### Notes

- Make sure you have `curl` and `bash` installed.
- Ollama manages and serves models automatically, so you do not need to handle
  paths manually.
- If using via WSL make sure to have `systemd` enabled.
- For more advanced usage and CLI options, refer to the
  [Ollama Documentation](https://docs.ollama.com).
