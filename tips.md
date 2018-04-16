### TermHere

1. 重置Mac的NVRAM后，TermHere不能右键在当前目录打开终端。

   解决方法:偏好设置->扩展，取消TermHere，然后再选中，然后又能用了。

### vue

1. ``npm run dev``报错:

   > You may use special comments to disable some warnings.
   > Use // eslint-disable-next-line to ignore the next line.
   > Use /* eslint-disable */ to ignore all warnings in a file.

   解决方法:注释掉webpack.base.config.js中的

   ```javascript
   test: /\.(js|vue)$/,
     loader: 'eslint-loader',
     enforce: 'pre',
     include: [resolve('src'), resolve('test')],
     options: {
       formatter: require('eslint-friendly-formatter'),
       emitWarning: !config.dev.showEslintErrorsInOverlay
     }
   ```

   解决问题。