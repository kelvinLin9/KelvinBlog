---
title: 建立vite + vue + BS5 環境
date: 2024-04-25 23:42:25
tags: [vite, vue, BS5]
---
## 安裝
### vite

[vite官網](https://vitejs.dev/guide/)

1. 執行安裝最新版本vite指令
![](https://hackmd.io/_uploads/SJiZQZcRn.png)
```
npm create vite@latest
```


2. 輸入專案資料夾名稱
![](https://hackmd.io/_uploads/B13AXWcA3.png)

3. 框架選vue
![](https://hackmd.io/_uploads/SJC3V-5R3.png)

4. 選create-vue(客製化安裝)
![](https://hackmd.io/_uploads/ry7XrWq0h.png)

5. 安裝相關套件
![](https://hackmd.io/_uploads/SJ1tHW9Ah.png)

6. 先不安裝TpyeScript
![](https://hackmd.io/_uploads/SJRvH-cC2.png)

7. JSX不裝(react相關)
    Vue Router要裝
    Pinia要裝
    Unit Testing不裝(相關測試套件)
![](https://hackmd.io/_uploads/HJ0pS-qR2.png)

8. End-to-End(不裝)
    ESLint(要裝)
    Prettier自動格式化工具(要裝)
![](https://hackmd.io/_uploads/r1WgA-cC2.png)

9.  安裝相關套件
```
npm i
```

### Bootstrap
- [BS官網](https://getbootstrap.com/docs/5.3/getting-started/vite/)

1. 安裝 bs sass
```
npm i --save bootstrap @popperjs/core
npm i bootstrap-icons
npm i --save-dev sass
```

2. 引入 bs
```javascript
import '../style/all.scss' // Import our custom CSS
import * as bootstrap from 'bootstrap' // Import all of Bootstrap's JS
import 'bootstrap-icons/font/bootstrap-icons.css'; // Import Bootstrap's icon
```

3. 到 node_modules 的 bootstrapt/scss 資料夾拿這幾個檔案出來放到 style/utils & /base 方便後續客製化
![image](https://hackmd.io/_uploads/S1hO_KJgA.png)


4. 到 all.scss 引入下面檔案(註解掉一些用不到的)
- [官網參考](https://getbootstrap.com/docs/5.3/customize/sass/)
```sass
// 1. Include functions first (so you can manipulate colors, SVGs, calc, etc)
@import "bootstrap/scss/functions";

// 2. Include any default variable overrides here

// 3. Include remainder of required Bootstrap stylesheets (including any separate color mode stylesheets)
@import "../utils/variables";
@import "../utils/variables-dark";

// 4. Include any default map overrides here

// 5. Include remainder of required parts
@import "bootstrap/scss/maps";
@import "bootstrap/scss/mixins";
@import "bootstrap/scss/root";

// 6. Optionally include any other parts as needed
@import "../utils/utilities";
@import "../base/reboot";
// @import "bootstrap/scss/type";
// @import "bootstrap/scss/images";
// @import "bootstrap/scss/containers";
// @import "bootstrap/scss/grid";
// @import "bootstrap/scss/helpers";

// 7. Optionally include utilities API last to generate classes based on the Sass map in `_utilities.scss`
// @import "bootstrap/scss/utilities/api";

// 8. Add additional custom code here

@import "bootstrap/scss/bootstrap";
@import "../utils/helpers";
```

## 設置
為了部屬到 github ，到 vite.config.js 加上
```
base: '/專案名稱/',
```
![image](https://hackmd.io/_uploads/Hy70cKkx0.png)


## 部屬到github
```
npm run build
cd dist
git init
git add -A
git commit -m 'deploy'
git push -f https://github.com/<gitnub ID>/<專案名稱>.git master:gh-pages

```