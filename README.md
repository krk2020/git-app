# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :groups
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|users_id|integer|null: false|
### Association
- has_many :users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text|null: false|
|groups_id|integer|null: false|
|user_id|integer|null: false|
|image|text||
### Association
- belongs_to :user
- belongs_to :group

## groups_messagesテーブル
|Column|Type|Options|
|------|----|-------|
|groups_id|integer|null: false|
|messages_id|integer|null: false|
### Association
- belongs_to :group
- belongs_to :message