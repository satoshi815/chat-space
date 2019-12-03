##usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|mail|string|null: false|


##association
has_many :group_users
has_many :massages
has_many :groups,through: :groups_users



##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

##association
has_many :group_users
has_many :messages
has_many :users,through: :groups_users


##messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|
|group|references|foreign_key: true|
|user|references|foreign_key: true|

##association
belongs_to :user
belongs_to :group


##groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|

##association
belongs_to :group
belongs_to :user


