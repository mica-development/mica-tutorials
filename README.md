# Mica Tutorials
Programming Language Mica Tutorials

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
    "command": "workbench.action.debug.selectandstart",
    "args": {
      "config": "Debug Current Mica Binary"
    },
    "when": "debuggersAvailable"
  },
  {
    "key": "f7",
    "command": "workbench.action.tasks.runTask",
    "args": "Build Selected Mica Example"
  }
]
```

// ...existing code...