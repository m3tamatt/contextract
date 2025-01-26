<div align="center">
  <img src="https://your-logo-url.png" alt="Contextract Logo" width="200"/>

  # Contextract
  
  *Your AI-Powered Context Extraction Companion for Aider*

  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  [![Made with Bash](https://img.shields.io/badge/Made%20with-Bash-1f425f.svg)](https://www.gnu.org/software/bash/)
  [![Powered by DeepSeek](https://img.shields.io/badge/Powered%20by-DeepSeek-blue)](https://deepseek.com)

</div>

## 🌟 Overview

Contextract is an intelligent context extraction tool designed to enhance your experience with [Aider](https://github.com/paul-gauthier/aider). It leverages the power of DeepSeek Chat API to analyze your codebase, generate precise summaries, and provide the most relevant context for your AI-assisted development tasks.

### 🎯 Key Features

- **Smart Context Extraction**: Automatically identifies and extracts relevant code context based on your queries
- **Codebase Summarization**: Generates concise technical summaries of your entire project structure
- **Intelligent File Selection**: Uses AI to determine which files are most relevant to your task
- **Seamless Aider Integration**: Works perfectly as a context provider for Aider
- **Configurable & Extensible**: Easy to customize for different project types and requirements

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/m3tamatt/contextract.git

# Install required global npm packages
npm install -g minimist directory-tree axios fs-extra

# Set up your DeepSeek API key
export DEEPSEEK_API_KEY='your-api-key-here'

# Make the script executable
chmod +x contextract
```

## 💡 Usage

```bash
# Generate new context with file extensions
./contextract -e "js ts jsx tsx" -p "How do I implement user authentication?"

# Use existing project summary
./contextract --existing -p "What's the database schema?"

# Specify multiple file types
./contextract -e "py rb js" -p "Show me all API endpoints"
```

### 📝 Command Options

| Option | Description |
|--------|-------------|
| `-e, --extensions` | Specify file extensions to analyze |
| `-p, --prompt` | Your query or task description |
| `--existing` | Use existing project summary |

## 🛠️ How It Works

1. **Project Analysis**
   - Scans your project structure
   - Generates file trees
   - Creates technical summaries

2. **Context Extraction**
   - Analyzes your query
   - Identifies relevant files
   - Generates optimal context

3. **AI Processing**
   - Utilizes DeepSeek Chat API
   - Processes summaries
   - Returns precise file selections

## 🎨 Features in Detail

### Intelligent Summarization
Contextract creates comprehensive summaries including:
- Key imports/exports
- Main functions/classes
- Core logic flow
- Critical configurations
- Notable error handling

### Smart Context Selection
The tool intelligently selects:
- Directly related files
- Supporting context files
- Configuration dependencies
- Relevant documentation

## 🔧 Configuration

Customize behavior through environment variables:

```bash
MAX_RETRIES=3           # API retry attempts
API_TIMEOUT=150         # Timeout in seconds
CONTEXT_LIMIT=6000000   # Maximum context size
RETRY_DELAY=2           # Delay between retries
```

## 🌍 Requirements

- Node.js & npm
- curl
- DeepSeek API key
- Required npm packages:
  - minimist
  - directory-tree
  - axios
  - fs-extra

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Aider](https://github.com/paul-gauthier/aider) - The amazing AI pair programming tool
- [DeepSeek](https://deepseek.com) - For their powerful AI API
- All contributors and supporters

---

<div align="center">
  Made with ❤️ by m3tamatt • [GitHub](https://github.com/m3tamatt)
</div>
