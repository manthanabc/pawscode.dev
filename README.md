# Paws 🐾

**AI Terminal Assistant for Developers**

Paws is a powerful, terminal-native AI assistant designed to help developers code faster, debug smarter, and refactor effortlessly—all without leaving the command line.

![Paws Terminal Demo](https://via.placeholder.com/800x400?text=Paws+Demo)

## 🚀 Features

- **Terminal-Native Workflow**: Seamlessly integrates into your existing dev environment.
- **500+ AI Models**: Support for OpenAI, Anthropic, Google Gemini, Mistral, and many more.
- **Context-Aware**: Understands your project structure, dependencies, and code patterns.
- **Privacy-First**: Your code stays local; only necessary context is sent to the AI provider.
- **MCP Support**: Extensible via the Model Context Protocol to connect with external tools.
- **Zero Config**: Works out of the box with sensible defaults.

## 📦 Installation

To install Paws, run the following command in your terminal:

```bash
curl -fsSL https://paws.sh/install | bash
```

Or via npm:

```bash
npm install -g @paws/cli
```

## ⚡ Quick Start

1.  **Initialize Paws** in your project directory:

    ```bash
    paws init
    ```

2.  **Ask a question**:

    ```bash
    paws "How do I implement a JWT auth middleware in Express?"
    ```

3.  **Refactor code**:

    ```bash
    paws refactor src/utils/helpers.js --goal "Improve performance"
    ```

## 🛠️ Usage

### Interactive Mode

Simply type `paws` to enter the interactive shell:

```bash
$ paws
~/project $ Explain the project structure
```

### One-Off Commands

```bash
paws -p "Fix the bug in src/App.js line 42"
```

### Configuration

You can customize Paws by creating a `paws.yaml` file in your project root or home directory.

```yaml
model: claude-3.5-sonnet
temperature: 0.7
custom_rules:
  - "Always use TypeScript types"
  - "Prefer functional programming patterns"
```

## 🤝 Contributing

We welcome contributions! Please see our [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to get started.

## 📄 License

Paws is open-source software licensed under the [MIT License](LICENSE).

---

<p align="center">
  Made with ❤️ for developers by developers.
</p>
