# Inline Assets HTML Plugin

A plugin extension of the webpack html-webpack-plugin to inline assets directly into the html file.

## Usage

```js
const HtmlPlugin = require('html-webpack-plugin')
const InlineAssetsHtmlPlugin = require('inline-assets-html-plugin')

const webpackConfig = {
  // ... other config options
  plugins: [
    new HtmlPlugin({ cache: false }), // Turn off caching so hot-reloading can re-inline files on change
    new InlineAssetsHtmlPlugin({
      test: /\.(css|js)$/, // Required: regexp test of files to inline,
      emit: false // Optional: to emit the files that were inlined. Defaults to false (remove the files)
    })
  ]
}
```

### Notes

To inline css files, you also need to have the `mini-css-extract-plugin` installed and set up to generate css files to be inlined.
