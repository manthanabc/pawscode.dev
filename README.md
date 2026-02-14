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

## 🔐 Running with Antigravity Proxy

> **⚠️ WARNING**: Using Antigravity proxy voids Google's Terms of Service and may result in your Google account being disabled. Please use a dummy account only.

Antigravity is a proxy service that allows you to route AI API requests through a centralized account management system.

### Installation and Setup

1. **Install Antigravity**:

   ```bash
   npm install -g antigravity
   ```

2. **Add your Antigravity account**:

   ```bash
   antigravity account add
   ```

   Follow the prompts to authenticate with your Antigravity account.

3. **Start the Antigravity proxy**:

   ```bash
   antigravity proxy start
   ```

   The proxy will start running, typically on `http://localhost:3000` or a configured port.

### Configure Paws to Use Antigravity

Once the proxy is running, configure Paws to use it:

1. **Provider login from Paws**:

   ```bash
   paws login
   ```

   This will prompt you to select a provider and authenticate.

2. **Use a dummy API key**:

   When configuring your provider, you can use a dummy key since Antigravity handles the actual authentication. For example:

   ```yaml
   # In your paws.yaml configuration
   providers:
     openai:
       api_key: "dummy-key"
       base_url: "http://localhost:3000/openai/v1"
   ```

   Or set it via environment variables:

   ```bash
   export OPENAI_API_KEY="dummy-key"
   export OPENAI_BASE_URL="http://localhost:3000/openai/v1"
   ```

3. **Verify the connection**:

   ```bash
   paws "Hello, can you hear me?"
   ```

   If configured correctly, Paws will route your requests through the Antigravity proxy.

### Stopping the Proxy

When you're done, stop the Antigravity proxy:

```bash
antigravity proxy stop
```

## 🔐 Running with Antigravity Proxy

> **⚠️ WARNING**: Using Antigravity proxy voids Google's Terms of Service and may result in your Google account being disabled. Please use a dummy account only.

Antigravity Claude Proxy is a proxy server that exposes an Anthropic-compatible API backed by Antigravity's Cloud Code, allowing you to use Claude and Gemini models.

### Installation and Setup

1. **Install Antigravity Claude Proxy**:

   ```bash
   npm install -g antigravity-claude-proxy@latest
   ```

   Or run directly with npx (no install needed):
   ```bash
   npx antigravity-claude-proxy@latest start
   ```

2. **Add your Antigravity account**:

   **Method A: Web Dashboard (Recommended)**
   - With proxy running, open `http://localhost:8080` in your browser
   - Navigate to the **Accounts** tab and click **Add Account**
   - Complete Google OAuth authorization in the popup window

   **Method B: CLI (Desktop or Headless)**
   ```bash
   # Desktop (opens browser)
   antigravity-claude-proxy accounts add
   
   # Headless (Docker/SSH)
   antigravity-claude-proxy accounts add --no-browser
   ```

   **Method C: Automatic (Antigravity Users)**
   - If you have the **Antigravity** app installed and logged in, the proxy will automatically detect your local session. No additional setup is required.

3. **Start the Antigravity proxy**:

   ```bash
   antigravity-claude-proxy start
   ```

   The proxy runs on `http://localhost:8080` by default.

### Configure Paws to Use Antigravity

Once the proxy is running, configure Paws to use it:

1. **Provider login from Paws**:

   ```bash
   paws provider login
   ```

   This will prompt you to select a provider and authenticate.

2. **Enter a dummy API key**:

   When configuring your provider, you can use a dummy key since Antigravity handles the actual authentication. For example, when prompted for an API key, you can enter `dummy-key` or any placeholder value.

3. **Set the base URL**:

   Configure Paws to use the Antigravity proxy URL:
   ```bash
   export ANTHROPIC_BASE_URL="http://localhost:8080"
   ```

4. **Verify the connection**:

   ```bash
   paws "Hello, can you hear me?"
   ```

   If configured correctly, Paws will route your requests through the Antigravity proxy.

### Stopping the Proxy

When you're done, stop the Antigravity proxy:

```bash
# Stop the proxy server (Ctrl+C in the terminal where it's running)
```

### Monitoring

Check account status, subscription tiers, and quota anytime:

```bash
# Check account status and quota limits
curl "http://localhost:8080/account-limits?format=table"
```

### Available Models

The proxy provides access to:

- **Claude Models**: claude-sonnet-4-5-thinking, claude-opus-4-5-thinking, claude-sonnet-4-5
- **Gemini Models**: gemini-3-flash, gemini-3-pro-low, gemini-3-pro-high, gemini-2.5-flash-lite

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
