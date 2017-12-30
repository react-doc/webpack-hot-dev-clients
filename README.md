webpack-hot-dev-client
---

This is an alternative client for [WebpackDevServer](https://github.com/webpack/webpack-dev-server) that shows a syntax error overlay.

It currently supports only Webpack 3.x.

```bash
npm i webpack-hot-dev-clients
```

webpack

```diff
module.exports = {
  entry: [
    // You can replace the line below with these two lines if you prefer the
    // stock client:
    // require.resolve('webpack-dev-server/client') + '?/',
    // require.resolve('webpack/hot/dev-server'),
+   require.resolve('webpack-hot-dev-clients/webpackHotDevClient'),
    "./src/index.js"
  ],
  devtool: 'inline-source-map',
  devServer: {
    contentBase: './dist',
+    hot: true
  },
  plugins: [
    new HtmlWebpackPlugin({
      title: 'Hot Module Replacement'
    }),
+    new webpack.NamedModulesPlugin(),
+    new webpack.HotModuleReplacementPlugin()
  ],
  output: {
    filename: '[name].bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```