# テーブル設計

## users　テーブル

| Column     | Type   | Options
| ---------- | ------ | 
| email      | string |
| password   | string |
| name       | string |
| profile    | text   |
| occupation | text   |
| position   | text   |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type       | Options
| ---------- | ---------- |
| title      | string     |
| catch_copy | text       | 
| concept    | text       |
| user       | references |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Column    | Type       | Options
| --------- | ---------- |
| text      | text       |
| user      | references |
| prototype | references |

### Association

- belongs_to :users
- belongs_to :prototype