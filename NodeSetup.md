

  <h3 align="center">Node Setup</h3>

## Install Node 

installs nvm (Node Version Manager)
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
   ```
download and install Node.js (you may need to restart the terminal)
```sh
nvm install 20
   ```

verifies the right Node.js version is in the environment
```sh
node -v # should print `v20.16.0`
   ```
verifies the right npm version is in the environment
```sh
npm -v # should print `10.8.1`

   ```
check for the latest version number and use them here. 

<!-- UPDATE NODE -->

## Update Node

Please follow the below instructions to update node in your machine:

### Windows or linux

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

### For Mac

1. With Homebrew
   ```sh
   brew update
   brew upgrade node
   ```

<!-- INSTALL & UPDATE YARN -->

## Install and Update yarn

Please follow the below instructions to install or update yarn in your machine.

### On Windows or linux

1. Install yarn
   ```sh
   npm install -g yarn
   ```
2. Update yarn
   ```sh
   yarn set version latest
   ```

### On Mac

1. Install yarn
   ```sh
   brew install yarn
   ```
2. Update yarn
   ```sh
   brew update
   brew upgrade yarn
   ```

<!-- EDITOR SETUP -->

## VS Code Editor Setup

In order to follow along the tutorial series, I recommend you to use Visual Studio Code Editor and install & apply the below extensions and settings.

### Extensions

Install the below extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)

### Settings

Go to your Visual Stuido Code `settings.json` file and add the below settings there:

```json
// config related to code formatting
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact",
    "vue"
  ],
  "eslint.format.enable": true,
```

### Set Line Breaks

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you dont do that, you will get errors in my setup.

<!-- LINTING SETUP -->

## Linting Setup

In order to lint and format your code automatically according to popular airbnb style guide, I recommend you to follow the instructions as described in video. References are as below.

### Install Dev Dependencies

```sh
sudo yarn add -D eslint prettier
sudo npx install-peerdeps --dev eslint-config-airbnb-base
sudo yarn add -D eslint-config-prettier eslint-plugin-prettier
```

### Dev dependency
```sh
"devDependencies": {
    "eslint": "^8.2.0",
    "eslint-config-airbnb-base": "15.0.0",
    "eslint-config-prettier": "^9.1.0",
    "eslint-plugin-import": "^2.25.2",
    "eslint-plugin-prettier": "^5.1.3",
    "prettier": "^3.3.1"
  }
```

### Setup Linting Configuration file

Create a `.eslintrc.json` file in the project root and enter the below contents:

```json
{
  "extends": ["prettier", "airbnb-base"],
  "parserOptions": {
    "ecmaVersion": 12
  },
  "env": {
    "commonjs": true,
    "node": true
  },
  "rules": {
    "no-console": 0,
    "indent": 0,
    "linebreak-style": 0,
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true
      }
    ]
  },
  "plugins": ["prettier"]
}
```

