# フリマアプリ「FURIMA」
---
## 概要
##### プログラミングスクールにて、スクラムによるアジャイル開発で製作したアプリケーションを紹介します。また本資料では、自身で実装した箇所、および開発を通じて得られた経験についても紹介します。
---
## 接続先情報
- URL http://54.95.116.177/
- ID/Pass
  - ID: y-monbran
  - Pass: y-monbran4649
- テスト用アカウント等
  - 購入者用
    - メールアドレス: sss2@mail.com
    - パスワード: sample2
  - 購入用カード情報
    - 番号： 4242424242424242
    - 期限： 2月20年
    - セキュリティコード：424
  - 出品者用
    - メールアドレス名: sss@mail.com
    - パスワード: sample1
---
## 開発時間・開発体制
- 開発時間
  - 開発期間：約3週間
  - 1日あたりの平均作業時間：10時間
- 開発体制
  - 人数：5人
  - アジャイル型開発（スクラム）
  - Trelloによるタスク管理
---
## 使用技術一覧
- バックエンド
  - Ruby 2.6.5
  - Rails 6.0.0
  - MySQL 5.6.47
  - Devise
  - CarrierWave
  - MiniMagick
- フロントエンド
  - Haml
  - Scss
  - javaScript
  - jQuery
  - Ajax
- テストコード
  - Rspec
  - factory_bot
---
## 動作確認方法
- 接続先およびログイン情報については、前述の通りです。
- 同時に複数の方がログインしている場合に、ログインできない可能性がございます。
- テストアカウントでログイン→トップページから出品ボタン押下→商品情報入力→商品出品
- 確認後、ログアウト処理をお願いします。
---
## 開発担当箇所
### 担当箇所一覧と確認方法
- DB設計
- 商品出品機能（フロントエンド・バックエンド）
  - http://54.95.116.177/items/new にアクセスするとご確認いただけます。
<img width="315" alt="furima-new" src="https://user-images.githubusercontent.com/66059951/92939958-6b881a00-f489-11ea-81e2-87a69d72cf28.png">

- 商品編集機能（フロントエンド・バックエンド）
- 商品削除機能（フロントエンド・バックエンド）
- 商品詳細表示機能（フロントエンド・バックエンド）
<img width="1440" alt="furima-show" src="https://user-images.githubusercontent.com/66059951/92939940-64f9a280-f489-11ea-947e-9f30a2911acf.png">

- カテゴリー機能（フロントエンド・バックエンド）
### 各担当箇所の詳細
- DB設計
  - 概要
    - 必要なテーブル、カラムの設定
    - アソシエーションの決定
  - 担当内容
    - ER図の作成
    - 各テーブルの作成
    - モデルへのアソシエーション、バリデーションの記述
- 商品出品機能
  - 概要
    - 新規に商品を出品する機能
    - 画像、商品名、説明文、地域などの必須項目を選択すると、出品できる
  - 担当内容（フロントエンド・バックエンド）
    - ルーティングの記述、コントローラーの作成
    - Ruby on railsの“Carrierwave”と"MiniMagick"というgemを使用し、画像投稿機能を追加
    - 地域、発送日数などはactive_hashを用いた
    - 必須事項が登録されていないときのために、エラーメッセージを実装
    - カテゴリー選択フォームなどのhaml,scss,javascriptを用いたマークアップ作業
    - 出品完了ページの実装
- 商品編集機能
  - 概要
    - 出品した商品を編集する機能
    - 編集ページにて、画像・商品名・説明文・地域など必須項目を選択し直すと、編集できる
  - 担当内容（フロントエンド・バックエンド）
    - ルーティング、コントローラーの設定
    - 出品機能に準じた商品情報の編集機能、エラーメッセージ、マークアップの実装
- 商品削除機能
  - 概要
    - 出品した商品を削除する機能
    - 商品詳細表示ページにて、削除ボタンを押すと削除できる
  - 担当内容（フロントエンド・バックエンド）
    - ルーティング、コントローラーの設定
- 商品詳細表示機能
  - 概要
    - 出品されている商品の詳細表示機能
    - 商品の画像・商品名・説明文・地域などの詳細が表示されている
  - 担当内容（フロントエンド・バックエンド）
    - ルーティング、コントローラーの設定
    - 商品詳細ページの実装。商品の画像や詳細情報が表示されるページのマークアップ。javascriptでサブ画像を選択すると画像が拡大して表示されるように実装
- カテゴリー機能
  - 概要
    - 出品されている商品のカテゴリー機能
    - Ruby on Railsの"ancestry"というgemを使用しレコードをツリー構造として編成している
  - 担当内容（フロントエンド・バックエンド）
    - ancestryの導入
    - db/seeds.rbにカテゴリーのレコードを記述
    - 商品出品・編集機能でカテゴリーの登録、商品詳細表示機能でカテゴリーの表示ができるように実装
