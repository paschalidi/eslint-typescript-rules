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
