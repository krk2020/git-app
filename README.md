# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :messages
- has_many :groups,though: :users_groups
- has_many :user_groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|users_id|integer|null: false|
### Association
- has_many :users
- has_many :messages
- has_many :users_groups
- has_many :users,though: :users_groups

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

## user_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false|
|groups_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group
