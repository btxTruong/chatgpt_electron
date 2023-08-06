# ChatGPT using Electron


## Stack
- Electron
- React
- Vite
- TailwindCSS
- OpenAI API

## Steps
## Setups
1. Initialize the project
```bash
npm create vite@latest
```

2. Update the project
```bash
npx npm-check-updates -u
```
3. Install dependencies
```bash
npm install
```

4. Install `vite-tsconfig-paths` to support `tsconfig.json` path alias. Add `tsconfigPaths()` in `plugins` in `vite.config.ts`
```bash
npm i vite-tsconfig-paths
```

and update `vite.config.ts`
```ts
export default defineConfig({
  plugins: [
    tsconfigPaths(),
...
})
```

5. Install TailwindCSS follow [this guide](https://tailwindcss.com/docs/guides/vite) and [this guide](https://tailwindcss.com/docs/using-with-preprocessors)
- `npm install -D tailwindcss postcss autoprefixer postcss-import`
- `npx tailwindcss init -p`
- Update `tailwind.config.js`
- Update `postcss.config.js`
- Update `src/index.css`
```js
// tailwind.config.js
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

```js
// postcss.config.js
export default {
  plugins: {
    'postcss-import': {},
    'tailwindcss/nesting': {},
    tailwindcss: {},
    autoprefixer: {},
  }
};
```

```css
/* src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

6. Install eslint + prettier: follow [this guide](https://medium.com/tinyso/react-hero-setup-eslint-for-typescript-react-application-d171df2bb408) and [this guide](https://typescript-eslint.io/getting-started)
```bash
  npm install -D prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-react
```
- Create `.prettierrc` file
```json
// .prettierrc
{
  "semi": true,
  "trailingComma": "none",
  "singleQuote": true,
  "printWidth": 120,
  "tabWidth": 2,
  "bracketSpacing": true
}

```
- Update `.eslintrc.cjs` file
```js
//.eslintrc.cjs
module.exports = {
  env: { browser: true, es2020: true },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react/recommended',
    'plugin:react-hooks/recommended',
    'prettier'
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: { ecmaVersion: 'latest', sourceType: 'module' },
  plugins: ['react-refresh', 'prettier'],
  rules: {
    'react-refresh/only-export-components': 'warn',
  },
}
```

7. Create `.editorconfig` file
```
# http://editorconfig.org
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
max_line_length = 120
```

8. Install `react-error-boundary` to handle error in React
```bash
npm install react-error-boundary
```
9. Install UI library follow [tailwindui](https://tailwindui.com/documentation)
```bash
npm install @headlessui/react @heroicons/react
npm install -D @tailwindcss/typography @tailwindcss/forms @tailwindcss/aspect-ratio
```
Setup can be found https://tailwindcss.com/docs/typography-plugin
