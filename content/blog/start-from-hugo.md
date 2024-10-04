---
title: "Start From Hugo"
description: ""
summary: "HUGO初學習！終於架自己的網站🤓"
date: 2024-10-04T18:04:20+08:00
lastmod: 2024-10-04T18:04:20+08:00
draft: false
weight: 50
categories: []
tags: []
contributors: []
pinned: false
homepage: false
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---
紀念一下，終於在颱風假的這幾天架設自己的網站（拋棄mxdium, wxxdpress的第一步），第一篇文章簡單記錄一下完成步驟來試試發佈文章！

## 架站步驟
這次使用的是 Hugo 生成網站模板，可以到 [官方網站](https://gohugo.io/templates/) 挑選自己喜歡的主題，不過前幾次下載專案跑的時候一直沒成功，有幾次是遇到專案的某些 library deprecated ==，推測可能有些作者已經沒再維護了。

### 安裝需要的工具
```
brew install npm
brew install hugo
```

### 指令小抄
1. 建立一個新的專案，這裏我挑的是 [Doks Theme](https://themes.gohugo.io/themes/doks/) 。
   ```
   npm create thulite@latest -- --template doks
   ```
2. install dependencies
   ```
   npm install
   ```
3. 試著在 local 端啟動看看，順利的話要可以看得到跑起來的主題
   ```
   npm run dev
   ```
4. 本地端可以看到主題頁面之後，下一步就是使用 Github Actions deploy 到 Github了。參考 [Thulite](https://docs.thulite.io/guides/deploy/github/) 官方文件教學，在專案檔路徑之下建立一個新檔案 .github/workflows/deploy.yml，並把官方文件提供的範例 YAML 檔貼上。（照貼就可以，line 7 branches 名稱要記得跟自己使用的 branch 相同）

5. 到自己的 Github 建立新的專案，專案檔名可以隨意取名。建立 repo 之後到 Github Settings > Pages > 選擇 Github Actions 作為 deploy source。

6. 回到 code, Production folder > hugo.toml 裡面， baseurl 貼上自已 github page 的網址，例如 "https://yxuan0329.github.io/xuansite/" 。
7. 最後推上 github 就大功告成。等 deploy 完成之後就可以到自己的網址瀏覽網頁了 耶 🥳


