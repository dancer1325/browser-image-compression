# Browser Image Compression
[![npm](https://img.shields.io/npm/v/browser-image-compression.svg)](https://www.npmjs.com/package/browser-image-compression)
[![npm](./coverage/badge.svg)](https://github.com/Donaldcwl/browser-image-compression)
[![npm](https://img.shields.io/npm/l/browser-image-compression.svg)](https://github.com/Donaldcwl/browser-image-compression)

* == Javascript module /
  * if you run | web browser -> compress image

## Features
* compress jpeg, png, webp, and bmp images 
  * | BEFORE uploading -- to the -- application server
    * reduce **resolution** or **storage size** == save bandwidth
* supports **Multi-thread** (web worker)
  * == NON-block compression

## ExampleS
* [here](example)

## How to use?
* _Example:_ [here](example/howToUse.html)

### -- via -- async await syntax
* _Example:_ [here](example/howToUse.html)

### -- via -- Promise.then().catch() syntax
* _Example:_ [here](example/howToUse.html)

## API
### `imageCompression(file: File, options: Options): Promise<File>`
* == MAIN function
* [source code](lib/index.js) & [Options](lib/index.d.md)

#### Caveat
* [browser Canvas object's MAXIMUM size](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#maximum_canvas_size) -- limited by -- EACH browser
  * == ⚠️image -- is resized to -- < EACH browser's MAXIMUM size / restricted ⚠️
  * / remains image's `proportion/ratio`

#### Abort / Cancel Compression
* requirements
  * [browser compatibility](https://caniuse.com/?search=AbortController)
* _Example:_ [here](example/howToUse.html)

### Helper function
* recommended
  * ONLY be used -- by -- advanced users
* see [utils.js's functions](lib/utils.js)

## Browsers support

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari-ios/safari-ios_48x48.png" alt="iOS Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>iOS Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)<br/>Opera |
| --------- | --------- | --------- | --------- | --------- | --------- |
| IE10, IE11, Edge| last 2 versions| last 2 versions| last 2 versions| last 2 versions| last 2 versions

### IE support
* steps
  * ⚠️include the "core-js polyfill" | your project ⚠️
    ```html
    <script src="https://cdnjs.cloudflare.com/ajax/libs/core-js/3.21.1/minified.min.js"></script>
    ```
    * Reason: 🧠this library -- uses -- ES features (_Example:_ Promise API, globalThis)

### Webp support
* webp compression -- is supported on -- MAJOR browsers
  * see [here](https://caniuse.com/mdn-api_offscreencanvas_converttoblob_option_type_parameter_webp)

## About Compression | Web Worker
* if browser supports "OffscreenCanvas" API -> you can use NON-blocking compression
  * OTHERWISE, MAIN thread is used
  * [browser compatibility of "OffscreenCanvas" API](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas#browser_compatibility)  

## Typescript type definitions
* see `package.json`'s `types` 

## About Content Security Policy (CSP)
* if your website has CSP enabled & you want to use Web Worker (== `useWebWorker: true`) -> | response header, add
`content-security-policy: script-src 'self' blob: https://cdn.jsdelivr.net`
  *`blob:` is for loading Web Worker script
  * `https://cdn.jsdelivr.net`
    * allows
      * importing this CDN's library | Web Worker script
  * if you do NOT want to load this library -- from -- CDN -> set your self hosted library URL | `options.libURL`

[dist]: https://github.com/Donaldcwl/browser-image-compression/tree/master/dist
[example]: https://github.com/Donaldcwl/browser-image-compression/tree/master/example
[delivrjs]: https://cdn.jsdelivr.net/
