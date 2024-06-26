## usersテーブル

| Column              | Type       | Options                        |
| ------------------- | ---------- | ------------------------------ |
| email               | string     | null: false, foreign_key: true |
| encrypted_password  | string     | null: false, foreign_key: true |
| name                | string     | null: false, foreign_key: true |
| profile             | text       | null: false, foreign_key: true |
| occupation          | text       | null: false, foreign_key: true |
| position            | text       | null: false, foreign_key: true |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| title       | string     | null: false, foreign_key: true |
| catch_copy  | text       | null: false, foreign_key: true |
| concept     | text       | null: false, foreign_key: true |
| user        | references | null: false, foreign_key: true |

### Association
- has_many   :comments
- belongs_to :user

## commentsテーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| content    | text       | null: false, foreign_key: true |
| prototype  | references | null: false, foreign_key: true |
| user       | references | null: false, foreign_key: true |

### Association
- belongs_to :prototype
- belongs_to :user