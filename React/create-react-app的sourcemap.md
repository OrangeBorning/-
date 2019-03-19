# create-react-app的sourcemap

cra 部署后发现 `sourcemap` 并没有关闭

  webpack.config.js
```js
// Source maps are resource heavy and can cause out of memory issue for large source files.
const shouldUseSourceMap = process.env.GENERATE_SOURCEMAP !== 'false';
```
  build.js
```js
process.env.GENERATE_SOURCEMAP = 'false';
```

cra build默认开启 `sourcemap`; 