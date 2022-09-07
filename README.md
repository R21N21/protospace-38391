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

## users テーブル

| column             | Type   | options                        |
| ------------------ | ------ | ------------------------------ |
| email              | string | null: false, foreign_key: true |
| encrypted_password | string | null: false                    |
| name               | string | null: false                    |
| profile            | text   | null: false                    |
| occupation         | text   | null: false                    |
| position           | text   | null: false                    |

### association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| column             | Type       | options                        |
| ------------------ | ---------- | ------------------------------ |
| title              | string     | null: false                    |
| catch_copy         | text       | null: false                    |
| concept            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### association

- belongs_to :user
- has_many :comments

## comments テーブル

| column             | Type       | options                        |
| ------------------ | ---------- | ------------------------------ |
| content            | text       | null: false                    |
| prototype          | references | null: false, foreign_key: true |
| user               | references | null: false, foreign_key: true |

## association

- belongs_to :user
- belongs_to :prototype