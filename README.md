# 🤖 Discord Yaps BOT (Paid)

> An intelligent Discord automation bot with AI-powered reply system using Groq API, designed for natural conversation automation and smart message handling across multiple accounts.

[![Node.js Version](https://img.shields.io/badge/node.js-14+-green.svg)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/vonssy/Discord-Yaps-BOT.svg)](https://github.com/vonssy/Discord-Yaps-BOT/stargazers)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Price](#price)
- [Proxy Support](#proxy-support)
- [Support](#support)
- [Contributing](#contributing)

## 🎯 Overview

<div align="center">
  <img src="images/image.png" alt="Overview" width="800">
  <p><em>An advanced Discord automation bot that uses AI (Groq LLaMA 3.1) to generate natural, human-like responses. The bot can monitor multiple Discord channels, reply to messages intelligently, and maintain conversations while appearing completely natural.</em></p>
</div>

**Key Highlights:**
- 🧠 AI-powered responses using Groq API
- 🔄 Multi-account support with proxy rotation
- 🎯 Smart message filtering and validation
- ⏰ Customizable interval timing per channel
- 🛡️ Rate limit protection with automatic API key rotation
- 💬 Support for both AI and fixed message modes

## ✨ Features

### Core Features
- 🤖 **AI-Powered Replies** - Natural conversation using Groq LLaMA 3.1 model
- 📊 **Multi-Account Management** - Handle multiple Discord accounts simultaneously
- 🔄 **Smart Proxy Rotation** - Automatic proxy switching on failures
- ⚡ **Flexible Channel Modes**:
  - **GM Channel**: Send scheduled greetings/messages
  - **General Channel (AI)**: AI-powered conversation
  - **Custom Channels**: Configurable AI or message mode

### Intelligent Features
- 🎯 **Smart Reply Logic**:
  - Only replies to meaningful messages
  - Filters out emojis, mentions, and low-value content
  - 3x reply limit per user to avoid spamming
  - Context-aware responses based on conversation history
  
- 🔐 **API Key Management**:
  - Multiple Groq API key support
  - Automatic rotation on rate limits
  - Cooldown system for blocked keys
  - Invalid key removal

- 📝 **Message Validation**:
  - Emoji-only message filtering
  - Mention-only message filtering
  - Punctuation-only filtering
  - Low-value text detection (ok, lol, thanks, etc.)

### User Interface
- 📱 **Interactive Menu System**
  - Fetch Channel IDs from Discord servers
  - Setup accounts and channels
  - Visual server and channel browser
  - Easy configuration management

## 💰 Price
- **Price:** $10 in Cryptocurrency
- **Payment Methods:** EVM, TON, SOL, SUI
- **Contact:** [Vonssy](https://t.me/vonssy_2nd)

## 📋 Requirements

- **Node.js:** Version 14 or higher
- **Groq API Key:** Get from [Groq Console](https://console.groq.com)
- **Discord Token(s):** Your Discord account token(s)
- **NPM Packages:**
  - `axios` - HTTP requests
  - `readline` - Interactive CLI
  - `https-proxy-agent` - Proxy support

## 🛠 Installation

### 1. Extract The Project

```bash
unzip Discord-Yaps-BOT.zip
cd Discord-Yaps-BOT
```

### 2. Install Dependencies

```bash
npm install
```

## ⚙️ Configuration

### 1. Groq API Key Setup

Create `groq_api_key.txt` in the project directory:

```
your_groq_api_key_1
your_groq_api_key_2
your_groq_api_key_3
```

**How to get Groq API Key:**
1. Visit [console.groq.com](https://console.groq.com)
2. Sign up/Login
3. Go to API Keys section
4. Create new API key
5. Copy and paste into `groq_api_key.txt`

### 2. Discord Token Setup

Create `accounts.json` in the project directory:

```json
[
    {
        "displayName": "display_name_1 (eg. Vonssy 1)",
        "discordToken": "discord_token_1"
    },
    {
        "displayName": "display_name_2 (eg. Vonssy 2)",
        "discordToken": "discord_token_2"
    },
    {
        "displayName": "display_name_3 (eg. Vonssy 3)",
        "discordToken": "discord_token_3"
    }
]
```

**How to get Discord Token:**
1. Open Discord in browser (Chrome recommended)
2. Press `Ctrl + Shift + I` (Developer Tools)
3. Go to "Network" tab
4. Type `/api` in filter
5. Click any request
6. Find "Authorization" in headers
7. Copy the token value

**⚠️ Warning:** Never share your Discord token with anyone!

### 3. Proxy Configuration (Optional)

Create `proxy.txt` in the project directory:

```
192.168.1.1:8080
http://192.168.1.2:8080
http://username:password@192.168.1.3:8080
```

**Supported formats:**
- `http://IP:PORT`
- `http://username:password@IP:PORT`

## 🚀 Usage

### Start the Bot

```bash
node bot.js
```

### Main Menu Options

When you run the bot, you'll see 4 main options:

#### 1. **Fetch Channel ID**
- Browse your Discord servers
- View all text channels
- Get channel IDs easily
- Navigate with arrow keys

**Steps:**
1. Select account
2. Choose server
3. View channels with IDs
4. Copy the Channel ID you need

#### 2. **Setup Accounts**
- Add/edit server configurations
- Create channel settings
- Configure AI or message mode
- Set intervals and messages

**Steps:**
1. Select account
2. Add/select server
3. Choose channel type:
   - **GM**: Fixed message mode
   - **General (AI)**: AI conversation mode
   - **Custom**: Your own channel
4. Enter Channel ID
5. Set interval (minutes)
6. Configure message or AI mode

#### 3. **Run Program**
- Start the automation
- Monitor all channels
- AI replies automatically
- View real-time status

#### 4. **Exit Program**
- Safely close the bot

## 🔧 How It Works

### Channel Modes

#### GM Channel (Message Mode)
```json
{
    "gm": {
        "id": "1234567890",
        "interval": 60,
        "message": "Good morning!"
    }
}
```
- Sends fixed message at intervals
- No AI processing
- Simple greeting/announcement

#### General Channel (AI Mode)
```json
{
    "general": {
        "id": "9876543210",
        "interval": 30,
        "useAI": true
    }
}
```
- AI-powered responses
- Reads recent messages
- Replies naturally
- Context-aware

#### Custom Channel
```json
{
    "custom-chat": {
        "id": "1122334455",
        "interval": 45,
        "useAI": true
    }
}
```
- Your custom configuration
- Choose AI or message mode
- Flexible naming

### AI Reply Logic

The bot uses intelligent filtering:

**✅ Will Reply To:**
- Genuine questions
- Meaningful statements
- Direct replies to your messages
- Conversations worth continuing

**❌ Will NOT Reply To:**
- Emoji-only messages
- Mention-only messages
- "ok", "lol", "thanks" (low-value)
- Already replied 3x to same user
- Attachments, embeds, stickers

### Interval System

- **Base Interval**: Set in config (e.g., 30 minutes)
- **Random Range**: Base + 0 to 5 minutes
- **Purpose**: Appear more human-like
- **Example**: 30 min config = 30-35 min actual

### API Key Rotation

1. **Normal Use**: Uses current API key
2. **Rate Limited**: 
   - Blocks key for 30 minutes
   - Rotates to next key
   - Logs cooldown
3. **Invalid Key**: 
   - Removes permanently
   - Rotates to next key
   - Shows warning

## 🌐 Proxy Support

### When to Use Proxies

- Multiple accounts
- Avoiding rate limits
- Geographic restrictions
- Privacy protection

### Proxy Rotation

- **GM Channels**: 1 retry (fast mode)
- **AI Channels**: Tries all proxies
- **Auto-rotation**: On proxy failure
- **Round-robin**: Even distribution

## 📊 Status Display

```
✓ System Status
  ├─ Accounts: 3
  ├─ Groq API Keys: 5 total (4 active, 1 blocked)
  ├─ Proxies: 10
  └─ Features: 3x Reply Limit | Smart Filtering | API Rotation
```

### Runtime Output

```
┌─ Account1 → ServerName → #general
│ 💬 @user replied to us (1/3): "Hey, how are you?"
│ 🧠 Reading previous message context...
│ 🗂 Context (our msg): "Hello there!"
│ 🤖 Generating AI reply...
│ ⌨ Typing...
│ ✓ Replied: "I'm doing great, thanks for asking!"
└────────────────────────────────
```

## 💖 Support the Project

If this bot has been helpful, consider supporting:

### Cryptocurrency Donations

| Network | Address |
|---------|---------|
| **EVM** | `0xe3c9ef9a39e9eb0582e5b147026cae524338521a` |
| **TON** | `UQBEFv58DC4FUrGqinBB5PAQS7TzXSm5c1Fn6nkiet8kmehB` |
| **SOL** | `E1xkaJYmAFEj28NPHKhjbf7GcvfdjKdvXju8d8AeSunf` |
| **SUI** | `0xa03726ecbbe00b31df6a61d7a59d02a7eedc39fe269532ceab97852a04cf3347` |

## 🤝 Contributing

Contributions are welcome! Here's how:

1. ⭐ **Star this repository**
2. 👥 **Follow** for updates
3. 🐛 **Report issues** on GitHub
4. 💡 **Suggest features**
5. 🔧 **Submit pull requests**

## ⚠️ Disclaimer

- Use at your own risk
- Discord may ban accounts using automation
- This bot is for educational purposes
- Always follow Discord's Terms of Service
- Use responsibly and ethically

## 🔍 Troubleshooting

### Common Issues

**"accounts.json not found"**
- Create the file in project root
- Check JSON syntax

**"All API keys are rate limited"**
- Wait for cooldown (30 minutes)
- Add more API keys

**"Invalid Discord Token"**
- Get fresh token from Discord
- Ensure no extra spaces
- Check token format

**Bot not replying**
- Check interval settings
- Verify channel IDs
- Check API key status
- Review message filters

## 📞 Contact & Support

- **Developer:** vonssy
- **Telegram:** [@vonssy_2nd](https://t.me/vonssy_2nd)
- **Issues:** [GitHub Issues](https://github.com/vonssy/Discord-Yaps-BOT/issues)
- **Discussions:** [GitHub Discussions](https://github.com/vonssy/Discord-Yaps-BOT/discussions)

---

<div align="center">

**Made with ❤️ by [vonssy](https://github.com/vonssy)**

*Thank you for using Discord Yaps BOT! Don't forget to ⭐ star this repository.*

</div>