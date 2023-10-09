---
theme: default
title: 分散型SNS～Fediverseのはなし～
titleTemplate: '%s - Slidev'
info: false
author: Hachian
highlighter: shiki
lineNumbers: false
fonts:
  sans: 'Kosugi Maru'
  serif: 'Kosugi Maru'
  mono: 'HackGen Console NF Regular'
drawings:
  persist: false
transition: slide-left
mdc: true
---

![](/thumbnail.png)

---

## Fediverseとは

### 初手Bing Chat

> [Fediverse（フェディバース）は、「federation（連合）」と「universe（世界）」のかばん語で、SNS・ミニブログ・ブログなどを含むWebサイトの公開やファイルホスティングを行う、独立性を保ったまま相互接続されたサーバー群のことを指します](https://ja.wikipedia.org/wiki/Fediverse)[1](https://ja.wikipedia.org/wiki/Fediverse)[。異なるサーバー（インスタンス）それぞれにおいてユーザーがアカウントを作成し、異なるサーバーに属するアカウント同士が各サーバー上のソフトウェアが実装するオープン標準の通信プロトコルを通して通信できることが特徴です](https://ja.wikipedia.org/wiki/Fediverse)[1](https://ja.wikipedia.org/wiki/Fediverse)[。テキストなどを投稿したり他のアカウントによる投稿を購読することができます](https://ja.wikipedia.org/wiki/Fediverse)[1](https://ja.wikipedia.org/wiki/Fediverse)[。Fediverse上には動画・音声・テキストデータの単純な共有だけでなく、公開範囲の限定やアドレス帳やカレンダーなどの共同編集が可能なソフトウェアも存在します](https://ja.wikipedia.org/wiki/Fediverse)[1](https://ja.wikipedia.org/wiki/Fediverse)。

### 大事なところ(IMO)

- Federation(連合) + Universe(世界・宇宙)
- **サーバー同士が意思疎通**をとれるTwitter(新:X)みたいなもの

---

## 既存のSNSとの違い

<img src="/sns.png" class="h-3/6 mx-auto mb-20px" >

- *サービス(サーバ)をまたいだフォローやメッセージ*が可能

---

## 1サービスでも複数サーバー

<img src="/mastodon.png" class="h-3/6 mx-auto mb-20px" >

- mastodon内にもいろいろなサーバがある
- やり取りできるメッセージはマイクロブログだけではない
  - 画像、動画、ブログポスト、音声など
- 様々なトピックごとにmastodonサーバがたっている
  - ポケモン、どうぶつの森、スプラトゥーン、音ゲーなどなど

---

## 全体像

[英語版WikipediaのFediverseの項目](https://en.wikipedia.org/wiki/Fediverse)にある図がまとまっている

<img src="/image.png" class="float-left h-4/6 mr-10" >

- 既存のFediverseサービスの概略図
- サービスの種類ごとに円でまとまっている
- 線の色は**プロトコル**を表す
  - ActivityPub, Zot, Diaspora, DFRN
  - (ほかにも…)Matrix, AT Protocol
- 同じプロトコルを使っていれば、サーバが違っても、サービスが違っても疎通がとれる

---

## プロトコルとは

- 通信するときの*取り決め*・*ルール*
- ActivityPubはプロトコルの一種
- [W3C](https://www.w3.org/TR/activitypub/)が取り決めている
- ActivityPubにおいて定められるプロトコルは2種類
  - クライアントサーバ間プロトコル
  - サーバ間プロトコル(*連合プロトコル*)
- 例えば以下のようなものが取り決められている。
  - `Object`: 本体・内容
    - `Page`: ウェブページ, `Note`: 短い文章
  - `Actor`: ユーザ・所有者
    - `Group`: グループ
  - `Activity`: アクション
    - `Like`: いいね, `Block`: ブロック, `Follow`: フォロー

---

## SNSを自作できる

- プロトコルにのっとった処理を実装してサーバをたてればFediverseに参加できる
- オープンソースで公開されているサービスであれば、サーバだけたてればOK
- クライアントアプリも作れる(Fediverseに限らずSNS全般でできる。Twitterは改悪)

### 運用面での問題

- プロトコルがたくさんある
  - テスト・実装が厳しそう
- 深いデータベース知識が必要
  - Fediverseに限らず、SNSを作ろうとするとかなり大変
- 盛り上がりとマネタイズ方法のトレードオフ
  - 利用料が高いと人が集まらない
  - 人がたくさんいたら利用料を高くしないといけない

---

## SNSに対する必要条件 (IMO)

<img src="/lane.png" class="float-right h-80% ml-5" >

- *普通*のタイムライン
  - 見たくないものをちゃんと見えなくしてほしい
- 広告モデルは避けたい
  - サブスクモデル、*従量課金*
- グループ細分化
  - 複数レーンで表現
  - 公開範囲の明確化
  - その日の(外交)**エネルギー**の残り具合で見れるTLが違う

<img src="/koko1.png" class="h-1/8 inline ml-30px mr-20px" >
<img src="/koko2.png" class="h-1/8 inline" >

---

## マネタイズ方法を考える

<img src="/maple.png" class="h-3/8 float-right" >

右図は[メイプルストーリー公式より引用](https://maplestory.nexon.co.jp/gameguide/communication/communication/)

- メイプルストーリーのチャットシステム
  - 全体・グループ・友達・ギルド・内緒・**メガホン(課金)**
- 耳栓 vs メガホン
  - 宣伝したい人はメガホンを購入
  - 宣伝を見たくない人は耳栓を購入
  - **1000円のメガホン < 1500円の耳栓**のような

<img src="/0.png" class="float-left h-33% mr-50px mt-20px" >
<img src="/1.png" class="h-33% mt-20px" >
