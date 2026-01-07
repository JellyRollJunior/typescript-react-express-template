# Typescript React Express Template

My personal template for Typescript React Express projects

#### Includes

-   Client
    -   Vite Typescript React template
    -   React Router
    -   TailwindCSS
    -   Prettier Config
    -   Path Aliasing
        -   @: './src'
    -   Zod
    -   Shared folder as dependency
-   Server
    -   Express, Zod, cors
    -   Dev: Typescript @types/node @types/express
    -   Dev: Nodemon tsx dotenv
    -   Dev: Jest supertest
    -   Build, start, dev scripts
    -   Shared folder as dependency
-   Shared
    -   Typescript

#### Ethos

-   Server is the source of truth
-   Shared has types only, no runtime
-   Shared exists to help client & server agree

## Tutorial - Client

1. Create base react typescript app with Vite

```bash
$ npm create vite@latest . -- --template react-ts
```

2. Install TailwindCSS with Vite: [Link](https://tailwindcss.com/docs/installation/using-vite)
3. Create prettier config
4. Install Prettier TailwindCSS plugin: [Link](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier)
5. Set up React Testing Library (RTL) in Vitest : [Link](https://www.robinwieruch.de/vitest-react-testing-library/)
    - 5a: Install Vitest
    - 5b: Enable HTML in Vitest with jsdom (so RTL can test React components)
    - 5c: Install RTL with [jest-dom](https://github.com/testing-library/jest-dom) matchers
        - 5ci: Latests jsdom uses CommonJS (our project only supports ES6). Install jsdom@22 which uses ES6 modules
    - 5d: Add test setup file, update vite config throughout
    - 5e: Install user-event
6. Install react-router-dom
7. Configure path aliasing (with vite)

```bash
# Run tests
$ npm run test
```

## Tutorial - Server

Reference: [Link](https://www.youtube.com/watch?v=Be7X6QJusJA)

1. Init npm

```bash
$ npm init -y
```

2. Install runtime dependencies

```bash
$ npm install express cors zod
```

3. Install dev dependencies Typescript and node/express types

```bash
# remember: TS is only for development. You run the JS the tsc compiler spits out
$ npm install -D typescript @types/node @types/express
```

4. Init Typescript config and select options for tsconfig.json

```bash
$ npx tsc --init
```

5. Create build / start script
6. Install nodemon & tsx & dotenv

```bash
# nodemon: building our TS automatically on file change
# tsx: (nodejs interpreter for typescript)
$ npm install -D nodemon tsx dotenv

# now we can watch for file changes
$ nodemon --exec tsx ./src/server.ts
```

7. Configure path aliasing

8. Install testing libraries & configure vitest.config.ts for path aliasing

```bash
npm install -D vitest supertest @types/supertest vite-tsconfig-paths
```

## Tutorial - Shared & Monorepo

1. Move client/server/shared into a packages folder

```
repo/
├─ packages/
│  ├─ client
│  ├─ server
│  └─ shared
```

2. Init shared with Typescript

```bash
npm init -y
npm install
npm install -D typescript
```

3. Init repo root to link packages

    - 3a. Create package.json declaration
    - 3b. npm install

4. Create base tsconfig to enforce similar ts config to all packages
