# README

# DB設計

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|Email|string|null: false|

### Association

- has_many :users_groups
- has_many :groups,  through: :users_groups
- has_many :massages


## groupsテーブル

Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association

- has_many :users_groups
- has_many :users  through: :users_groups
- has_many :massages


## users_groupsテーブル

olumn|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association

- belongs_to :user
- belongs_to :group



## massagesグループ
olumn|Type|Options|
|------|----|-------|
|body|text| |
|image|text| |
user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association

- belongs_to :user
- belongs_to :group

