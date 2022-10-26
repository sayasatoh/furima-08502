## users

|Column  |Type  |Options   |
|---------------|------|----------|
|nickname       |string|null:false|
|email          |string|null:false|
|password       |string|null:false|
|first_name     |string|null:false|
|last_name      |string|null:false|
|first_name_kana|string|null:false|
|last_name_kana |string|null:false|
|birth_day      |date  |nill:false|


### Association
-has_many:products
-has_many:item_purchases

## products

|Column          |Type       |Options   |
|----------------|-----------|----------|
|name            |string     |null:false|
|image           |text       |null:false|
|explanation     |text       |null:false|
|category        |integer    |null:false|
|condition       |integer    |null:false|
|postage_type    |integer    |null:false|
|prefectures     |integer    |null:false|
|preparation_days|integer    |nill:false|
|value           |integer    |null:false|
|user            |references |null:false|


### Association
-belongs_to:user
-has_one:item_purchase

## item_purchases テーブル
| Column        | Type    | Options                        |
| ------------- | ------- | ------------------------------ |
| product       | integer | null: false, foreign_key: true |
| user          | integer | null: false, foreign_key: true |
| purchase_info | integer | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :product
- belongs_to :purchase_info


## purchase_info テーブル

| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| postal_code   | string     | null: false                    |
| prefectures   | integer    | null: false, foreign_key: true |
| city          | string     | null: false                    |
| address       | string     | null: false                    |
| building_name | string     |                                |
| phone_number  | string     | null: false                    |
| item_purchase | integer    | null: false, foreign_key: true |

### Association

-has_one :item_purchase
