webpack-hot-dev-client
---

```bash
npm i webpack-hot-dev-clients
```

webpack

```diff
module.exports = {
  entry: [
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