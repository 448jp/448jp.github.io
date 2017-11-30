---
published: true
title: Kobito for Windowsのデータを複数PCで共有する
layout: post
---
ようやくWindows対応しましたね、Kobito。というわけで、Windows版でも複数PCでデータを共有したい！という欲求に駆られて、方法を調べました。あくまで改造なので、AYOR (At Your Own Risk) でお願いします。

方法としては、基本的にMac版と同じです。アプリケーションとは別の場所に作成されるデータベースを、シンボリックリンクを使ってDropboxなどのクラウドストレージで同期する、という流れ。

1. Kobitoを閉じる
1. データベース（C:\Users\ユーザー名\AppData\Roaming\KaitaBrowser\IndexedDB以下）をDropboxなどの適当な場所にコピー
1. C:\Users\ユーザー名\AppData\Roaming\KaitaBrowser\IndexedDBを削除
1. コマンドプロンプトを管理者権限で開く
1. 以下のコマンドでシンボリックリンクを作成する

    ```
    mklink /D C:\Users\ユーザー名\AppData\Roaming\KaitaBrowser\IndexedDB C:\Users\ユーザー名\Dropbox\適当な場所
    ```
    
1. 同期できてハッピー！

設定などは同期されませんのでご注意ください。念のため、データベースは作業前にバックアップしておくのがいいでしょう。

それにしても、「KaitaBrowser」って何なんでしょうか……。Qiitaの逆がKaitaってことか。