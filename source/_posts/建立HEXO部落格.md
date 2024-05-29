---
title: 建立HEXO部落格
date: 2024-05-25 23:42:25
tags: hexo
---
[Hexo 官網](https://hexo.io/zh-tw/)
[Node.js 官網](https://nodejs.org/en)
[Git 官網](https://git-scm.com/)

```
node -v
npm -v
npm install -g hexo-cli
hexo -v
```

[終端機操作分享](https://w3c.hexschool.com/git/8dc4619b)

```
1. 前往指令：cd 
2. 建立 Hexo 部落格：hexo init 你的網站名稱
3. 開啟 Hexo 伺服器：hexo server
```

開啟部落格
---
```
hexo server
```

[Markdown 官方教學](https://markdown.tw/)
[Ray 助教部落格 Markdown 教學](https://israynotarray.com/other/20191111/1875438261/)


常用指令
---
```
hexo new 文章名稱
hexo generate
hexo server
hexo clean
hexo deploy
```

客製化
---
```
hexo new page about
```

全域網站加入客製選單(clone 下來到 theme)
---
[hexo-theme-landscape 樣式連結](https://github.com/hexojs/hexo-theme-landscape)
```
git clone --depth 1 https://github.com/hexojs/hexo-theme-landscape themes/landscape
```





用 GitHub Pages 來部署你的部落格
---
[Hexo + GitHub Pages 官方部署說明](https://hexo.io/zh-tw/docs/github-pages#%E4%B8%80%E9%8D%B5%E9%83%A8%E5%B1%AC)
```
npm  i hexo-deployer-git --save
```
清空 _config.yml 的現有資料，並新增以下組態:
```
deploy:
  type: git
  repo: https://github.com/<username>/<project>
  # example, https://github.com/hexojs/hexojs.github.io
  branch: gh-pages
```
執行 hexo clean && hexo deploy 。
瀏覽 <GitHub 用戶名>.github.io 檢查你的網站能否運作。

後續:
url: http://example.com 記得也要改