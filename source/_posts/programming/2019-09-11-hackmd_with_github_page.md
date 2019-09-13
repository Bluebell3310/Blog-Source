---
layout: post
title:  利用hackmd與jekyll在github上建立github.io部落格
date:   2019-9-11 23:50:00 +0800
categories: 程式設計
tag: github
tags: blog
---

最近發現，hackmd出了一個功能，可以讓hackmd裡面的檔案與github進行連結，亦即，可以用hackmd這個方便的md文件編輯器，來編輯github上的文件。

這時我就靈光一閃，耶，既然可以用hackmd來編輯，那我之前用jekyll在github page上架設的blog是不是就有救了呢!??

耶，到底行不行阿{-.-} 耶耶耶~~~

不行不行... 因為如果要觸發github page的build，需要具有verify的使用者才行，但是hackmd使用的hithub app沒有email，所以無法
我想的到的解法有，開一個machine user(設定為使用ssh key，[參考](https://developer.github.com/v3/guides/managing-deploy-keys/#machine-users))，然後用一隻爬蟲(或api，如果github有提供的話)一直監控這個網站，一旦發現有人push東西上去，就重複push一個空白的commit。理論上可行，但好麻煩...
