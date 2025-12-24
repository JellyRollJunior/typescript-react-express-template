# Typescript React Template

My personal template for Typescript React projects

#### Includes

- Vite Typescript React template
- React Router
- TailwindCSS
- Prettier Config

## Tutorial

1. Create base react typescript app with Vite

```bash
npm create vite@latest . -- --template react-ts
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

```bash
# Run tests
$ npm run test
```
