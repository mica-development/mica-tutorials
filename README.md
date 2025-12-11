# Mica Tutorials
Programming Language Mica Tutorials

## Getting Started

### Installation

To install Mica on your system, follow these steps:

1. **Download the Mica package:**
   ```bash
   wget -q https://github.com/mica-development/mica-tutorials/releases/download/v0.0.1/mica_4.0.0_amd64.deb
   ```

2. **Install the package:**
   ```bash
   sudo apt-get install ./mica_4.0.0_amd64.deb
   ```

3. **Clean up the installation file:**
   ```bash
   rm ./mica_4.0.0_amd64.deb
   ```

4. **Verify the installation:**
   ```bash
   mica --version
   ```

### Quick Install (Single Command)

For convenience, you can run all steps in one command:

```bash
wget -q https://github.com/mica-development/mica-tutorials/releases/download/v0.0.1/mica_4.0.0_amd64.deb && \
sudo apt-get install ./mica_4.0.0_amd64.deb && \
rm ./mica_4.0.0_amd64.deb && \
mica --version
```

## Recommended Keyboard Shortcuts

For a better development experience, add these shortcuts to your user keybindings:
- **Ctrl+0** - Reset Zoom
- **F6** - Debug Current Mica Binary
- **F7** - Build Selected Mica Example

To add them:
1. Open **Preferences: Open Keyboard Shortcuts (JSON)** (Ctrl+K Ctrl+S, then click the file icon)
2. Copy and paste the following into your `keybindings.json`:

```json
[
  {
    "key": "ctrl+0",
    "command": "workbench.action.zoomReset"
  },
  {
    "key": "f6",
    "command": "workbench.action.tasks.runTask",
    "args": "Build Selected Mica Example"
  },
  {
    "key": "f7",
    "command": "workbench.action.debug.selectandstart",
    "args": {
      "config": "Debug Current Mica Binary"
    },
    "when": "debuggersAvailable"
  }
]
```
