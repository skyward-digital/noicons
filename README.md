<!-- <p align="center">
  <a href="https://skyward.digital/resources/noicons/#gh-light-mode-only" target="_blank">
    <img src="./.github/logo-light.svg" alt="noicons" width="300">
  </a>
  <a href="https://skyward.digital/resources/noicons/#gh-dark-mode-only" target="_blank">
    <img src="./.github/logo-dark.svg" alt="noicons" width="300">
  </a>
</p> -->

# Welcome to NoIcons!

An opinionated, completely blank icon library for you to use any of your custom SVG icons in first party [React](#react) and [Vue](#vue) libraries. No more inline SVGs!

[Add your icon library URL here (or delete this)](#)

<a href="https://github.com/skyward-digital/noicons/releases"><img src="https://img.shields.io/npm/v/noicons" alt="Latest Release"></a>
<a href="https://github.com/skyward-digital/noicons/blob/master/LICENSE"><img src="https://img.shields.io/npm/l/noicons.svg" alt="License"></a>

## Quickstart

Get started in a few simple steps:

1. Fork this repo
1. Add your custom SVG icons to the `src` directory
1. Rename this
1. Add your NPM token to your github secrets
1. Import the icons in your React or Vue project

## Basic Usage

There are a ton of great icon sets out there but most don't provide you with a way to easily use these in code, either providing you with a library where you have to load every icon worse, expecting you to copy and paste svg code inline.

That leads to problems:

1. Maintenance is tricky when you inevitably want to update your icons
2. Extra code created leads to larger bundles and slower (even marginally) sites

Instead, this library provides a simple way to use your own custom SVG icons in React and Vue, without having to copy and paste them inline.

Go from this:

```html
<svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path
    stroke-linecap="round"
    stroke-linejoin="round"
    d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
  />
</svg>
```

To this:

```js
import { BeakerIcon } from '@noicons/react/solid'

<BeakerIcon>
```

## Adding your own icons

To add your own icons, simply add them to the `src` directory. If you have multiple icon styles, group them into subdirectories. For example:

```
src
├── outline
│   ├── Annotation.svg
│   ├── ...
├── solid
│   ├── Annotation.svg
│   ├── ...
├── additional icons if you want (See below)
```

We've preconfigured some default icon styles, but you can add your own rules or remove unused rules if necessary.

If you wish to add or remove icon styles, you'll need to update the `build` script in `package.json` to include or exclude the new icon styles. We've included a default `svgo.config.yaml` file, but you can update this for new icon styles if you'd like more specific rules.

```json
"scripts": {
  "build": "npm run build-outline && npm run build-solid && npm run build-light && npm run build-duotone && npm run build-react && npm run build-vue",
  ...
  "build-light": "rimraf ./light ./optimized/light && svgo --config=svgo.config.yaml -f ./src/light -o ./optimized/light --pretty --indent=2",
  "build-duotone": "rimraf ./duotone ./optimized/duotone && svgo --config=svgo.config.yaml -f ./src/duotone -o ./optimized/duotone --pretty --indent=2",
}
```

## React

First, install `@noicons/react` from npm:

```sh
npm install @noicons/react
```

Now each icon can be imported individually as a React component:

```js
import { BeakerIcon } from '@noicons/react/solid'

function MyComponent() {
  return (
    <div>
      <BeakerIcon className="h-6 w-6 text-blue-500" />
      <p>...</p>
    </div>
  )
}
```

Icons use an upper camel case naming convention and are always suffixed with the word `Icon`.

## Vue

_Note that this library currently only supports Vue 3._

First, install `@noicons/vue` from npm:

```sh
npm install @noicons/vue
```

Now each icon can be imported individually as a Vue component:

```vue
<template>
  <div>
    <BeakerIcon class="h-6 w-6 text-blue-500" />
    <p>...</p>
  </div>
</template>

<script setup>
import { BeakerIcon } from '@noicons/vue/solid'
</script>
```

Icons use an upper camel case naming convention and are always suffixed with the word `Icon`.

<!-- ## Contributing

While we absolutely appreciate anyone's willingness to try and improve the project, we're currently only interested in contributions that fix bugs, for example lightgs like incorrect TypeScript types, or fixing an icon that's been exported with a fill instead of a stroke, etc.

**We're not accepting contributions for new icons or adding support for other frameworks like Svelte or SolidJS**. Instead we encourage you to release your own icons in your own library, and create your own packages for any other frameworks you'd like to see supported. -->

## Thanks

Thanks to the Tailwind team for creating the original [Heroicons](https://github.com/tailwindlabs/heroicons) library, which this project is heavily inspired by.

## License

This library is MIT licensed.
