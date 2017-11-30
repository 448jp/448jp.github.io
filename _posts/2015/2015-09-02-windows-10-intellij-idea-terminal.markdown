---
published: true
title: Windows 10でIntelliJ IDEAのTerminalが使えない問題
layout: post
---
#### 問題

Windows 10でIntelliJ IDEAのTerminalを開いてキーボードを叩いても何も入力できない（恐ろしい）。

#### 対策

1. Windows + Rで「ファイル名を指定して実行」ダイアログを開く
2. 「cmd」と入力してコマンドプロンプトを開く
3. コマンドプロンプトのタイトルバーで右クリックして、プロパティを開く
4. 一番下にある「従来のコンソールを使う (再起動が必要)」にチェックを入れ、OKボタンをクリック
5. IntelliJ IDEAで新しいTerminalを開くと問題が解消される（再起動は不要）

#### 参考

[http://stackoverflow.com/questions/31716473/intellij-idea-terminal-broken-with-windows-10](http://stackoverflow.com/questions/31716473/intellij-idea-terminal-broken-with-windows-10)