---
published: true
title: Electronを試してみた
layout: post
---
明けましておめでとうございます。昨年は、多忙を言い訳にずいぶんブログをさぼってしまいました。[弟子](http://better-than-i-was-yesterday.com/)の手前、師匠が情報発信を怠るわけにはいかないので、今年は記事を増やしていきたいと思います。

さて、新年1発目は、[Electron](http://electron.atom.io/)を試した記録です。Electronは、言わずと知れたマルチプラットフォーム向けデスクトップアプリケーションを構築するためのしくみです。

一昔前は、ちょっとしたデスクトップアプリを作るには[Adobe AIR](http://www.adobe.com/jp/products/air.html)が最高だったのですが、今や時代も移り変わり、デスクトップ環境にもHTML5の波が押し寄せているという状況です。

では、早速Electronを使ってみましょう。

### 環境
- Windows 10
- Node.js v6.9.4
- Git

記事内で言及しているコード、ファイル構成、スクリーンショットは、本日時点のものです。

### Electronを最小構成で起動する

#### 1. electron-quick-startリポジトリをクローンする
最小構成のアプリケーションを作るために、[electron-quick-start](https://github.com/electron/electron-quick-start)というリポジトリが公式に用意されていますので、これを利用します。同リポジトリをクローンします。

#### 2. npm install
必要なnpmパッケージをインストールするため、クローンしたリポジトリ上で、`npm install`を実行します。インストールには時間がかかるので、コーヒーでも飲みながら待ちましょう。

#### 3. npm start
アプリを起動するため、`npm start`を実行します。成功すると、Hello World!というアプリが起動します。ウィンドウ右側にGoogle ChromeのデベロッパーツールらしきものがあるためChromeっぽく見えますが、きちんと個別に動作するデスクトップアプリです。

![](/images/20170107.png "electron-quick-startのHello World!アプリ")

### アプリを改変する
本記事では、Electronの詳しい内容については言及を避けます。以下の2点だけ改変をしてみましょう。

#### 1. デベロッパーツールを非表示にする
最終的なアプリとして使うときには不要な、デベロッパーツールを非表示にしてみましょう。main.jsを開き、25-26行目のコードをコメントアウトします。

```js
// Open the DevTools.
mainWindow.webContents.openDevTools()
```

↓

```js
// Open the DevTools.
// mainWindow.webContents.openDevTools()
```

保存し、再度`npm start`を実行すると、デベロッパーツールが消えました。

![](/images/20170107_b.png "デベロッパーツールが消えた")

#### 2. 表示される文字列を変更する
「Hello World!」と表示されている文字列を変更してみましょう。index.htmlを開き、8行目を改変します。

```html
<h1>Hello World!</h1>
```

↓

```html
<h1>こんにちは世界！</h1>
```

保存し、再度`npm start`で、文字列が変わるはずです。簡単！

![](/images/20170107_c.png "Helloからこんにちはへ")

### 配布用パッケージをビルドする
作成したアプリを一般のユーザーに使ってもらうには、各OSに合わせて配布用パッケージをビルドします。公式の手順はかなり複雑なため、ここではサードパーティーかつオープンソースで開発されている[electron-packager](https://github.com/electron-userland/electron-packager)を利用しましょう。

なお、以下の手順はすべて管理者権限が必要になるはずですので、しかるべき環境で実行してください。

#### 1. electronをインストールする
Electron本体も必要なので、`npm install electron -g`でグローバルにインストールします。インストール後、`electron -v`を実行すると、インストールされているElectronのバージョンが表示されます。

#### 2. electron-packagerをインストールする
続いて、`npm install electron-packager -g`でグローバルにelectron-packagerをインストールします。試していませんが、ローカルにインストールしてnpm scriptsから利用することもできるようです。

#### 3. ビルドする
以下のコマンドで、配布用パッケージをビルドします。

```
electron-packager . FirstApp --platform=darwin,win32 --arch=x64
```

`.`の部分では、ビルドするアプリのパスを指定します。ここでは、先ほど作成したアプリのルートで実行するため、`.`を指定しました。

`FirstApp`の部分では、アプリの名前を指定します。具体的には、出力されるディレクトリ名や、実行ファイル名に使われます。

`--platform`では、対象プラットフォームをカンマ区切りで指定します。`darwin`はmacOS向け、`win32`はWindows向けです。

`--arch`では、対象アーキテクチャをカンマ区切りで指定します。`x64`は64ビット向けです。

プラットフォームやアーキテクチャの指定が面倒であれば、`--all`とだけ指定することで、全対象に向けてビルドできます。

なお、私のWindows環境では、管理者権限がないとmacOS向けのビルドができませんでした。

ビルドが成功すると、対象ごとにディレクトリが作成され、その下に配布用パッケージが出力されます。パッケージごと配布し、実行ファイル（Windowsはexe、macOSはapp）を起動すれば、一般のユーザーにも利用可能です。

### まとめ
やはり、手軽にデスクトップアプリを作れることが大きな利点ですね。ウェブの技術で作れるという特徴も、アプリ制作者の裾野を広げるという意味では興味深いところです。

なにかよさげなアプリを作ったら、またブログを書きます！
