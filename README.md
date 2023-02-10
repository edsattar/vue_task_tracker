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
<style>
</style>
```

## 5. Optional

The YouTube guide deletes the given Welcome vue components, but I decided to keep them for future reference.

### Experimenting with the dev site
```html
<template>
  <h3>Hello World!</h3>
</template>
```

### Emmet
For emmet functionality add the following to the settings.json. To find the file use Ctrl+Shift+P and look for Preferences: Open User Setting (JSON)
```json
"emmet.includeLanguages": {
  "javascript": "javascriptreact",
  "vue-html": "html",
  "vue": "html"
},
```



## 6. Following the YouTube guide

Copy the style for App.vue from the given [repo](https://github.com/bradtraversy/vue-crash-2021)

Put `<div class="container">` around our heading<br>
Create `Heading.vue` component<br>
Export Header in `<script>`<br>
Add `<style>`

In App.vue<br>
Import Header in `<script>`, and add Header to `components:`<br>
Call the component in `<template>`

Use `props:` to pass variables into sub-templates

### Create Button.vue
- style
- @click function

### Create Tasks.vue
- pass 'tasks' array into Tasks
- use `v-for="task in tasks" :key="task.id"` extract the elements

### Create Task.vue
- pass 'task' element into Task
- dynamic class `v-bind:class="[task.reminder ? 'reminder' : '', 'task']`
- add "xmark" icon, @click x to delete
- @dblclick to toggle reminder
- passing $emits up the components hierarcy 
### Compile and Minify for Production

```sh
npm run build
```
