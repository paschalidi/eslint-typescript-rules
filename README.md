````
yarn add -D eslint prettier @typescript-eslint/{eslint-plugin,parser} eslint-config-{airbnb,prettier} eslint-plugin-{import,jest,jsx-a11y,prettier,react,react-hooks}
````

 .eslintrc
````
{
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "./tsconfig.json",
    "tsconfigRootDir": "."
  },
  "plugins": ["@typescript-eslint", "react-hooks", "jest", "prettier"],
  "env": {
    "browser": true,
    "jest/globals": true,
    "node": true
  },
  "extends": [
    "airbnb",
    "plugin:@typescript-eslint/recommended",
    "plugin:import/typescript",
    "plugin:prettier/recommended",
    "prettier/@typescript-eslint"
  ],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/explicit-function-return-type": "off",
    "import/named": "off",
    "import/export": "off",
    "import/prefer-default-export": "off",
    "react/prop-types": "off",
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "no-unused-expressions": [
      "error",
      { "allowShortCircuit": true, "allowTernary": true }
    ],
    "react/jsx-filename-extension": [
      "error",
      { "extensions": [".jsx", ".tsx"] }
    ]
  }
}
````


## A better approach
```
yarn add eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier eslint-plugin-prettier eslint-plugin-react --dev
```

.eslintrc
```
{
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "./tsconfig.json",
    "tsconfigRootDir": "."
  },
  "env": {
    "browser": true,
    "jest/globals": true,
    "node": true,
    "es6": true
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  },
  "plugins": ["@typescript-eslint", "react", "jest", "prettier"],
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
  ],
  "rules": {
    "react/prop-types": "off", // Disable prop-types as we use TypeScript for type checking
    "@typescript-eslint/explicit-function-return-type": "off"
  }
}
```
