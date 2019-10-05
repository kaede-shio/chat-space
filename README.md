# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


# DB設計

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|VARCHAR(255)|null: false|
|Email|VARCHAR(255)|null: false|
|user_group_id|integer|null: false, foreign_key: true|

### Association

- has_many :users_groups
- has_many :groups,  through: :users_groups
- has_many :massages


## groupテーブル

Column|Type|Options|
|------|----|-------|
|group_name|VARCHAR(255)|null: false|
|user_group_id|integer|null: false, foreign_key: true|
|massage_id|integer|null: false, foreign_key: true|

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



## massageグループ
olumn|Type|Options|
|------|----|-------|
|body|text| |
|image|text| |
user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association

- belongs_to :user
- belongs_to :group

