<div align="center">
  <img src="https://your-logo-url.png" alt="Contextract Logo" width="200"/>

  # Contextract
  
  *Intelligent Context Selection for AI-Powered Development*

  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  [![Made with Bash](https://img.shields.io/badge/Made%20with-Bash-1f425f.svg)](https://www.gnu.org/software/bash/)
  [![Powered by DeepSeek](https://img.shields.io/badge/Powered%20by-DeepSeek-blue)](https://deepseek.com)

</div>

## 🌟 Overview

Contextract is a powerful CLI tool that revolutionizes how you work with AI coding assistants. It analyzes your codebase using DeepSeek's AI to intelligently select the most relevant files for your specific task or question. Perfect for use with tools like [Aider](https://github.com/paul-gauthier/aider), it ensures your AI assistant has exactly the context it needs - no more, no less.

### 🎯 Key Features

- **Intelligent Context Selection**: AI-powered selection of relevant files based on your query
- **Project Understanding**: Generates and uses technical summaries of your codebase
- **Global Usage**: Works from any directory in your project
- **Flexible File Filtering**: Customizable file extension filtering
- **Smart Caching**: Reuse existing summaries for faster responses

## 🚀 Installation

### Method 1: Direct Installation (Recommended)
```bash
# Clone the repository
git clone https://github.com/yourusername/contextract.git

# Install required global npm packages
npm install -g minimist directory-tree axios fs-extra

# Move the script to your binary directory
sudo cp contextract /usr/local/bin/
sudo chmod +x /usr/local/bin/contextract

# Set up your DeepSeek API key (add this to your .bashrc or .zshrc)
export DEEPSEEK_API_KEY='your-api-key-here'
```

### Method 2: Manual Download
```bash
# Download the script directly
sudo curl -o /usr/local/bin/contextract https://raw.githubusercontent.com/m3tamatt/contextract/main/contextract

# Make it executable
sudo chmod +x /usr/local/bin/contextract

# Install required global npm packages
npm install -g minimist directory-tree axios fs-extra

# Set up your DeepSeek API key (add this to your .bashrc or .zshrc)
export DEEPSEEK_API_KEY='your-api-key-here'
```

### Verification
```bash
# Verify installation
contextract --version
# or
which contextract  # Should show /usr/local/bin/contextract
```

## 💡 Usage

Contextract can be run from any directory in your project. It will analyze the current directory and its subdirectories.

### Basic Usage:

```bash
# Generate new context analysis
contextract -e "js ts" -p "How does the authentication system work?"

# Output will look like:
🌳 Generating NEW project structure for extensions: js ts
📝 Analyzing project structure...
🧠 Processing with Deepseek API...
✨ Recommended files to add:
/add src/auth/AuthProvider.tsx src/auth/useAuth.ts src/pages/api/auth/[...nextauth].ts src/config/auth.config.ts

# Use existing analysis (faster)
contextract --existing -p "Show me the database models"

# Output:
📁 Using EXISTING project summary...
🧠 Processing with Deepseek API...
✨ Recommended files to add:
/add src/models/User.ts src/models/Post.ts src/models/Comment.ts src/db/schema.ts
```

### Command Options

```bash
contextract [options]

Options:
  -e, --extensions <ext>   Space-separated list of file extensions to analyze
  -p, --prompt <prompt>    Your question or task description
  --existing              Use existing project summary (faster)
```

## 🛠️ How It Works

1. **Project Analysis Phase**
   ```mermaid
   graph LR
   A[Scan Directory] --> B[Filter Files]
   B --> C[Generate Tree]
   C --> D[Create Summaries]
   ```

2. **Context Selection Phase**
   ```mermaid
   graph LR
   A[Process Query] --> B[AI Analysis]
   B --> C[Select Files]
   C --> D[Return Context]
   ```

## 🎨 Real-World Examples

### Authentication Implementation
```bash
$ contextract -e "ts tsx" -p "How is user authentication implemented?"
✨ Recommended files to add:
/add src/auth/AuthContext.tsx
    src/auth/useAuth.hook.ts
    src/pages/api/auth/login.ts
    src/pages/api/auth/logout.ts
    src/config/auth.config.ts
```

### API Endpoint Analysis
```bash
$ contextract -e "ts js" -p "Show me all API endpoints for user management"
✨ Recommended files to add:
/add src/api/users/index.ts
    src/api/users/[id].ts
    src/middleware/auth.ts
    src/types/api.ts
```

## ⚙️ Configuration

Create a `.contextractrc` in your home directory or project root:

```json
{
  "maxRetries": 3,
  "apiTimeout": 150,
  "contextLimit": 6000000,
  "retryDelay": 2,
  "excludeDirs": ["node_modules", "dist", ".git"],
  "defaultExtensions": ["js", "ts", "tsx"]
}
```

## 🔧 Requirements

- Node.js ≥ 14
- npm ≥ 6
- DeepSeek API key

## 🚦 Status Codes

| Emoji | Meaning |
|-------|---------|
| 🌳 | Generating new analysis |
| 📁 | Using cached analysis |
| 🧠 | Processing with AI |
| ✨ | Success |
| ❌ | Error |

## 🤝 Contributing

We love contributions! See our [Contributing Guide](CONTRIBUTING.md) for details.

```bash
# Development setup
git clone https://github.com/m3tamatt/contextract.git
cd contextract
npm install
npm link

# Run tests
npm test
```

## 🙏 Acknowledgments

- [Aider](https://github.com/paul-gauthier/aider) - Revolutionary AI pair programming
- [DeepSeek](https://deepseek.com) - Powerful AI capabilities
- All our amazing contributors

---

<div align="center">
  <sub>Built by m3tamatt ❤️</sub>
  
  [GitHub](https://github.com/m3tamatt)
</div>
