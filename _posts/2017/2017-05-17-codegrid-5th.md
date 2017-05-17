---
published: true
title: 「CodeGrid 5周年記念パーティー」でLTしてきました
layout: post
---
フロントエンドを愛するみなさん、こんにちは。オッキーです。先週の金曜日、「[CodeGrid 5周年記念パーティー](https://atnd.org/events/86816)」に出席し、『フロントエンドのための5つ星Webサービス』というタイトルでLTをしてきました。

LTでは、Web制作の中でも時間に追われがちなフロントエンドに役立つ、3つのWebサービスを紹介しました。本記事では、その捕捉として各サービスをもう少し掘り下げてご紹介します。

当日のスライドは、以下をご覧ください。

<script async class="speakerdeck-embed" data-id="2094404bebd946518bb6f95c67606a0b" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

### チームでも個人でも！ Markdownで情報共有「esa.io」
まず始めにご紹介するのは、巷でも色んなところで名前を聞く機会のある、国産ドキュメント共有サービス「esa.io」です。

<a class="embedly-card" href="https://esa.io/">esa.io - Expertise Sharing Archives for motivated teams.</a><script async src="//cdn.embedly.com/widgets/platform.js" charset="UTF-8"></script>

他にもMarkdownでドキュメントを書いて共有できるサービスはたくさんありますが、中でもesaが優れているのは以下の3点です。

#### 画像などの外部ファイルをサクッとアップできる
アップロードしたいファイルを、ブラウザのエディタ部分にドラッグ＆ドロップするだけで、Amazon S3にアップロード＆表示してくれます。ドキュメントを書いているときって内容に集中したいので、画像へのパスとか考えたりしたくないんですよね。

![画像のアップロード](/images/2017/20170517.gif)

画像だけでなく、PDFやオフィス関連ファイルもOKなので、ドキュメントに関連するファイルを保存しておくのに大変便利です。

#### カテゴリーをフレキシブルに設定、変更できる
私がesaで最も気に入っている機能がこれです。ドキュメントのタイトルを`大カテゴリー/小カテゴリー/文章タイトル`というようにスラッシュ区切りで設定することで、自動的にカテゴリーに分類してくれます。

分類したカテゴリーはツリービューで確認できますし、あとから名称を変えたくなっても、特定カテゴリー以下の名前を一括で変更することができます。最初は適当なカテゴライズにしておいても、あとあと整理できる、という安心感が素晴らしいです。

#### ボタン1つで外部に共有可能
作成したドキュメントは、ボタン1つで外部に公開できます。内容を更新しても、同じURLでアクセスできるところがポイント高し。もちろん、途中で公開を止めることもかんたんです。

![ドキュメントを共有ボタン](/images/2017/20170517_b.png)

これらの機能は、まさに**情報を育てる**ことに向いています。アップデートが激しいフロントエンド界隈のような情報を管理、共有するため、日々便利に使っています。

### タスクを確殺するTODOリスト「Plan」
続いてご紹介するのは、TODOリストの「Plan」です。タスク管理ツールは玉石混合で山ほどありますが、私はここ2〜3年ほどPlanで落ち着き、実際にタスクの処理も大変捗るようになっています。

<a class="embedly-card" href="https://getplan.co/login">Plan: Organize your life</a><script async src="//cdn.embedly.com/widgets/platform.js" charset="UTF-8"></script>

Planの一番の特長は、タスクごとに時間の長さを入力できる点です。しかも、それをカレンダーと連携することができるので、各タスクを1日の時間の中のどこで処理するのかを明示できます。

具体的に見てみましょう。画面左側でタスクを登録し、画面右側に表示されているカレンダーにドラッグ＆ドロップします。タスクの長さもドラッグ＆ドロップでかんたんに変えられます。

![タスク登録](/images/2017/20170517_c.gif)

登録したタスクは、週別、月別表示にも対応しているPlan上で確認できますし、Googleカレンダーに連携しているのでGoogleカレンダー側でチェックすることもできます。もちろんタスク管理機能があるので、タスクごとに未完了・完了のステータスを持つことができ、表示にも反映されます。

これまで私は、さまざまなTODOリスト、タスク管理サービスを使ってきましたが、どうしてもリストに終わらないタスクが残ってしまい、ストレスを抱えることが多々ありました。

Planでは、1日の業務時間の中に入れられる分のタスクしか入れられない（＝入れたとしても当然着手できないし、終わらない）ことが明確になるので、自分のキャパシティを超えていることが直感的に分かります。

フロントエンド領域は特に複雑で入り組んだ業務内容が多く、また変更も発生しやすいため、このようにフレキシブルかつ**実際的**にタスクを管理できるPlanが、ピッタリ合うのではないでしょうか。

### レポート機能が充実の時間管理ツール「Toggl」
Web制作の現場で起こりがちなのが、**事前に見積もった工数と、実際の工数に開きがでてしまう**という問題です。工数を短く見積もると納期が厳しくなりますし、長く見積もってもコストと成果物が見合わず、どちらにしてもクライアントの満足度を下げてしまいます。

見積もり方法にはさまざまなアプローチがありますが、一番大事なのは、**見積もりと実際の工数の差を、必ず振り返る**、ということです。書いてみると当たり前ですが、本当に重要なことです。PDCAというやつですね。

そんなときに役立つのがこの「Toggl」です。

<a class="embedly-card" href="https://toggl.com/">Toggl - Free Time Tracking Software</a><script async src="//cdn.embedly.com/widgets/platform.js" charset="UTF-8"></script>

Togglは、Web/デスクトップ/モバイルアプリでタイマーを動作させて、何のタスクにどのくらいの時間を使ったかを記録できるサービスです。

レポート機能が充実しており、年/月/日別や、クライアント/プロジェクト別にグラフを表示できます。チーム機能もあるため、複数人の時間管理をまとめることも可能です。

![レポート例](/images/2017/20170517_d.png)

私は、2012年からすべての仕事のタスクをTogglで記録しています。月によっては労働時間が400時間を超えていて震えるときもありました（笑……えない）が、PlanとTogglでタスクの見積もりと処理を繰り返してきた結果、ここ1〜2年では大きく見積もりと実際の工数が乖離してしまう、ということはなくなりました。

### まとめ
というわけで、ざっくりと3つのサービスを掘り下げてご紹介しました。みなさんもオススメのサービスがありましたら、こっそり教えてくださいね！