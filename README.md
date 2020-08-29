# barbour_app


![トップページ](barbourtop.png)

## アプリ概要

個人制作ですので趣味の合う人達が集まって気軽にチャットするという仮定で作っております。

## 主な機能

## ruby,ruby on rails,haml,scss,javascriptsで制作したチャットアプリです。
1 初めての方はsign up、アカウントをお持ちの方はlog in画面でメールアドレスとパスワードを記入。
2 グループを作成orすでにあるグループに入っていただくとすぐにチャット開始できるアプリです。

## 作者

南 由之


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :groups ,through: users_groups
- has_many :users_groups
- has_many :messages

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :users ,through: users_groups
- has_many :users_groups
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group