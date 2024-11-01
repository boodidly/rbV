# Ollama Terminal Chat

A beautiful terminal-based chat interface for Ollama with voice synthesis support.

![Terminal Chat Banner](https://i.imgur.com/your-image-here.png)

## Features

- 🎯 Direct integration with Ollama API
- 🎭 Multiple voice synthesis options
- ⌨️ Smooth typing animation
- 🎨 Beautiful terminal UI with colors
- 📝 Natural text wrapping
- ⚡ Fast response times

## Installation Guide for Arch Linux

### 1. Install System Dependencies

```bash
# Install Node.js and npm
sudo pacman -S nodejs npm

# Install system audio dependencies
sudo pacman -S festival festival-us

# Install Git
sudo pacman -S git
```

### 2. Install Ollama

```bash
# Install yay AUR helper if you don't have it
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

# Install Ollama from AUR
yay -S ollama-bin
```

### 3. Start Ollama Service

```bash
# Start Ollama service
systemctl --user start ollama

# Enable Ollama to start on boot (optional)
systemctl --user enable ollama
```

### 4. Download the LLaMA Model

```bash
# Pull the LLaMA 3.2 1B model
ollama pull llama3.2:1b
```

### 5. Install the Chat Application

```bash
# Clone the repository
git clone https://your-repo-url/ollama-terminal-chat.git
cd ollama-terminal-chat

# Install dependencies
npm install
```

### 6. Run the Application

```bash
# Start the chat
npm start
```

## Usage

### Available Commands

- `voice` - Toggle voice output on/off and select voice
- `voices` - List available voice options
- `help` - Show all available commands
- `exit` - Exit the chat

### Voice Options

The following voices are available:
- Alex (Default male voice)
- Samantha (Default female voice)
- Daniel (British male voice)
- Karen (Australian female voice)
- Moira (Irish female voice)

## Troubleshooting

### Audio Issues

If you encounter audio problems:

1. Check if the audio service is running:
```bash
systemctl --user status pipewire
```

2. Ensure audio permissions are correct:
```bash
groups $USER | grep audio
# If 'audio' is missing:
sudo usermod -a -G audio $USER
```

3. Test system audio:
```bash
speaker-test -t wav -c 2
```

### Ollama Connection Issues

If Ollama isn't responding:

1. Check if Ollama service is running:
```bash
systemctl --user status ollama
```

2. Verify the API is accessible:
```bash
curl http://localhost:11434/api/tags
```

3. Restart Ollama if needed:
```bash
systemctl --user restart ollama
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this project however you'd like.

## Credits

Built with ❤️ using:
- [Ollama](https://ollama.ai)
- [Node.js](https://nodejs.org)
- [say.js](https://github.com/Marak/say.js)
- [chalk](https://github.com/chalk/chalk)
- [inquirer](https://github.com/SBoudrias/Inquirer.js)