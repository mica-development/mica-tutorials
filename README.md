# 🚀 Getting Started with the Mica Programming Language

Welcome to the Mica programming language tutorials! This guide will walk you through everything you need to start developing with Mica using GitHub Codespaces and Visual Studio Code.

## 📋 Prerequisites

Before you begin, you'll need:
- A GitHub account (free)
- An internet connection
- A web browser

No local installation required! We'll use GitHub Codespaces for a ready-to-code environment.

---

## 📚 Tutorial Examples Overview

This repository contains a curated collection of Mica programming examples, each designed to teach specific language features and concepts. Start with `hello_world` and progress through the examples as you become more comfortable with Mica.

### Available Examples

| Example | Description | Key Concepts |
|---------|-------------|--------------|
| **hello_world** | The classic first program | Basic program structure, imports, output |
| **type_promotion** | Type casting and conversions | Implicit/explicit promotions, compile-time optimization, numeric type system |
| **math_power** | Mathematical function library | float32/float64 functions, trigonometry, logarithms, rounding, precision differences |
| **nesting_craziness** | Advanced nested functions | Pascal-style nested procedures, lexical scoping, complex call chains |
| **utf_sources** | Unicode and internationalization | UTF-8 source code, UTF-32 strings, multilingual identifiers, emoji support |
| **playground** | General experimentation space | Numeric types, pointers, flexible declaration order |

### 🎯 Recommended Learning Path

1. **hello_world** - Start here to understand basic program structure
2. **type_promotion** - Learn about Mica's type system and conversions
3. **math_power** - Explore the mathematical function library
4. **playground** - Experiment with various Mica features
5. **utf_sources** - Discover Mica's powerful Unicode support
6. **nesting_craziness** - Master advanced scoping and nested functions

Each example includes comprehensive comments explaining the concepts being demonstrated. Feel free to modify the examples and experiment with the code!

---

## Step 1: Install Visual Studio Code

Visual Studio Code (VS Code) is a free, lightweight code editor that works on any platform.

