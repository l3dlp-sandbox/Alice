# Alice

Say "Hi" to Alice 👋, your open-source AI companion designed to live on your desktop.

Alice brings together voice interaction, intelligent context awareness, powerful tooling, and a friendly personality to assist you with everything from daily tasks to deeper creative work. She’s more than a chatbot, she’s built to feel present, responsive, emotionally engaging, and deeply useful.

<p align="center">
  <img src="https://github.com/pmbstyle/Alice/blob/main/animation.gif?raw=true" alt="Alice Animation">
</p>



## ✨ Key Features

### 💻 Local and Cloud use

Alice designed to work with Cloud(OpenAI/OpenRouter) and Local LLMs (Ollama/LM Studio).
Has built-in speech-to-text, text-to-speech, and embedding services.
While the OpenAI cloud API is preferred and provides the best user experience, Alice can go **fully local** (experimental).

### 🗣️ Voice Interaction

* Fast, VAD-powered voice recognition (via `gpt-4o-transcribe` or `whisper-large-v3`)
* Natural-sounding responses with OpenAI TTS and optional support for local multilingual text-to-speech via Piper TTS
* Interruptible speech and streaming response cancellation for smoother flow

### 🧠 Memory & Context

* **Thoughts**: Short-term context stored in Hnswlib vector DB
* **Memories**: Structured long-term facts in local DB
* **Summarization**: Compact message history into context prompts
* **Emotion awareness**: Summaries include mood estimation for more human responses

### 🎨 Vision & Visual Output

* Screenshot interpretation using Vision API
* Image generation using `gpt-image-1`
* Animated video states (standby / speaking / thinking)

### 🪄 Computer Use Tools

Alice can now interact with your local system with user-approved permissions:

* 📂 File system browsing (e.g. listing folders)
* 💻 Shell command execution (`ls`, `mv`, `mkdir`, etc)
* 🔐 Granular command approvals:

  * One-time
  * Session-based
  * Permanent (revocable)
* 🔧 Settings tab "Permissions" lets you review and manage all approved commands

### ⚙️ Function Calling

* Web search (including Seaxng support)
* Google Calendar & Gmail integration
* Torrent search & download (via Jackett + qBittorrent)
* Time & date awareness
* Clipboard management
* Task scheduler (reminders and command execution)
* Open applications & URLs
* Image generation
* MCP server support

### 💬 Wake Word Support  
With the local STT model, you can now set a **wake-up word** (like "Hey, Siri").  
- Alice will always listen, but only process requests when the wake word is spoken.  
- Default mode is **auto language detection**, but you can also select a specific language in settings. 

### 💻 Dedicated Chrome [Extension](https://github.com/pmbstyle/alice-chrome-extension)

* Ask Alice about your active Chrome tab
* Context menu for selected text on a web page
  - Fact check this
  - Summarize this
  - Tell me more about it

### 🎛️ Flexible Settings

Fully customizable settings interface:

* LLM provider selection between OpenAI, OpenRouter, Ollama, LM Studio
* Cloud or local TTS, STT, Embeddings
* Model choice & parameters (temperature, top\_p, history, etc)
* Prompt and summarization tuning
* Audio/mic toggles & hotkeys
* Available tools & MCP configuration
* Google integrations



## 🚀 Download

👉 **[Download the latest release](https://github.com/pmbstyle/Alice/releases/latest)**

Follow the [Setup Instructions](https://github.com/pmbstyle/Alice/blob/main/docs/setupInstructions.md) to configure your API keys and environment.



## 🛠️ Technologies Used

* **Frontend:** [Vue.js](https://vuejs.org/), [TailwindCSS](https://tailwindcss.com/)
* **Desktop Shell:** [Electron](https://www.electronjs.org/)
* **State Management:** [Pinia](https://pinia.vuejs.org/)
* **AI APIs:** [OpenAI](https://platform.openai.com/), [OpenRouter](https://openrouter.ai/), [Groq](https://console.groq.com/)
* **Backend:** [Go](https://go.dev/)
* **Vector search engine**: [hnswlib-node](https://github.com/nmslib/hnswlib)
* **Local storage**: [better-sqlite3](https://github.com/WiseLibs/better-sqlite3)
* **Voice activity detection:** [VAD (Web)](https://github.com/ricky0123/vad)
* **Local STT & TTS:** [whisper.cpp](https://huggingface.co/ggerganov/whisper.cpp) & [Piper](https://github.com/rhasspy/piper)
* **Local Embeddings:** [all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2)
* **Animation:** [Kling Pro](https://fal.ai/)

Other tools:

* [Jackett](https://github.com/Jackett/Jackett) — Torrent aggregator
* [qBittorrent](https://www.qbittorrent.org/) — Torrent client



## 🧑‍💻 Getting Started (Development)

```bash
# 1. Clone the repo
$ git clone https://github.com/pmbstyle/Alice.git

# 2. Install dependencies
$ npm install

# 3. Set up your .env file (see .env.example for reference)
```

Follow [setup instructions](https://github.com/pmbstyle/Alice/blob/main/docs/setupInstructions.md) to obtain required API credentials.

```bash
# 4. Compile backend
npm run build:go

# 5. Run dev environment
$ npm run dev
```

### 📦 Production Build

Optionally, create an `app-config.json` file in the root directory for Google integration:

```json
{
  "VITE_GOOGLE_CLIENT_ID": "",
  "VITE_GOOGLE_CLIENT_SECRET": ""
}
```

```bash
# Build the app
$ npm run build
```

Install the output from the `release/` directory.



## 🐧 Community

* 🏗️ [ArchLinux AUR Package](https://aur.archlinux.org/packages/alice-ai-app-bin)



## 🤝 Contributing

Ideas, bug reports, feature requests - all welcome! Open an issue or PR, or just drop by to share your thoughts. Your input helps shape Alice into something wonderful 💚
