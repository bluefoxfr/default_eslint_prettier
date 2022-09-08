# My default configuration for eslint and prettier.

## Init eslint

```
yarn add -D eslint
npx eslint --init
```

## DevDependencies

```
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-hooks jest prettier
```

## Eslint config file

In .eslintrc.json

```
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:prettier/recommended"
    ],
    "overrides": [
      {
        "files": ["**/*.test.ts", "**/*.test.js"],
        "env": {
          "jest": true
        }
      }
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module",
        "ecmaFeatures": {
          "jsx": true
        }
    },
    "plugins": [
        "react",
        "@typescript-eslint"
    ],
    "rules": {
      "@typescript-eslint/no-unused-vars": [
        "error",
        { "ignoreRestSiblings": true }
      ],
      "@typescript-eslint/no-explicit-any": "error",
      "@typescript-eslint/indent": "off",
      "@typescript-eslint/explicit-function-return-type": "off",
      "@typescript-eslint/no-non-null-assertion": "off",
      "@typescript-eslint/interface-name-prefix": "off",
      "react/prop-types": "off",
      "react/display-name": "off",
      "react/self-closing-comp": [
        "warn",
        {
          "component": true,
          "html": true
        }
      ],
      "prettier/prettier": ["error", { "singleQuote": true }],
      "no-console": ["error", { "allow": ["warn", "error"] }]
    }
}
```

## Prettier config file

In .prettierrc

```
{
  "singleQuote": true,
  "trailingComma": "all",
  "jsxBracketSameLine": false,
  "bracketSpacing": true
}
```

## In Vscode workspace settings

In .vscode/settings.json

```
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "eslint.validate": ["javascript"]
 }
```
