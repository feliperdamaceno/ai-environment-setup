[← Return](../README.md)

## LLM CLI & Ollama Plugin Setup

This guide covers installing the `llm` CLI tool, configuring it for **Ollama**
models, and using the `llm-ollama` plugin.

---

### Install `llm` CLI

If you don’t have it installed yet, run:

```
pip install llm
```

After installation, verify it with:

```
llm --version
```

---

### Install the `llm-ollama` Plugin

This plugin provides access to models running on an **Ollama** server. Install
it in the same environment as `llm`:

```
llm install llm-ollama
```

---

### Configure `llm` for Ollama Models

Make sure the **Ollama** server is running and the models are installed locally:

```
ollama list
```

This should display the models available. The plugin will automatically query
the **Ollama** server for available models.

You can also list them via `llm`:

```
llm ollama models
```

All models will now be automatically registered with `llm` and available for
prompting, chatting, and embedding.

---

### Using Ollama Models with `llm`

#### Interactive Chat via Alias

You can create shell aliases for convenience (add to `~/.bashrc` or `~/.zshrc`)
and reload the shell:

```
alias deepseek='llm -m deepseek-r1:8b'

# and

alias qwen='llm -m qwen2.5-coder:7b-instruct-q4_0'
```

To start chatting or run a command use:

```
deepseek
qwen
```

#### Running Prompts

With the setup ready, you can run a prompt like this:

```
find . -type f -name "*.ts" | deepseek "Which of these files contain 'main' function?"
```

### Notes

- Make sure Ollama is installed and the required models are pulled before using
  `llm`.
- The plugin keeps the models in sync with Ollama’s local server, so any model
  pulled via Ollama is automatically available in `llm`.
- Deepseek Coder is better for chat based tasks, while Qwen Coder is more
  focused on small individual tasks, so choose wisely.
