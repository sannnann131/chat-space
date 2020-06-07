## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
|group_id|integer|null: false, foreign_key: true|

### Association
- has_many :massages
- has_many :groups_users
- has_many :groups through: :groups_users


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|massage|text|null: false|
|image|string|
|posttime|datetime|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|

### Association
- has_many :groups_users
- has_many :users through: :groups_users
- has_many :massages


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user
