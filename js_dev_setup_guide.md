# JavaScript Development Environment Setup Guide

Complete step-by-step guide for setting up a professional JavaScript, React, Node.js, and Next.js development environment with VS Code.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Step 1: Install Node.js and npm](#step-1-install-nodejs-and-npm)
- [Step 2: Install VS Code](#step-2-install-vs-code)
- [Step 3: Install Essential VS Code Extensions](#step-3-install-essential-vs-code-extensions)
- [Step 4: Configure VS Code Settings](#step-4-configure-vs-code-settings)
- [Step 5: Set Up Git (Optional but Recommended)](#step-5-set-up-git-optional-but-recommended)
- [Step 6: Create Your First Projects](#step-6-create-your-first-projects)
- [Step 7: Configure Code Formatting and Linting](#step-7-configure-code-formatting-and-linting)
- [Step 8: Install Additional Tools](#step-8-install-additional-tools)
- [Step 9: Browser Extensions](#step-9-browser-extensions)
- [Step 10: Verify Your Setup](#step-10-verify-your-setup)
- [Troubleshooting](#troubleshooting)
- [Next Steps](#next-steps)

---

## Prerequisites

- A computer running Windows, macOS, or Linux
- Administrator privileges to install software
- Basic familiarity with command line/terminal

---

## Step 1: Install Node.js and npm

### Windows/macOS:
1. Go to [nodejs.org](https://nodejs.org/)
2. Download the **LTS version** (Long Term Support)
3. Run the installer and follow the setup wizard
4. Accept all default settings during installation

### Linux (Ubuntu/Debian):
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Verify Installation:
Open your terminal/command prompt and run:
```bash
node --version
npm --version
```
You should see version numbers for both commands.

---

## Step 2: Install VS Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Download VS Code for your operating system
3. Install the application:
   - **Windows**: Run the downloaded `.exe` file
   - **macOS**: Drag the app to Applications folder
   - **Linux**: Follow the installation instructions for your distribution

4. Launch VS Code to ensure it works properly

---

## Step 3: Install Essential VS Code Extensions

Open VS Code and press `Ctrl+Shift+X` (or `Cmd+Shift+X` on Mac) to open the Extensions panel.

### Install these extensions one by one:

#### Core Extensions (Must-have):
1. **ES7+ React/Redux/React-Native snippets**
   - Search: "ES7+ React"
   - Publisher: dsznajder
   - Click "Install"

2. **Prettier - Code formatter**
   - Search: "Prettier"
   - Publisher: Prettier
   - Click "Install"

3. **ESLint**
   - Search: "ESLint"
   - Publisher: Microsoft
   - Click "Install"

4. **Auto Rename Tag**
   - Search: "Auto Rename Tag"
   - Publisher: Jun Han
   - Click "Install"

#### Helpful Extensions:
5. **GitLens — Git supercharged**
   - Search: "GitLens"
   - Publisher: GitKraken
   - Click "Install"

6. **Live Server**
   - Search: "Live Server"
   - Publisher: Ritwick Dey
   - Click "Install"

7. **Path Intellisense**
   - Search: "Path Intellisense"
   - Publisher: Christian Kohler
   - Click "Install"

8. **JavaScript (ES6) code snippets**
   - Search: "JavaScript ES6"
   - Publisher: charalampos karypidis
   - Click "Install"

---

## Step 4: Configure VS Code Settings

### Method 1: Settings UI
1. Press `Ctrl+,` (or `Cmd+,` on Mac) to open Settings
2. Configure these settings:
   - Search "format on save" → Enable "Editor: Format On Save"
   - Search "default formatter" → Set to "Prettier - Code formatter"
   - Search "tab size" → Set to 2
   - Search "auto save" → Set to "afterDelay"

### Method 2: Settings JSON (Recommended)
1. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
2. Type "Preferences: Open Settings (JSON)"
3. Replace the content with:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "editor.tabSize": 2,
  "files.autoSave": "afterDelay",
  "editor.wordWrap": "on",
  "editor.minimap.enabled": true,
  "workbench.iconTheme": "vs-seti",
  "terminal.integrated.fontSize": 14
}
```

4. Save the file (`Ctrl+S` or `Cmd+S`)

---

## Step 5: Set Up Git (Optional but Recommended)

### Install Git:
- **Windows**: Download from [git-scm.com](https://git-scm.com/)
- **macOS**: Install via Homebrew: `brew install git` or download from git-scm.com
- **Linux**: `sudo apt install git` (Ubuntu/Debian)

### Configure Git:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Verify Git Installation:
```bash
git --version
```

---

## Step 6: Create Your First Projects

### Create a React Application:
1. Open terminal in VS Code (`Ctrl+`` ` or `Cmd+`` `)
2. Navigate to your desired folder:
```bash
cd Desktop
mkdir my-projects
cd my-projects
```

3. Create React app:
```bash
npx create-react-app my-first-react-app
cd my-first-react-app
npm start
```

4. Your React app should open in browser at `http://localhost:3000`

### Create a Next.js Application:
```bash
cd ../
npx create-next-app@latest my-first-nextjs-app
cd my-first-nextjs-app
npm run dev
```

5. Your Next.js app should open at `http://localhost:3000`

### Create a Basic Node.js Project:
```bash
cd ../
mkdir my-node-project
cd my-node-project
npm init -y
```

6. Create a simple `index.js` file:
```javascript
console.log("Hello, Node.js!");

const express = require('express');
const app = express();
const PORT = 3000;

app.get('/', (req, res) => {
  res.send('Hello World from Node.js!');
});

app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

7. Install Express:
```bash
npm install express
```

8. Run your Node.js app:
```bash
node index.js
```

---

## Step 7: Configure Code Formatting and Linting

### Install Prettier Globally:
```bash
npm install -g prettier
```

### Create Prettier Configuration:
In each project folder, create a `.prettierrc` file:
```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false
}
```

### Set Up ESLint for React Projects:
```bash
cd my-first-react-app
npm install --save-dev eslint
npx eslint --init
```

Follow the prompts:
- How would you like to use ESLint? → "To check syntax and find problems"
- What type of modules? → "JavaScript modules (import/export)"
- Which framework? → "React"
- Does your project use TypeScript? → "No"
- Where does your code run? → "Browser"
- What format for config file? → "JSON"

### Add npm Scripts:
Add these to your `package.json`:
```json
{
  "scripts": {
    "lint": "eslint . --ext .js,.jsx",
    "lint:fix": "eslint . --ext .js,.jsx --fix",
    "format": "prettier --write ."
  }
}
```

---

## Step 8: Install Additional Tools

### Package Managers (Choose One):

#### Yarn (Alternative to npm):
```bash
npm install -g yarn
```

#### pnpm (Fast and efficient):
```bash
npm install -g pnpm
```

### Node Version Manager (Recommended):

#### nvm for macOS/Linux:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```

#### nvm-windows for Windows:
Download from [github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows)

### Global Utilities:
```bash
npm install -g nodemon          # Auto-restart Node.js apps
npm install -g live-server      # Simple development server
npm install -g http-server      # Another simple server option
```

---

## Step 9: Browser Extensions

Install these browser extensions for better development experience:

### Chrome/Edge Extensions:
1. **React Developer Tools**
   - Go to Chrome Web Store
   - Search "React Developer Tools"
   - Install the extension

2. **Redux DevTools** (if using Redux)
   - Search "Redux DevTools"
   - Install the extension

### Firefox Extensions:
- Same extensions are available in Firefox Add-ons

---

## Step 10: Verify Your Setup

### Test Node.js:
```bash
node --version
npm --version
```

### Test React:
```bash
cd my-first-react-app
npm start
```
- Should open browser with React logo spinning

### Test Next.js:
```bash
cd ../my-first-nextjs-app
npm run dev
```
- Should show Next.js welcome page

### Test VS Code Extensions:
1. Open a `.js` file
2. Type `rafce` and press Tab → Should create a React functional component
3. Save the file → Should auto-format with Prettier
4. Make a syntax error → ESLint should show red underlines

### Test Terminal in VS Code:
- Press `Ctrl+`` ` → Should open integrated terminal
- Run `npm --version` → Should show version number

---

## Troubleshooting

### Common Issues and Solutions:

#### "npm command not found"
- **Solution**: Restart your terminal/VS Code after installing Node.js
- **Alternative**: Add Node.js to your PATH manually

#### Extensions not working
- **Solution**: Reload VS Code window (`Ctrl+Shift+P` → "Developer: Reload Window")

#### Prettier not formatting on save
- **Solution**: 
  1. Check if Prettier is set as default formatter
  2. Ensure "Format on Save" is enabled
  3. Try `Ctrl+Shift+P` → "Format Document"

#### Port already in use
- **Solution**: 
  ```bash
  # Kill process using port 3000
  npx kill-port 3000
  # Or use different port
  npm start -- --port 3001
  ```

#### Permission errors (macOS/Linux)
- **Solution**: Use `sudo` for global installations or fix npm permissions:
  ```bash
  sudo chown -R $(whoami) ~/.npm
  ```

---

## Next Steps

### Learn More:
1. **JavaScript Fundamentals**
   - ES6+ features (arrow functions, destructuring, modules)
   - Async/await and Promises
   - Array methods (map, filter, reduce)

2. **React Concepts**
   - Components and JSX
   - State and Props
   - Hooks (useState, useEffect)
   - Event handling

3. **Node.js Development**
   - Express.js framework
   - REST API development
   - Database integration (MongoDB, PostgreSQL)

4. **Next.js Features**
   - Server-side rendering (SSR)
   - Static site generation (SSG)
   - API routes
   - File-based routing

### Recommended Learning Resources:
- [MDN Web Docs](https://developer.mozilla.org/)
- [React Documentation](https://react.dev/)
- [Next.js Documentation](https://nextjs.org/docs)
- [Node.js Documentation](https://nodejs.org/docs/)
- [freeCodeCamp](https://www.freecodecamp.org/)

### Practice Projects:
1. **Todo List App** (React)
2. **Weather App** (React + API)
3. **Blog Website** (Next.js)
4. **REST API** (Node.js + Express)
5. **Full-stack App** (Next.js + API routes)

---

## Useful Commands Reference

### npm Commands:
```bash
npm init -y                    # Initialize new project
npm install package-name       # Install package locally
npm install -g package-name    # Install package globally
npm install --save-dev package # Install as dev dependency
npm start                      # Run start script
npm run build                  # Run build script
npm list                       # List installed packages
npm outdated                   # Check for outdated packages
npm update                     # Update packages
```

### VS Code Shortcuts:
```
Ctrl+Shift+P (Cmd+Shift+P)    # Command palette
Ctrl+` (Cmd+`)                # Toggle terminal
Ctrl+Shift+` (Cmd+Shift+`)    # New terminal
Ctrl+B (Cmd+B)                # Toggle sidebar
Ctrl+Shift+E (Cmd+Shift+E)    # Explorer panel
Ctrl+Shift+X (Cmd+Shift+X)    # Extensions panel
Ctrl+/ (Cmd+/)                # Toggle comment
Alt+Shift+F (Opt+Shift+F)     # Format document
Ctrl+D (Cmd+D)                # Select next occurrence
Ctrl+Shift+L (Cmd+Shift+L)    # Select all occurrences
```

---

**Congratulations!** 🎉 You now have a complete JavaScript development environment set up and ready for building modern web applications with React, Node.js, and Next.js!