# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      ...tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      ...tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      ...tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

```
diplomado-react
├─ deployGithuPage.md
├─ eslint.config.js
├─ index.html
├─ package-lock.json
├─ package.json
├─ playwright.config.ts
├─ pruebas.md
├─ public
│  └─ vite.svg
├─ README.md
├─ src
│  ├─ App.css
│  ├─ App.tsx
│  ├─ assets
│  │  └─ react.svg
│  ├─ components
│  │  ├─ index.ts
│  │  ├─ layout
│  │  │  ├─ Footer.tsx
│  │  │  ├─ Header.tsx
│  │  │  ├─ index.ts
│  │  │  ├─ Layout.tsx
│  │  │  ├─ Menu.tsx
│  │  │  └─ types.ts
│  │  ├─ tasks
│  │  │  ├─ index.ts
│  │  │  ├─ TaskDialog.tsx
│  │  │  ├─ TaskFilter.tsx
│  │  │  ├─ TaskHeader.tsx
│  │  │  ├─ TaskTabla.tsx
│  │  │  └─ type.ts
│  │  └─ users
│  │     ├─ index.ts
│  │     ├─ type.ts
│  │     ├─ UserDialog.tsx
│  │     ├─ UserFilter.tsx
│  │     ├─ UserHeader.tsx
│  │     └─ UserTabla.tsx
│  ├─ config
│  │  └─ env.ts
│  ├─ contexts
│  │  ├─ alert
│  │  │  ├─ Alert.context.tsx
│  │  │  ├─ Alert.provider.tsx
│  │  │  └─ index.ts
│  │  ├─ auth
│  │  │  ├─ Auth.context.tsx
│  │  │  ├─ Auth.provider.tsx
│  │  │  └─ index.ts
│  │  └─ index.ts
│  ├─ helpers
│  │  ├─ error.helper.ts
│  │  ├─ form.helper.ts
│  │  └─ index.ts
│  ├─ hooks
│  │  ├─ index.ts
│  │  ├─ useAlert.ts
│  │  ├─ useAuth.ts
│  │  └─ useAxios.ts
│  ├─ index.css
│  ├─ interfaces
│  │  ├─ actionState.interface.ts
│  │  └─ index.ts
│  ├─ layouts
│  │  └─ PrivateLayout.tsx
│  ├─ lib
│  │  └─ axiosCliente.ts
│  ├─ main.tsx
│  ├─ models
│  │  ├─ index.ts
│  │  ├─ loginModel.ts
│  │  ├─ TaskModel.ts
│  │  └─ userModel.ts
│  ├─ pages
│  │  ├─ private
│  │  │  ├─ index.ts
│  │  │  ├─ PerfilPage.tsx
│  │  │  ├─ TasksPage.tsx
│  │  │  └─ UsersPage.tsx
│  │  └─ public
│  │     ├─ index.ts
│  │     ├─ LoginPage.tsx
│  │     ├─ NotFoundPage.tsx
│  │     └─ UserPage.tsx
│  ├─ routes
│  │  ├─ AppRouter.tsx
│  │  └─ PublicRouter.tsx
│  └─ vite-env.d.ts
├─ tests
│  ├─ auth
│  │  ├─ login.spec.ts
│  │  └─ registration.spec.ts
│  ├─ auth.spec.ts
│  ├─ example.spec.ts
│  ├─ flows
│  │  └─ flow-user-tasks.spec.ts
│  ├─ helpers
│  │  ├─ auth.ts
│  │  ├─ index.ts
│  │  └─ tasks.ts
│  └─ tasks
│     ├─ task.create.spec.ts
│     ├─ task.delete.spec.ts
│     ├─ task.done.spec.ts
│     └─ task.edit.spec.ts
├─ tests-examples
│  └─ demo-todo-app.spec.ts
├─ tsconfig.app.json
├─ tsconfig.json
├─ tsconfig.node.json
└─ vite.config.ts

```