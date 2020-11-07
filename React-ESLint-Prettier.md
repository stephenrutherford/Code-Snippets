# Setting up ESLint with Prettier in VSCode for React Applications

## Install ESLint
Run the following if ESLint is not yet installed globally.

```
npm i -G eslint
```

## Init ESLint
In your React app, initialize the ESLint config.

```
eslint --init
```
Use the following answers: 
* To check syntax and find problems
* JavaScript modules
* React
* N
* Browser
* JSON
* Y

## Install Dev Dependecies
Next, install need the following peer dependecies. 
```
npx install-peerdeps --dev eslint-config-react-app
```
```
npm i -D eslint-config-prettier eslint-plugin-prettier prettier
```

## ESLint Rules
Open the `.eslintrc.json` file and replace it with the following settings.
```
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "react-app",
        "prettier"
    ],
    "parserOptions": {
        "ecmaVersion": 2018
    },
    "plugins": [
        "react",
        "prettier"
    ],
    "rules": {
        "prettier/prettier": [
            "error",
            {
                "printWidth": 80,
                "trailingComma": "es5",
                "semi": false,
                "jsxSingleQuote": true,
                "SingleQuote": true,
                "useTabs": true
            }
        ]
    }
}

```

## Workspace Settings
Finally, add the below to your VSCode WorkSpace setings.
```
"settings": {
    "eslint.alwaysShowStatus": true,
    "eslint.nodeEnv": ""
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript"]
  }
```
