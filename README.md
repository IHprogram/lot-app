# テーブル設計

## users テーブル

| Column     | Type       | Option      |
| ---------- | ---------- | ----------- |
| name       | string     | null: false |
| email      | string     | null: false |
| password   | string     | null: false |

### Assosiation

- has_many :lots
- has_many :comments

## lots テーブル

| Column     | Type       | Option      |
| ---------- | ---------- | ----------- |
| result     | string     | null: false |

### Assosiation

- belongs_to :user
- has_many :comments

## comments テーブル

| Column     | Type       | Option                         |
| ---------- | ---------- | ------------------------------ |
| content    | text       |                                |
| user       | references | null: false, foreign_key: true |
| lot        | references | null: false, foreign_key: true |

### Assosiation

- belongs_to :user
- belongs_to :lot