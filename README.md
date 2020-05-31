## usersテーブル

|Column|Type|Option|
|------|----|------|
|nickname|string|null:false|
|email|string|null:false, unique:true|
|password|string|null:false, unique:true|





俺だ俺だお！！
１１１１１１
## Assosiation
- has_many :comments
- has_many :items
- has_one :credit_card
- has_one :profile

## profilesテーブル

|Column|Type|Option|
|------|----|------|
|first_name|string|null:false|
|family_name|string|null:false|
|first_name_kana|string|null:false|
|family_name_kana|string|null:false|
|birth_year|integer|---|
|birth_month|integer|---|
|birth_day|integer|---|
|phone＿number|integer|unique:true|
|zip_code|integer(7)|null:false|
|prefecture|integer|null:false|
|city|string|null:false|
|house_number|string|null:false|
|building_name|string|null:false|
|user_id|references|null:false, foreign_key:true|

## Assosiation
- belongs_to :user

## itemsテーブル

|Column|Type|Option|
|------|----|------|
|name|string|null:false, index:true|
|price|integer|null:false|
|description|text|null:false|
|condition|integer|null:false|
|shipping_fee|integer|null:false|
|shipping_form|integer|null:false|
|days_before_shipping|integer|null:false|
|shipping_method|integer|null:false|
|trade_status|integer|null:false|
|category_id|references|null:false, index:true, foreign_key:true|
|user_id|references|null:false, index:true, foreign_key|

## Assosiation
- belongs_to :category
- belongs_to :user
- has_many :images
- has_many :comments
- has_one :order

## categoriesテーブル

## credit_cardsテーブル

|Column|Type|Option|
|------|----|------|
|card_number|integer|null:false, unique:true|
|expiration_year|integer|null:false|
|expiration_momnth|integer|null:false|
|security_code|integer|null:false|
|user_id|references|null:false, foreign_key:true|

## Assosiation
- belongs_to :user

## orderテーブル

## products_imageテーブル

## commentsテーブル
|Column|Type|Option|
|------|----|------|
|body|text|null:false|
|product_id|references|null:false, index:true, foreign_key:true|
|usesr_id|references|null:false, index:true, foreign_key:true|

## Assosiation
- belongs_to :item
- belongs_to :user