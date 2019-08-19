---
title: 样式
order: 9
---

Remax 默认支持 css/less/sass/stylus，安装你需要的样式，即可使用。如：

```bash
  npm install less   # less 用户
  npm install node-sass   # sass 用户
```

```js
import './index.css';
import './index.less';
import './index.scss';
```

Remax 会自动对 `px` 做处理，如：

```css
.view {
  height: 16px;
}
```

编译成微信小程序:

```css
.view {
  height: 16rpx;
}
```

编译成支付宝小程序:

```
.view {
  height: 1rem;
}
```

如果你不想转换 `px` ，就写成 `PX`，如：

```
.view {
  height: 16PX:
}
```

Remax 同时也支持 [Css Modules](https://github.com/css-modules/css-modules)

所有以 `module.css|less` 结尾的文件都将按照 **Css Modules** 处理。如：

```css
/* index.module.css */

.view {
  display: flex;
}
```

```js
import styles from './index.module.css';

export default function() {
  return <View className={styles.view}> view </View>;
}
```

你也可以通过 `remax.config.js` 配置不同的 Css Modules 匹配规则，关于 Remax 配置请参考 [开发 - 配置](/开发/配置)

## 小程序自定义组件样式

Remax 使用的是 React 组件特性，因此没有自定义组件的概念，你无须关心小程序自定义组件样式的问题

## 样式补全

Remax 没有对样式做补全，在上传代码时，记得开启小程序 **样式补全** 选项