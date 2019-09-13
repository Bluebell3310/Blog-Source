---
layout: post
title:  Java起手式
date:   2018-7-30 12:00:00 +0800
categories: 程式設計
tag: java
---


一個標準的java起手式如下:

```java=
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello! World!");
    }
}
```

剛開始學的時候，都傻傻地照著寫，但都不知道它是什麼意思，直到最近查到一篇Oracle的文章之後才知道其原理為何。

第一行的class就是java的基本單位，應該沒什麼好講的，重點在第二行的public static void main(String[] args)，剛開始學的時候一直搞不懂他到底為何要這樣寫，查了老半天也看不出個所以然。

首先，public static 應該很好懂，因為要被別人呼叫一定要是public，而因為是應用程式的entry point，也就是入口的部分，一定要一開始就存在，所以static也很好懂，主要是後面那個String[] args的參數，真的很詭異，而這個其實就是拿來「給使用者輸入所選擇功能」用的。

舉例而言，如果我們今天在linux系統下要列出檔案列表要使用"ls"這個應用程式，而如果要連同隱藏檔一起列出來就要在ls後面加上-a的參數，而這個-a就是讀進String[] args的參數，根據讀進來的參數，程式再去作出相應的動作，就是這個用法，搞了老半天終於懂了。

參考資料:

Lesson: A Closer Look at the "Hello World!" Application, Oracle. 2018/7/30, from: https://docs.oracle.com/javase/tutorial/getStarted/application/#MAIN

第六章、Linux 檔案與目錄管理，鳥哥的LINUX私房菜。2018/07/30，檢自:

http://linux.vbird.org/linux_basic/0220filemanager.php#ls