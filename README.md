# Inline Assets HTML Plugin

A plugin extension of the webpack html-webpack-plugin to inline assets directly into the html file.

## Installation
```
npm install inline-assets-html-plugin -D
```


## Usage

```js
const HtmlWebpackPlugin = require('html-webpack-plugin')
const InlineAssetsHtmlPlugin = require('inline-assets-html-plugin')

const webpackConfig = {
  // ... other config options
  plugins: [
    new HtmlWebpackPlugin({
      // ... your other html-webpack-plugin options ...
      cache: false  // Turn off caching during development so hot-reloading can re-inline the files on change
    }),
    new InlineAssetsHtmlPlugin({
      test: /\.(css|js)$/, // Required: regexp test of files to inline,
      emit: false // Optional: to emit the files that were inlined. Defaults to false (remove the files)
    })
  ]
}
```

### Notes

To inline css files to a style tag, you also need to have the `mini-css-extract-plugin` installed and set up to generate css files to be inlined.  If you simply use style-loader, the styles will be applied by the js code.
