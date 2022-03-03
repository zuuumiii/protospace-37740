#テーブル設計

## usersテーブル

| Colummn            | Type    | Option                   |
|--------------------|---------|--------------------------|
| email              | stirng  | null:false, unique:true  |
| encrypted_password | string  | null:false               |
| name               | stirng  | null:false               |
| profile            | text    | null:false               |
| occupation         | text    | null:false               |
| position           | text    | null:false               |

## Association
has_many :prototypes
has_many :comments

## prototypesテーブル

| Colummn            | Type       | Option                        |
|--------------------|------------|-------------------------------|
| title              | stirng     | null:false                    |
| catch_copy         | text       | null:false                    |
| concept            | text       | null:false                    |
| user               | references | null:false, foregin_key: true |

## Association
belongs_to :user
has_many :comments

## commentsテーブル

| Colummn            | Type       | Option                        |
|--------------------|------------|-------------------------------|
| content            | stirng     | null:false                    |
| prototype          | references | null:false  foregin_key: true |
| user               | references | null:false, foregin_key: true |

## Association
belongs_to :user
belongs_to :prototype

