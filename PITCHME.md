### こんなカンファレンス行きました
　　　　　　　　　　　　　〜2017/10〜
<br>

<br>
<br>
　　　　　　　　　　　　Naoki Takimoto
---
今回行ったカンファレンス
<br>

* DevFest Tokyo 2017
* Android Bazaar and Conference 2017 Autumn<br>（ABC 2017 Autumn）

---
### DevFest Tokyo 2017

---
DevFest Tokyo 2017
<br>

<span>日時：2017/10/9(月) 10:00〜17:00</span><br>
<span>場所：東京国際交流館</span><br>
<span>主催：[東京で活躍している 14 のコミュニティ](https://tokyo.gdgjapan.org/team)</span><br>
<span>人数：約1,000人</span><br>
<span>内容：[タイムテーブル](https://tokyo.gdgjapan.org/schedule/day1)</span><br>
<span>URL：https://tokyo.gdgjapan.org/</span><br>
<img src="assets/logo_devfest2017.png" style="float: right;" height="100px" />

---
### レポート

---
個人スケジュール
<br>

<div style="padding-right: 75px; padding-left: 75px;">
<div>10:00　オープニング</div>
<div>10:40　クラウドってなんだろ？クラウドを活かすアプリケーション設計とは？</div>
<div>11:30　大半のウェブサービス/アプリは、Firebaseなら簡単で安いですよ</div>
<div>12:10　昼休憩</div>
<div>13:20　ナビゲーションのUIベストプラクティス</div>
<div>14:10　React Nativeアプリをリリースし続けるために、最初に行う8つの取り組み</div>
<div>15:00　FirebaseAnalytics + BigQuery + DataStudio</div>
<div>15:50　FlutterでAndroid/iOS両対応のアプリ開発</div>
</div>

---
オープニング
<br>
<img src="assets/dev_fest_opening.jpg" />

---
オープニング
<br>
<img src="assets/opening_me.jpg" />

---
クラウドってなんだろ？クラウドを活かすアプリケーション設計とは？
 [@sinmetal](https://qiita.com/sinmetal)
<br>

* クラウドのメリット
  * H/Wのイニシャルコストが不要
  * H/Wのリプレースも不要
  * H/Wの構成を容易に変更可能
* クラウドでもH/Wがデータセンターに存在し、日々壊れている
  * H/Wが壊れたとしても、すぐ別のH/Wが生成され蘇る
  * クラウドが壊れることを前提に設計を行う必要あり

---
クラウドってなんだろ？クラウドを活かすアプリケーション設計とは？
<br>

* クラウドを活かすには？
  * 可用性(Availability)をあげる
    * リトライ
    * リクリエイト
  * パフォーマンスを上げる
    * 非同期処理(Queue)
    * 分散処理
* [発表資料](https://goo.gl/X54o2S)

Note:
リトライ
* 様々なレイヤー
  * クライアント・アプリケーションサーバ間
　* アプリケーションサーバ・DBサーバ間
* 適切なタイムアウト設定
* リトライを何回しても、複数のデータが作成されないようにする(冪等性(べきとう))

リクリエイト
* 複数インスタンスを用意
* 起動までにかかる時間を短くする

非同期処理
* 同期的に処理をする必要ないのは、非同期処理にする
* Queueサービスを使って、Taskのリトライ・割当などすると楽

---
大半のウェブサービス/アプリは、Firebaseなら簡単で安いですよ
 [神楽坂やちま](https://qiita.com/Yatima)
<br>

* Firebaseは真のサーバレス
* 使い方は少し独特
* 値段が高いがその分開発人数が減るので、トータルでは安くなる
* 無料枠も多い
* [Cloud Firestore](https://qiita.com/Yatima/items/54ea22d0cea1acc6cbcb)
* [発表資料](https://speakerdeck.com/yatima/apuriha-firebasenarajian-dan-dean-idesuyo)

Note:
様々なサービス
* 開発系
  * realtime database: DB
  * Hosting: HTML
  * Cloud Storage: 画像、動画
  * Cloud Function: API
* 便利系
  * Authentication
  * Cloud Messaging
  * Dynamic Links
* 監視系
  * Analytics
  * Crash Reporing
* 広告系

独特な例
* realtime database: NoSQL、JSONオブジェクトでデータ格納する

---
昼休憩
<br>
<img src="assets/lunch_time.png" />


---
ナビゲーションのUIベストプラクティス
 鈴木拓生
<br>

* 画面のヒエラルキーを考えることが大切
  * 親子関係
  * 並列関係
  * 無関係
  * コレクション
* そのヒエラルキーに基づいたナビゲーションを行う
  * 画面遷移の方法
    * ボタン、タブ、サイドメニュー...
  * 画面を戻る方法
    * 戻るボタン、☓ボタン...

Note:
例）ニュースアプリ
  * 親子関係: 一覧画面と詳細ページ
  * 並列関係: 一覧画面でのカテゴリー切り替え
  * 無関係: 設定、ヘルプ
  * コレクション: ポップアップ

画面のナビゲーション
  * Button
    * 下の階層に遷移するとき使う
  * Tab
    * 関連した項目を並べる
  * Bottom Navigation
    * 関連しない項目を並べる
    * ユーザがよく使う画面を置く
  * Navigation Drawer
    * どの画面からもアクセスができる
    * ユーザがたまにしか使わないが不可欠な画面を置く
  * Contents Navigation
    * 画面とコンテンツを分ける
    * 戻る以外のナビゲーションを置かない

---
React Nativeアプリをリリースし続けるために、最初に行う8つの取り組み
 [中川幸哉](https://qiita.com/Nkzn)
<br>

* React Nativeとは
* JSエンジニアはアプリエンジニアの"当たり前"でつまずく
  * Gradle、XCode
  * Google Play Stpre、iTunes Connect
* 知っておきたいTips
  * applicationId / Bundle Identifier
  * バージョン番号
  * Fablic
  * Fastlane
* [発表資料](https://www.slideshare.net/Nkzn/react-native8-80596018?ref=http://ja.algonote.com/entry/devfest17)

Note:
applicationId / Bundle Identifier
 * アプリが持つ一意のID
 * 会社のドメインの逆順がいいよ
 * Android: ハイフンNG、アンダーバーOK
 * iOS: ハイフンOK、アンダーバーNG
バージョン番号
 * ストアに表示される番号
 * 内部バージョン（これしか使わない）

---
FirebaseAnalytics + BigQuery + DataStudio
 [なかむらさとる](https://qiita.com/satoru_mag)
<br>

* FirebaseAnalyticsって？
  * SDK導入するだけで、ある程度データ収集してくれる
  * 自分でアクション設定してデータ収集も可能
* BigQueryって？
  * 完全なサーバレスモデル
  * Dremelというクエリエンジン
  * クエリ課金、ストレージ課金
* DataStudioって？
  * スライドにBigQuery連携してグラフを表示できる
  * GUIで操作(SQL不要)
* [発表資料](https://www.slideshare.net/ssuser8463f8/firebaseanalyticsbigquerydatastudio?ref=https://www.slideshare.net/ssuser8463f8/slideshelf)

Note:
完全なサーバレスモデル
* H/Wや機能アップデート不要
* VMやCPU、メモリ、ディスクサイズの設定も不要

Dremelというクエリエンジン
* いつでも元気にフルスキャン

---
FlutterでAndroid/iOS両対応のアプリ開発
 [najeira](https://qiita.com/najeira)
<br>

* Flutterとは？
  * クロスプラットフォーム開発
  * 開発言語はDart
  * 自前でUI作成
  * ホットリロード
  * まだアルファ版
* [発表資料](https://www.slideshare.net/najeira/flutterandroidios)

:Note
Dart
* Googleによって開発されたウェブ向けのプログラミング言語
* JavaScriptの代替
* 競合するTypeScriptがGoogle社内の標準プログラミング言語として承認された

---
### Android Bazaar and <br>Conference 2017 Autumn

---
Android Bazaar and Conference 2017 Autumn
<br>

<span>日時：2017/10/14(土) 10:00〜18:00</span><br>
<span>場所：川崎市産業振興会館</span><br>
<span>主催：日本Androidの会</span><br>
<span>人数：約500人</span><br>
<span>内容：[タイムテーブル](http://abc.android-group.jp/2017a/timetables/)</span><br>
<span>　　　[バザール](http://abc.android-group.jp/2017a/bazaar/)</span><br>
<span>URL：http://abc.android-group.jp/2017a/</span><br>
<img src="assets/logo_abc2017a.png" style="float: right;" height="100px" />

---
### レポート

---
個人スケジュール
<br>

<div style="padding-right: 75px; padding-left: 75px;">
<div>10:00　オープニング</div>
<div>10:10　はじめてのボイス・アシスタント<br>　　　---Amazon Echo/Alexa と Google Assistant---</div>
<div>11:10　Android登場10年目～Androidのイマを魅る～</div>
<div>12:00　昼休憩</div>
<div>13:00　Google AR101（TangoからARCore、WebAR）</div>
<div>14:00　はじめてのActions on Google</div>
<div>15:00　はじめてのMonaca ～中学校でもできる本格スマホアプリ開発</div>
<div>16:00　アプリカンではじめるハイブリッドアプリ開発</div>
<div>17:15　恒例☆秋の大LT大会</div>
</div>


