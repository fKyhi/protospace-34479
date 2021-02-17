## usersテーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| email      | string     | null: false                    |
| password   | string     | null: false                       |
| name       | string     | null: false                       |
| profile    | text       | NOT NULL                       |
| occupation | text       | NOT NULL                       |
| position   | text       | NOT NULL                       |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | NOT NULL                       |
| catch_copy | text       | NOT NULL                       |
| concept    | text       | NOT NULL                       |
| user       | references |                                |

### Association
- belongs_to :user
- has_many :comments

## commentsテーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| text       | text       | NOT NULL                       |
| user       | references |                                |
| prototype  | references |                                |

### Association
- belongs_to :prototype
- belongs_to :user
