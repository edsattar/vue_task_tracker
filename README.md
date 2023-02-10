# vue-task-tracker

Following this [YouTube guide](https://youtu.be/qZXt1Aom3Cs) by [Traversy Media](https://www.youtube.com/@TraversyMedia)

## 1. Node.js
Make sure you have an up-to-date version of Node.js installed, then run the following command in your command line (without the > sign):

## 2. Install Vue
```
> npm init vue@latest
```

### Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

### Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## 3. Project Setup

```sh
npm install
```
using Vue 3

### Compile and Hot-Reload for Development

```sh
npm run dev
```

## 4. Understanding Structure

`./src/main.js` is kind of the entry point to Vue,

`./src/App.vue` is like the root component

`./index.html` is the single page that's loaded in the browser, similar the base layout, the App.vue gets injected to the following `<div>`.
```html
<div id="app"></div>
```

### Vue file structure

```html
<template></template>
<script>
  import YourComponent from './component/YourComponent.vue'

  export default {
    name: 'App',
    components: {
      YourComponent
    }
  }
</script>
<style></style>
```


### Compile and Minify for Production

```sh
npm run build
```
