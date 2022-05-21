# Manual setup

Follow the procedure listed below for setup of this repo manually and to add
additional packages or to customize existing setup.

## Create a project with vite

```shell
npm create vite@latest project
cd project
npm install
npm install -D eslint
npm init @eslint/config
```

> Use the following configuration during above command

```
√ How would you like to use ESLint? · style
√ What type of modules does your project use? · esm
√ Which framework does your project use? · react
√ Does your project use TypeScript? · No
√ Where does your code run? · browser
√ How would you like to define a style for your project? · guide
√ Which style guide do you want to follow? · airbnb
√ What format do you want your config file to be in? · JavaScript
```

## Install and configure prettier

```shell
npm install -D --save-exact prettier
echo {}>.prettierrc.json
```

> Add following configuration in `.prettierrc.json`

```json
{
  "singleQuote": false,
  "jsxSingleQuote": false,
  "proseWrap": "always"
}
```

## Install and configure eslint

```
npm install -D eslint-config-prettier eslint-plugin-prettier
```

> In `.eslintrc.js` config file, add "plugin:prettier/recommended" to `extends`
> array

## Install and configure tailwindcss and daisyui

```
npm install daisyui tailwindcss
npx tailwindcss init --postcss
```

> Add `content` and `plugins` in `tailwind.config.js` as shown below

```js
module.exports = {
  content: ["./src/**/*.{html,js,jsx,css}"],
  theme: {
    extend: {},
  },
  plugins: [require("daisyui")],
  daisyui: {
    themes: ["light", "dark"],
  },
};
```

## Run prettier on all files

```
npx prettier -w .
```
