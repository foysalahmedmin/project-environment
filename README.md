<h1 align="center"> - PROJECT ENVIRONMENT -</h1>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Update Node](#update-node)
  - [Windows](#windows)
  - [Mac](#mac)
- [VS Code Editor Setup](#vs-code-editor-setup)
  - [Extensions](#extensions)
  - [Settings](#settings)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Setup Linting Configuration file](#setup-linting-configuration-file)
- [Contact](#contact)

<!-- UPDATE NODE -->

## Update Node

Please follow the below instructions to update node in your machine:

### Windows

1. Update npm
   ```sh
   npm install npm@latest -g
   ```
2. Clear npm cache
   ```sh
   npm cache clean -f
   ```
3. Install n
   ```sh
   npm install -g n
   ```
4. Update node to latest version
   ```sh
   n latest
   ```

### Mac

1. With Homebrew
   ```sh
   brew update
   brew upgrade node
   ```

<!-- EDITOR SETUP -->

## VS Code Editor Setup

In order to follow along the tutorial series, I recommend you to use Visual Studio Code Editor and install & apply the below extensions and settings.

### Extensions

Install the below extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
- [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
- [Turbo Console Log](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)
- [Cody: AI Coding Assistant with Autocomplete & Chat](https://marketplace.visualstudio.com/items?itemName=sourcegraph.cody-ai)

### Settings

Go to your Visual Stuido Code `settings.json` file and add the below settings there:

```json
{
  "terminal.integrated.tabs.defaultIcon": "clone",
  "terminal.integrated.env.linux": {},
  "editor.fontSize": 16,
  "editor.wordWrap": "on",
  "diffEditor.wordWrap": "on",
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit",
    "source.organizeImports": "explicit"
  },
  "editor.inlineSuggest.suppressSuggestions": true,
  "git.enableSmartCommit": true,
  "[xml]": {
    "editor.defaultFormatter": "redhat.vscode-xml"
  },
  "tailwindCSS.emmetCompletions": true,
  "tailwindCSS.classAttributes": [
    "class",
    "className",
    "ngClass",
    "class:list",
    "activeClass",
    "activeClassName"
  ]
}
```

<!-- LINTING SETUP -->

## Linting Setup

In order to lint and format your code automatically according to popular airbnb style guide, I recommend you to follow the instructions as described in video. References are as below.

### Install Dev Dependencies

1. ~
   ```sh
    npm i -D eslint prettier
    npm i -D eslint-config-prettier eslint-plugin-prettier eslint-plugin-import
    npm i -D prettier-plugin-css-order
   ```
2. For Rect-js
   ```sh
    npm i -D eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-react-refresh
   ```
3. For Next-js
   ```sh
    npm i -D eslint-config-next
   ```
4. For Tailwindcss
   ```sh
    npm i -D prettier-plugin-tailwindcss
   ```

### Setup Linting Configuration file

Create a `.eslintrc.json` file in the project root and enter the below contents:

```json
{
  "root": true,
  "env": {
    "node": true,
    "browser": true,
    "commonjs": true
  },
  "extends": ["eslint:recommended", "prettier"],
  /*
  -- For React-js
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:react/jsx-runtime",
    "plugin:react-hooks/recommended",
    "prettier"
  ],
  -- For Next-js
  "extends": [
    "next/core-web-vitals", 
    "eslint:recommended", 
    "prettier"
  ], 
  */
  "ignorePatterns": ["dist", ".eslintrc.cjs"],
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  },
  "plugins": ["prettier"],
  "rules": {
    "no-undef": "warn",
    "no-unused-vars": "warn",
    "no-console": "warn"
  }
}
```

Create a `.prettierrc.json` file in the project root and enter the below contents:

```json
{
  "plugins": ["prettier-plugin-tailwindcss", "prettier-plugin-css-order"]
}
```

<!-- CONTACT -->

## Contact

Foysal Ahmed - [foysalahmedmin@gmail.com](mailto:foysalahmedmin@gmail.com)
