# barbour_app


![トップページ](barbourtop.png)

URL: https://barbourapp.herokuapp.com

## 企画背景

趣味が同じ人たちが集まってチャット出来たら素晴らしいと思い作成致しました。

## ・開発環境

言語：Haml・SCSS・javascripts・Ruby・Ruby on Rails ツール: DB:Mysql サーバー：heroku

## 実装機能
チャットアプリ チャット機能全般を要しております。

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