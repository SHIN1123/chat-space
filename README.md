# DB設計

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|

### Association
- has_many :messages
- has_many :users, through: groups_users

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|index: true, null: false|
|password|string|null: false|
|username|string|null: false|

### Association
- has_many :messages
- has_many :groups, through: groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


