# Ignite Lab - Do Figma ao React

Evento disponibilizado pela [RocketSeat](https://www.rocketseat.com.br/)

### A aplicação teve as seguintes etapas de construção

- Projeto no Figma
- Design System - Criação dos componentes
- Documentação no Storybook
- Deploy automatizado com GitHub Actions
- Criação do Front-End em Vite
- Implementação de testes com Jest no Storybook.

## Tecnologias e ferramentas utilizadas

- [React.JS (Vite)](https://vitejs.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Radix UI](https://www.radix-ui.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Storybook](https://storybook.js.org/)
- [Addon A11y](https://www.npmjs.com/package/@storybook/addon-a11y)
- [Github Actions](https://github.com/features/actions)
- [Jest](https://jestjs.io/pt-BR/)
- [MSW](https://mswjs.io/)

## Projeto no Figma

[Projeto Figma](https://www.figma.com/file/5jg9IRCiuF9DJ1UmbCvmEe/Ignite-Lab-Design-System?node-id=0%3A1)
  
## Configurando o Projeto

## Iniciando o repositório do Git

```bash
git init
```

## Iniciando a pasta do projeto com o Vite

- [https://vitejs.dev/guide/](https://vitejs.dev/guide/)

## Iniciando o projeto

```bash
npm create vite@latest
```

## Configurando o vite no package.json

```json
{
  "name": "lab-ds",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview",
    "storybook": "start-storybook -p 6006"
  },
  "dependencies": {
    "@radix-ui/react-checkbox": "^1.0.0",
    "@radix-ui/react-slot": "^1.0.0",
    "clsx": "^1.2.1",
    "phosphor-react": "^1.4.1",
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@babel/core": "^7.19.3",
    "@types/react": "^18.0.17",
    "@types/react-dom": "^18.0.6",
    "@vitejs/plugin-react": "^2.1.0",
    "autoprefixer": "^10.4.12",
    "babel-loader": "^8.2.5",
    "postcss": "^8.4.17",
    "typescript": "^4.6.4",
    "vite": "^3.1.0"
  }
}
```

## Configuração inicial do .gitignore

```.gitignore
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*

node_modules
dist
dist-ssr
*.local

# Editor directories and files
.vscode/*
!.vscode/extensions.json
.idea
.DS_Store
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?
```

## Removendos pastas padrões para criação da estrutura do projeto

### Arquivos Removidos

- src/App.css
- src/index.css
- src/assets/react.svg

### Arquivos editados

- App.tsx
- main.tsx

## Instalando o TailwindCSS

- [https://tailwindcss.com/docs/installation](https://tailwindcss.com/docs/installation)

```bash
npm install -D tailwindcss  postcss autoprefixer
npx tailwindcss init -p
```

### Adicionando o TailwindCSS no packages.json

```json
{
  "name": "lab-ds",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@babel/core": "^7.19.3",
    "@types/react": "^18.0.17",
    "@types/react-dom": "^18.0.6",
    "@vitejs/plugin-react": "^2.1.0",
    "autoprefixer": "^10.4.12",
    "babel-loader": "^8.2.5",
    "postcss": "^8.4.17",
    "tailwindcss": "^3.1.8",
    "typescript": "^4.6.4",
    "vite": "^3.1.0"
  }
}
```

## Configurando o globals.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
## Configurando os Tokens no TailwindCSS

```cjs
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './src/**/*.tsx',
  ],
  theme: {
    fontSize: {
      'xs': 14,
      'sm': 16,
      'md': 18,
      'lg': 20,
      'xl': 24,
      '2xl': 32,
    },
    colors: {
      black: '#000',
      white: '#fff',
      transparent: 'transparent',
      gray: {
        900: '#121214',
        800: '#202024',
        400: '#7c7c8a',
        200: '#c4c4cc',
        100: '#e1e1e6',
      },
      cyan:{
        500: '#81d8f7',
        300: '#98e1fb',
      }
    },
    extend: {
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
      }
    },
  },
  plugins: [],
}
```

## Adicionando a fonte inter do GoogleFonts no index.html

- [https://fonts.google.com/specimen/Inter?vfquery=inter](https://fonts.google.com/specimen/Inter?vfquery=inter)

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet" />
    <title>Ignite Lab Design System</title>
  </head>
  <body>
    <div id="root"></div>
```

## Instalando o CSLX

- [https://www.npmjs.com/package/clsx](https://www.npmjs.com/package/clsx)

```bash
npm install --save clsx
```

## Adicionando o RadixUI-Slot

- [https://www.radix-ui.com/docs/primitives/utilities/slot#slot](https://www.radix-ui.com/docs/primitives/utilities/slot#slot)

```bash
npm install @radix-ui/react-slot
```

## Adicionando o phosphor-react

- [https://www.npmjs.com/package/phosphor-react](https://www.npmjs.com/package/phosphor-react)

```bash
npm i phosphor-react 
```

## Adicionando o RadixUI-Checkbox

- [https://www.radix-ui.com/docs/primitives/components/checkbox](https://www.radix-ui.com/docs/primitives/components/checkbox)

```bash
npm install @radix-ui/react-checkbox
```

## Criando os componentes

### Componentes criados

- Heading.tsx
- Text.tsx
- Button.tsx
- TextInput.tsx
- Checkbox.tsx

## Adicionando o StoryBook

- [https://storybook.js.org/docs/react/get-started/introduction](https://storybook.js.org/docs/react/get-started/introduction)

```bash
npm i @storybook/storybook-deployer --save-dev
npx sb init --builder @storybook/builder-vite --use-npm 
```

## Configuração final do .gitignore removendo a pasta do StoryBook

```.gitignore
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*

node_modules
dist
dist-ssr
*.local

# Editor directories and files
.vscode/*
!.vscode/extensions.json
.idea
.DS_Store
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?

# Storybook
storybook-static
```

### Configurando o tema Dark no manager.js

```js
import { addons } from '@storybook/addons'
import { themes } from '@storybook/theming'

addons.setConfig({
    theme: themes.dark,
})
```

### Configurando o tema Dark no preview.cjs

```cjs
import { themes } from '@storybook/theming';
import '../src/styles/global.css';

export const parameters = {
  actions: { argTypesRegex: "^on[A-Z].*" },
  controls: {
    matchers: {
      color: /(background|color)$/i,
      date: /Date$/,
    },
  },
  docs: {
    theme: themes.dark,
  },
}
```

### Configurando o main.cjs

```cjs
module.exports = {
    "stories": [
      "../src/**/*.stories.mdx",
      "../src/**/*.stories.@(js|jsx|ts|tsx)"
    ],
    "addons": [
      "@storybook/addon-links",
      "@storybook/addon-essentials",
      "@storybook/addon-interactions"
    ],
    "framework": "@storybook/react",
    "core": {
      "builder": "@storybook/builder-vite"
    },
    "features": {
      "storyStoreV7": true
    },
    viteFinal: (config, { configType }) => {
      if (configType === 'PRODUCTION') {
        config.base = '/rocketseat-ignite-lab-design-system/'
      }
      return config
    },
  }
```

### Adicionando o StoryBook no packages.json

```json
{
  "name": "lab-ds",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview",
    "storybook": "start-storybook -p 6006",
    "build-storybook": "build-storybook"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@babel/core": "^7.19.3",
    "@storybook/addon-actions": "^6.5.12",
    "@storybook/addon-essentials": "^6.5.12",
    "@storybook/addon-interactions": "^6.5.12",
    "@storybook/addon-links": "^6.5.12",
    "@storybook/builder-vite": "^0.2.4",
    "@storybook/react": "^6.5.12",
    "@storybook/testing-library": "^0.0.13",
    "@types/react": "^18.0.17",
    "@types/react-dom": "^18.0.6",
    "@vitejs/plugin-react": "^2.1.0",
    "autoprefixer": "^10.4.12",
    "babel-loader": "^8.2.5",
    "postcss": "^8.4.17",
    "tailwindcss": "^3.1.8",
    "typescript": "^4.6.4",
    "vite": "^3.1.0"
  }
}
```

## Publicando os componentes criados no StoryBook

- Heading.stories.tsx
- Text.stories.tsx
- Button.stories.tsx
- TextInput.stories.tsx
- Checkbox.stories.tsx

## Deploy do Storybook no Github Pages

### Veja aqui a publicação do StoryBook no GitHub Pages

- [https://diegodrcha.github.io/ignite-lab-design-system](https://diegodrcha.github.io/ignite-lab-design-system)
  
## Instalação e uso

### Clone o projeto e acesse a pasta

```bash
git clone https://github.com/diegodrcha/ignite-lab-design-system.git
```

### Siga os passos abaixo

```bash
# Instalar as Dependências
$ npm i

# Iniciar o Servidor em Modo de Desenvolvimento
$ npm run dev

# Iniciar o StoryBook
$ npm run storybook
```

## Adicionando módulo de acessibilidade

Link

- [https://www.npmjs.com/package/@storybook/addon-a11y](https://www.npmjs.com/package/@storybook/addon-a11y)

### Instalando a dependencia

```bash
npm i @storybook/addon-a11y --dev
```

### Adicionando o AddOn no main.cjs

```cjs
module.exports = {
    "stories": [
      "../src/**/*.stories.mdx",
      "../src/**/*.stories.@(js|jsx|ts|tsx)"
    ],
    "addons": [
      "@storybook/addon-links",
      "@storybook/addon-essentials",
      "@storybook/addon-interactions",
      "@storybook/addon-a11y"
    ],
    "framework": "@storybook/react",
    "core": {
      "builder": "@storybook/builder-vite"
    },
    "features": {
      "storyStoreV7": true
    },
    viteFinal: (config, { configType }) => {
      if (configType === 'PRODUCTION') {
        config.base = '/ignite-lab-design-system/'
      }
      return config
    },
  }
```

## Adicionando interações no StoryBook

Links

- [interactions](https://storybook.js.org/docs/react/essentials/interactions)
- [@storybook/addon-interactions](https://storybook.js.org/addons/@storybook/addon-interactions)

### Instalando as dependencias

```bash
npm i @storybook/addon-interactions @storybook/jest @storybook/testing-library @storybook/test-runner --dev
```

Dependencias adicionadas

- @storybook/addon-interactions
- @storybook/jest
- @storybook/testing-library
- @storybook/test-runner

### Adicionando o AddOn do interactions no main.cjs

```cjs
module.exports = {
    "stories": [
      "../src/**/*.stories.mdx",
      "../src/**/*.stories.@(js|jsx|ts|tsx)"
    ],
    "addons": [
      "@storybook/addon-links",
      "@storybook/addon-essentials",
      "@storybook/addon-interactions",
      "@storybook/addon-a11y"
    ],
    "framework": "@storybook/react",
    "core": {
      "builder": "@storybook/builder-vite"
    },
    "features": {
      "storyStoreV7": true,
      "interactionsDebugger": true
    },
    viteFinal: (config, { configType }) => {
      if (configType === 'PRODUCTION') {
        config.base = '/ignite-lab-design-system/'
      }
      return config
    },
  }
```

### Instalando o Axios

```bash
npm i axios
```

### Instalando o MSW - Mock Service Worker

```bash
npm i msw --save-dev
```

### instalando o MSW Storybook Addon

```bash
npm i msw-storybook-addon --save-dev
```

### Iniciando o Service Worker

```bash
npx msw init public/
```

### Adicionando o Axios no main.cjs

```cjs

```cjs
module.exports = {
    "stories": [
      "../src/**/*.stories.mdx",
      "../src/**/*.stories.@(js|jsx|ts|tsx)"
    ],
    "addons": [
      "@storybook/addon-links",
      "@storybook/addon-essentials",
      "@storybook/addon-interactions",
      "@storybook/addon-a11y"
    ],
    "framework": "@storybook/react",
    "core": {
      "builder": "@storybook/builder-vite"
    },
    "features": {
      "storyStoreV7": true,
      "interactionsDebugger": true
    },
    "staticDirs": [
      "../public"
    ],
    viteFinal: (config, { configType }) => {
      if (configType === 'PRODUCTION') {
        config.base = '/ignite-lab-design-system/'
      }
      return config
    },
  }
```

### Editando o arquivo preview.js

```js
import { initialize, mswDecorator } from 'msw-storybook-addon';

// Initialize MSW
initialize();

// Provide the MSW addon decorator globally
export const decorators = [mswDecorator];
```

## Contatos

<div>
    <a href="https://instagram.com/odiegodarocha" target="_blank">
      <img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank">
    </a>
    <a href = "mailto:diegopablorocha@gmail.com">
      <img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank">
    </a>
    <a href="https://www.linkedin.com/in/diegopablodarocha/" target="_blank">
      <img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank">
    </a>
</div>

## Github

- [https://github.com/diegodrcha](https://github.com/diegodrcha)