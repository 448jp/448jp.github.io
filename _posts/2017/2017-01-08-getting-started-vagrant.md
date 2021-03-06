---
published: true
title: Vagrantを使ってWindowsにCentOSの仮想マシンを導入する
layout: post
---
新年早々の3連休、みなさんいかがお過ごしですか？　ふとカレンダーを見ると、これ以降3月下旬まで祝日がないんですねぇ……。そろそろ正月気分から抜けなければ。

さて、新年2発目の記事は、タイトルの通りVagrant（ベイグラント）を使ってWindowsにCentOSの仮想マシンを導入する方法を紹介します。

仮想マシンには、1台のPCにさまざまな構成の環境を複数用意できる、開発/テスト用にいつでも作成/破棄できる環境を作れる、などのメリットがあります。

### 環境
- Windows 10
- [VirtualBox](https://www.virtualbox.org) 5.1.12
- [Vagrant](https://www.vagrantup.com/) 1.9.1

記事内で言及しているコード、ファイル構成、スクリーンショットは、本日時点のものです。

### 仮想マシンを導入する

#### 1. VirtualBoxをインストールする
仮想マシンを利用するための環境として、VirtualBoxをインストールします。他にも、VMwareやクラウド経由で利用する方法もあります。ここでは、上記のリンクからWindows用のVirtualBox一式をダウンロードし、インストールします。

#### 2. Vagrantをインストールする
仮想マシンの作成や環境構築を自動化するためのツールとして、Vagrantをインストールします。VirtualBoxと同様に、上記のリンクからWindows用のVagrant一式をダウンロードし、インストールします。

インストール後、PCの再起動を要求されますので、再起動します。

#### 3. 仮想マシンを作成する
さっそく仮想マシンを作成します。作成したいディレクトリに移動し、コマンドプロンプトで以下のコマンドを実行します。

```
vagrant init
```

実行すると、Vagrantfileというファイルが生成されます。表示されているメッセージには、仮想マシンの準備が整った旨が書かれています。

![](/images/20170108.png "vagrant initの実行結果")

#### 4. boxを指定する
Vagrantで利用するboxを指定します。boxとは、仮想マシンのベースとなるイメージファイルのことです。

ここでは、既に用意されているCentOS 6.5を利用するため、Vagrantfileをテキストエディタなどで開き、15行目を以下のように書き換えます。

```ruby
  config.vm.box = "base"
```

↓

```ruby
  config.vm.box = "puphpet/centos65-x64"
```

CentOSの他にもさまざまなboxが用意されており、[Atlas](https://atlas.hashicorp.com/boxes/search)などで探せます。

#### 5. 仮想マシンを起動する
いよいよ仮想マシンを起動します。以下のコマンドを実行します。

```
vagrant up
```

自動的に先ほど指定したboxのダウンロード、およびセットアップが始まります。

![](/images/20170108_b.png "boxのダウンロード中")

完了次第、仮想マシンが起動します。この時点では、仮想マシンは起動しているものの、特にウィンドウなどが開くわけではありませんので注意してください。

また、初回はboxのダウンロードに時間がかかりますが、2回目以降はすぐに起動します。

#### 6. 仮想マシンが起動しているかどうかを確認する
仮想マシンが起動しているかどうかは、以下のコマンドで確認できます。

```
vagrant status
```

Current machine states（現在の仮想マシンの状態）に、running (virtualbox)（VirtualBoxで起動中）と表示されれば、仮想マシンは起動しています。

![](/images/20170108_c.png "vagrant statusの実行結果")

これで、仮想マシンの導入は完了です。実際に扱うには、起動した仮想マシンにログインし、さまざまな操作を行っていくことになります。

なお、仮想マシンを終了するには、以下のコマンドを実行します。

```
vagrant halt
```

### まとめ
Windowsで新しいことに挑戦するとき、macOSやLinuxを（暗黙的に）前提としている記事を参考にしてしまって、うまく動かなかったり、環境がおかしくなってしまったりすること、ありませんか？　私は死ぬほどあります。

もともとよく分かっていないことを始めようとしてつまづくと、元の地点に戻ることも困難であったりするものです。

そんなときに仮想マシンを使うことで、Windowsの環境はそのままに、いくらでも実験できる環境を手に入れることができます。CentOSであれば、Windows固有の問題に悩まされることもありません。

というわけで、ひとまず導入までとなりますが、Vagrantを使ったWindowsでの仮想マシンの導入方法の紹介でした。