# README

# テーブル設計

#usesテーブル

| Column     | Type   | option      |
| --------   | ------ | ------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

Association
has_many :prototype
has_many :comments

#prototypesテーブル

| Column     | Type   | option      |
| --------   | ------ | ------------|
| title      | string | null: false |
| catch_copy | text   | null: false |
| concept    | text   | null: false |
| image      |        |             |

Association
has_many :comments
belong_to :users

#commentsテーブル

| Column     | Type      | option      |
| --------   | ------    | ------------|
| text       | text      | null: false |
| user       | reference |             |
| prototype  | reference |             |

Association
belong_to :users
belong_to :prototypes