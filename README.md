##usersテーブル
|Column          |Type    | Options     |
|----------------|--------|-------------|
|nickname        |  string| null:false  |
|password        |  string| null:false  |
|birth           |  date  | null:false  |
|e-mail          |string  |null:false   |

#Association
has_many :dreams
has_many :comments
has_many :likes


##dreamsテーブル
|Column                                | Type     |Options                      |
|--------------------------------------|----------|-----------------------------|
|user                                  |references|null:false,foreign_key:true  |
|name                                  |string    |null:false                   |
|text                                  |text      |null:false                   |
| category_id(active_hash)             | integer  | null: false                 |

#Association
belongs_to :user
has_many: comments 
has_many :likes



##commentsテーブル
|Column        | Type      |Options                    |
|--------------|-----------|---------------------------|
|user          |references |null:false,foreign_key:true|
|item          |references |null:false,foreign_key:true|
|text          |text       |null:false                 |

#Association
belongs_to:user 
belongs_to:dream 



#likesテーブル
|Columns   |Type      |Options                    |
|----------|----------|---------------------------|
|user      |references|null:false,foreign_key:true|
|dream     |references|null:false,foreign_key:true|

##Association
belongs_to :user
belongs_to :dream