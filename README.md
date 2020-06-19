# Viewing DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: false|
|password|string|null: false|
|nickname|string|null: false, unique: false|
### Association
- has_many :views


## postsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|------|
|content|text|------|
|area|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :images


## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|posts_id|string|null: false, foreign_key: true|
|src|string|null: false|
### Association
- belongs_to :posts
- has_many :posts, through: :posts_tags