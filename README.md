# vite-plugin-pug

![test](https://github.com/SubZtep/vite-plugin-pug/workflows/npm%20test/badge.svg)

A plugin that makes [Vite](https://vitejs.dev/) parse `<pug src="example.pug"></pug>` in your `index.html`. The rendered template replaces this tag with the compiled markup.

> :information_source: **Vue** single file components don’t require this plugin, adding [Pug](https://www.npmjs.com/package/pug) to the dependency list is enough. — aka `npm i -D pug`

## Features (exists and awaiting)

- [x] CommonJS and ES module builds.
- [x] Handle self-closing `pug` tags.
- [x] Works with multiple `pug` tags.
- [x] Generated _TypeScript_ declarations.
- [x] Reload when saving changes on a `.pug` file.
- [x] Support Pug local variables.
- [ ] **Templates for multiple inputs.** [_WIP_:link:](https://github.com/SubZtep/vite-plugin-pug/tree/multipage/examples/multiroot#readme)
- [ ] _Experimental hot module reloading functionality._
- [ ] _Handle adding or removing files._

## Installation

Using npm:

```sh
$ npm install vite-plugin-pug --save-dev
```

## Configuration

Create a `vite.config.js` [configuration file](https://vitejs.dev/config/) and import the plugin:

```js
// vite.config.(js|ts)
import { defineConfig } from "vite"
import pugPlugin from "vite-plugin-pug"

const options = { pretty: true } // FIXME: pug pretty is deprecated!
const locals = { name: "My Pug" }

export default defineConfig({
  plugins: [
    pugPlugin(options, locals)
  ]
})
```

### Plugin Parameters

| Name    | Required | Description                                                         |
| ------- | -------- | ------------------------------------------------------------------- |
| options | optional | [Pug options](https://pugjs.org/api/reference.html#options) object. |
| locals  | optional | Data object with Pug locals.                                        |

## Usage

### Simple

Create a template file.

```pug
//- index.pug
h1 Hello World
p I'm a cool Vite project!
```

Embed `pug` tag with `src` attribute somewhere.

```html
<!-- index.html -->
<html>
  <body>
    <pug src="index.pug" />
    <script type="module" src="/main.ts"></script>
  </body>
</html>
```

That's it.

> :bulb: Check out **its starter** implementation [in this repository](https://github.com/SubZtep/css-tetris-3d).

## Example

Please find the [examples](examples/multipage) folder in this repository.

## Contribution

~~After Rollup~~ I started to use _**Vite**_ recently but this is not a reason to leave my beloved template format behind. Its [lack of active](https://github.com/marlonmarcello/vite-plugin-pug) Pug plugins made me make one quickly. It does the job to me, I will extend it when I need it. :suspect:

If it doesn't match with your setup please [start a new discussion](https://github.com/SubZtep/vite-plugin-pug/discussions/new) about it, I'm interested to see other workflows. If something is simply not working, please [raise an issue](https://github.com/SubZtep/vite-plugin-pug/issues/new). **PRs certainly welcome!** (.❛ ᴗ ❛.)