---
## 開発を通じて得られた知見
### 工夫した点
#### チームとして工夫を行った点
最初に全員でほとんどのマークアップを終わらせました。それによってアプリケーションの全体像を早い段階で具体的に掴むことができました。また、商品出品機能が他の多くの機能と関わっていたため、優先的にそこの実装を終わらせることで他の機能の実装がしやすくなりました。
#### 個人として工夫を行った点
データの管理を、ancestryというgemを使ったり、active_hashで管理したり、データの性質によって管理方法を変える工夫をしました。
### 苦労した点
#### チームとして苦労した点
GitHubでコンフリクトが頻発しました。しかし、コンフリクトの解消を行っていく中で、冷静に対処をすれば問題ないということを実感しました。ただ、例えばビューでのコンフリクトはまだしも、マイグレーションファイルなどでコンフリクトを起こしてしまうと厄介なので、重点的にコンフリクトを避けるべきポイントというものがあると感じました。今後は、そもそもコンフリクトが起きないような作業分担や作業方法を模索していきたいです。
#### 個人として苦労した点
商品出品ページと商品編集ページの実装で非常に苦労しました。具体的には、ancestryで管理しているカテゴリー登録のところでjavascriptを使い親カテゴリーから順番にフォームを出現させる実装が大変でした。また、画像投稿フォームもjavascriptで実装しましたが、枚数制限のバリデーションのかけ方などで多くの試行錯誤をしました。
また、商品出品ページと商品編集ページは共通点が多くあるので、どこまで互換性を持たせるかよく考えました。
商品編集ページでは登録済みの内容を初期値としてフォームに表示させる実装を行ったので、その部分は出品ページと編集ページでは明確にやり方を変える必要がありました。コードのリファクタリングにも繋がる部分だと思うので今後も、共通点のあるコードはまとめるという意識は忘れずに持っていたいです。

---
## DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|nickname|string|null: false|
|email|string|null false|
|password|string|null: false|
|first_name|string|null: false|
|family_name|string|null: false|
|first_name_kana|string|null: false|
|family_name_kana|string|null: false|
|birthday|date|null: false|

#### Association
- has_many: profiles, dependent: :destroy
- has_many: comments, dependent: :destroy
- has_many: histories, dependent: :destroy
- has_many :seller_items, foreign_key: "seller_id", class_name: "items"
- has_many :buyer_items, foreign_key: "buyer_id", class_name: "items"
- has_one :credit_card, dependent: :destroy


### addressesテーブル
|first_name|string|null: false|
|family_name|string|null: false|
|first_name_kana|string|null: false|
|family_name_kana|string|null: false|
|post_code|integer(7)|null: false|
|prefecture_code|integer|null: false|
|city|string|null: false|
|house_number|string|null: true|
|building_name|string|------|
|phone_number|string|unique: true|
|user|references|null: false, foreign_key: true|

#### Association
- belongs_to :user
- Gem：jp_prefecture


### itemsテーブル
|Column|Type|Option|
|------|----|------|
|id|string|null: false|
|name|string|null: false|
|introduction|text|null: false|
|price|integer|null: false|
|item_condition|references|null: false, foreign_key: true|
|postage_payer|references|null: false, foreign_key: true|
|prefecture_code|references|null: false, foreign_key: true|
|preparation_day|references|null: false, foreign_key: true|
|category|references|null: false, foreign_key: true|
|status|enum|null: false|
|seller|references|null: false, foreign_key: true|
|buyer|references|foreign_key: true|

#### Association
- has_many :comments, dependent: :destroy
- has_many :favorites
- has_many :item_imgs, dependent: :destroy
- belongs_to :category
- belongs_to_active_hash :item_condition
- belongs_to_active_hash :postage_payer
- belongs_to_active_hash :preparation_day
- belongs_to :seller, class_name: "User"
- belongs_to :buyer, class_name: "User"
- Gem：jp_prefecture


### commentsテーブル
|Column|Type|Option|
|------|----|------|
|comment|text|null: false|
|user|references|null: false, foreign_key: true|
|item|references|null: false foreign_key: true|

#### Association
- belongs_to :user
- belongs_to :item


### item_imgsテーブル
|Column|Type|Option|
|------|----|------|
|url|string|null: false|
|item|references|null: false, foreign_key: true|

#### Association
- belongs_to :item


### brandsテーブル
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

#### Association
- has_many :items


### categoriesテーブル
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

#### Association
- has_many :items


### favoritesテーブル
|Column|Type|Option|
|------|----|------|
|user_id|references|null: false, foreign_key: true|
|item_id|references|null: false, foreign_key: true|

#### Association
- belongs_to :user
- belongs_to :item


### credit_cardsテーブル
|Column|Type|Option|
|------|----|------|
|card_num|integer|null:false, unique: true|
|expiration_year|integer|null:false|
|expiration_month|integer|null:false|
|security_code|integer|null:false|
|user_id|references|null:false, foreign_key: true|

#### Association
- belongs_to :user
