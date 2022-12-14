VS-Code-Editor-Setup
#Install the below extensions:

ESLint
Prettier
Settings
Go to your Visual Stuido Code settings.json file and add the below settings there:

// config related to code formatting
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
"[javascript]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": null
},
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true,
  "source.organizeImports": true
},
"eslint.alwaysShowStatus": true


Linting Setup
In order to lint and format your code automatically according to popular airbnb style guide, I recommend you to follow the instructions. References are as below.

yarn add -D eslint prettier
npx install-peerdeps --dev eslint-config-airbnb-base
yarn add -D eslint-config-prettier eslint-plugin-prettier
Setup Linting Configuration file
Create a .eslint file in the project root and enter the below contents:

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
        "trailingComma": "es6",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true
      }
    ]
  },
  "plugins": ["prettier"]
}
Contact