### Windows
1. Visit [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Click **Download for Windows**
3. Run the downloaded installer (`VSCodeSetup.exe`)
4. Follow the installation wizard (accept defaults)
5. Launch VS Code from the Start Menu

### macOS
1. Visit [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Click **Download for Mac**
3. Open the downloaded `.zip` file
4. Drag **Visual Studio Code** to your Applications folder
5. Launch VS Code from Applications

### Linux
#### Ubuntu/Debian:
```bash
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
sudo apt update
sudo apt install code
```

#### Fedora/RHEL:
```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
sudo dnf check-update
sudo dnf install code
```

---

## Step 2: Login to GitHub in VS Code

1. **Open VS Code**
2. Click on the **Accounts** icon in the lower-left corner (profile icon)
3. Select **Sign in to Sync Settings** or **Sign in with GitHub**
4. A browser window will open asking you to authorize VS Code
5. Click **Authorize Visual Studio Code**
6. You may need to enter your GitHub credentials
7. Once authorized, return to VS Code - you should now see your GitHub username in the lower-left corner

---

## Step 3: Connect to a GitHub Codespace

GitHub Codespaces provides a complete development environment in the cloud, so you don't need to install anything locally!

### Option A: Create Codespace from GitHub Website

1. **Navigate to the repository:** [https://github.com/mica-development/mica-tutorials](https://github.com/mica-development/mica-tutorials)
2. Click the green **Code** button
3. Select the **Codespaces** tab
4. Click **Create codespace on main**
5. Wait for the codespace to initialize (this may take 1-2 minutes)
6. Your browser will open a VS Code environment ready to use!

### Option B: Create Codespace from VS Code

1. **Open VS Code**
2. Press `F1` or `Ctrl+Shift+P` (Windows/Linux) / `Cmd+Shift+P` (Mac) to open the Command Palette
3. Type **Codespaces: Create New Codespace**
4. Select **Create from repository**
5. Search for and select: `mica-development/mica-tutorials`
6. Choose the **main** branch
7. Select your preferred machine type (2-core is sufficient for learning)
8. Wait for the codespace to initialize
9. Your codespace is ready!

---

## Step 4: Install Mica in Your Codespace

Once your codespace is running, it's time to install the Mica programming language compiler.

### Quick Install (Recommended)

Open the terminal in your codespace (`` Ctrl+` `` or **Terminal → New Terminal**) and run:

```bash
wget -q https://github.com/mica-development/mica-tutorials/releases/download/v0.0.1/mica_4.0.0_amd64.deb && \
sudo apt-get install ./mica_4.0.0_amd64.deb && \
rm ./mica_4.0.0_amd64.deb && \
mica --version
```

### Step-by-Step Install

Alternatively, you can install step by step:

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

You should see the Mica version information displayed!

---

## Step 5: Try Your First Mica Program

Let's run the classic "Hello, World!" program to ensure everything is working.

1. **Navigate to the example:**
   ```bash
   cd hello_world
   ```

2. **View the example code:**
   ```bash
   cat hello_world.mica
   ```

3. **Compile with debug information and link:**
   ```bash
   mica --compile --link --purge --optimize debug --source hello_world.mica --build ../build
   ```

4. **Run the example and verify the size of its executable:**
   ```bash
   ../build/hello_world
   ll ../build/hello_world
   ```   

5. **Compile without debug information and link:**
   ```bash
   mica --compile --link --purge --optimize release --source hello_world.mica --build ../build
   ```

6. **Run the example and verify the size of its executable again:**
   ```bash
   ../build/hello_world
   ll ../build/hello_world
   ```   

Congratulations! You've just run your first Mica program! 🎉

---

## Step 6: Debug Your Mica Program in VS Code

Debugging is essential for understanding how your program works and finding issues. VS Code provides powerful debugging capabilities for Mica programs using keyboard shortcuts.

### Prerequisites

Make sure you have set up the keyboard shortcuts mentioned in the Development Tips section:
- **F6** - Build Selected Mica Example (with debug information)
- **F7** - Debug Current Mica Binary

### Debugging Workflow

1. **Open your Mica source file:**
   
   Open `hello_world.mica` in the editor (or any other Mica program you want to debug).

2. **Set a breakpoint:**
   
   Click in the left margin (gutter) next to a line number where you want to pause execution. A red dot will appear indicating a breakpoint. For example, set a breakpoint on the line with the `println` statement.

3. **Compile with debug information (F6):**
   
   Press **F6** to build your Mica program. You'll be prompted to select:
   - **Source file:** Choose your `.mica` file (e.g., `hello_world.mica`)
   - **Optimization level:** Select **debug** (includes debug symbols)
   - **Quality gate:** Select your preferred quality level
   - **Target platform:** Select your target platform
   
   The program will be compiled with debug information and placed in the `build` directory.

4. **Start debugging session (F7):**
   
   Press **F7** to start the debugging session. VS Code will:
   - Prompt you to select the binary to debug (if multiple exist)
   - Launch the debugger with your compiled program
   - Stop at your breakpoint
   
5. **Use debugging controls:**
   
   Once paused at a breakpoint, use the debugging toolbar or keyboard shortcuts:
   - **Continue (F5):** Resume execution until the next breakpoint
   - **Step Over (F10):** Execute the current line and move to the next
   - **Step Into (F11):** Enter into function calls
   - **Step Out (Shift+F11):** Exit the current function
   - **Restart (Ctrl+Shift+F5):** Restart the debugging session
   - **Stop (Shift+F5):** End the debugging session

6. **Inspect variables:**
   
   While debugging, you can:
   - Hover over variables to see their values
   - View the **Variables** panel in the left sidebar to see all local and global variables
   - Use the **Watch** panel to monitor specific expressions
   - Check the **Call Stack** to understand the execution flow

### Quick Debugging Tips

- **Build before debugging:** Always press **F6** first to ensure your latest code changes are compiled
- **Debug vs. Release builds:** Use `--optimize debug` for debugging (larger binaries with symbols) and `--optimize release` for production (smaller, optimized binaries)
- **Multiple breakpoints:** Set breakpoints at different locations to step through complex logic
- **Debug Console:** Use the Debug Console to evaluate expressions while debugging
- **Conditional breakpoints:** Right-click a breakpoint to add conditions

### Example Debugging Session

Here's a typical debugging workflow:

```bash
# 1. Navigate to your example directory
cd hello_world

# 2. In VS Code:
#    - Open hello_world.mica
#    - Set a breakpoint on the println line
#    - Press F6 and select:
#      * Source: hello_world.mica
#      * Optimization: debug
#    - Press F7 to start debugging
#    - Use F10 to step through the code
#    - Press F5 to continue execution
```

Now you can debug your Mica programs efficiently! 🐛✨

---

## 🛠️ Development Tips

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
### Using the Build Task

This repository includes a pre-configured build task for compiling Mica examples:

1. Press `F1` to open the Command Palette
2. Type **Tasks: Run Task**
3. Select **Build Selected Mica Example**
4. Follow the prompts to select your target file and build options

Or simply press **F6** after setting up the keyboard shortcut above!

---

## 📚 Learning Resources

### Official Documentation

For comprehensive documentation, tutorials, and language references, visit the official Mica Development website:

**[https://mica-dev.com/](https://mica-dev.com/)**

Here you'll find:
- Complete language reference
- Advanced tutorials and examples
- API documentation
- Community forums and support
- Latest news and updates

### Explore the Examples

This repository contains various examples to help you learn Mica. Start with the `hello_world` example and gradually explore more complex programs as you become comfortable with the language.

---

## 💡 Tips for Success

- **Save your work regularly** - Codespaces automatically save, but it's good practice
- **Explore the examples** - Each example demonstrates different Mica features
- **Read the documentation** - Visit [mica-dev.com](https://mica-dev.com/) for in-depth guides
- **Experiment** - Try modifying the examples to see how changes affect the output
- **Ask questions** - Engage with the Mica community for support

---

## 🤝 Need Help?

If you encounter any issues or have questions:

1. **Check the documentation** at [https://mica-dev.com/](https://mica-dev.com/)
2. **Review the examples** in this repository
3. **Visit the official Mica Development website** for support resources
4. **Report issues** on the GitHub repository

---

## 🎓 Next Steps

Now that you have Mica set up, you're ready to:

1. ✅ Explore more examples in this repository
2. ✅ Read the official documentation at [mica-dev.com](https://mica-dev.com/)
3. ✅ Write your own Mica programs
4. ✅ Join the Mica community and share your projects

---

## 📄 License

See the [LICENSE](LICENSE) file for details.

---

## 🌟 About Mica

Mica is developed and maintained by **Mica Development UG**. For more information about the language, company, and ecosystem, visit [https://mica-dev.com/](https://mica-dev.com/).

---

**Happy coding with Mica! We're excited to see what you'll build.** 🚀

---

*Last updated: December 2025*