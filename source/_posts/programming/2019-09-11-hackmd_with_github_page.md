---
layout: post
title:  利用HakcMD編輯GitHub Pages部落格
date:   2019-9-11 23:50:00 +0800
categories: 程式設計, 部落格架設
tags: blog, github, hackmd
---

# 利用HakcMD編輯GitHub Pages部落格

## 前言
:::info
前言部分僅為個人廢話，完全可以跳過沒關係喔~
:::

最近發現，HackMD出了一個功能，可以讓HackMD裡面的檔案與GitHub進行連結，亦即，可以用HackMD這個方便的md文件編輯器，來編輯GitHub上的文件。

這時我就靈光一閃，耶，既然可以用HackMD push筆記到GitHub上面，那我是不是就可以用HackMD來編輯我之前用GitHub Pages內建的Jekyll架的部落格了呢!

原先的部落格有幾個讓我不滿意的地方:
1. 只能用git push的方式更新文章，所以有很多限制
    * 一定要在電腦上操作，手機無法
    * 沒有安裝git的電腦無法
    * 就算裝了git的電腦還是要經過一番設定才能正常更新文章
2. 嘗試了幾個本機端的MarkDown編輯器，都沒有比較滿意的

如果能用HackMD來編輯文章的話，可以解決很多的問題:
1. HackMD是web端的應用程式，完全可以跨平台操作
2. 做為一個MarkDown編輯器，它堪稱完美，而且開發團隊活躍，常常推出令人耳目一新的功能
3. 原本在HackMD上面就打了很多筆記，如果可以與部落格同步就可以無痛轉移這些文章到部落格上

但是，事與願違，經過一番嘗試後發現有個問題。雖然文章可以正常使用HackMD push到GitHub上面，但是因為用GitHub APP進行push的緣故，所以無法觸發GitHub Pages內建的Jekyll Build功能，如果要觸發build的話，需要有verified email的使用者才行(參考[官方文件](https://help.github.com/en/articles/generic-jekyll-build-failures))。

我想的到的解法是用一隻爬蟲(或api，如果github有提供的話)一直監控這個repository，一旦發現有人push東西上去，就重複push一個空白的commit來觸發build。理論上可行，但是感覺很麻煩。

於是乎我到HackMD的粉專發問，小編給我的回應是只能用CI/CD工具進行build，當下看了真是一頭霧水，以前有聽過CI/CD的工具，但一直搞不懂那是做啥用的。

經過一番折騰才讓我研究出來，其實小編的意思是讓我用CI/CD工具對GitHub進行監控，如果有人push東西上去，CI/CD就會把東西clone下來，做好local build之後，再把東西deploy到GitHub上面。這就不是使用GitHub Pages自帶的Jekyll build功能了，而是全部自己來。

總之，搞了一整天總算是成功弄出來了，以下是教學，正文開始~

---
待更新...