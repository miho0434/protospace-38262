###  　投稿画面
[![Image from Gyazo](https://i.gyazo.com/62df2828dbc5e1e00ffb161a161e6d7f.gif)](https://gyazo.com/62df2828dbc5e1e00ffb161a161e6d7f)

###  　投稿編集
[![Image from Gyazo](https://i.gyazo.com/d5348953bf4487609a6faebd7a60810c.gif)](https://gyazo.com/d5348953bf4487609a6faebd7a60810c)

###  　コメント機能
[![Image from Gyazo](https://i.gyazo.com/6fa48ebac385ea55e077f643a225ec31.gif)](https://gyazo.com/6fa48ebac385ea55e077f643a225ec31)


## usersテーブル
| Column             | Type       | Options                |
| ----------------   | --------   | ------------           |
| email              | string     | null: false ユニーク制約 |
| encrypted_password | string     | null: false            |
| name               | string     | null: false            |
| profile            | text       | null: false            |
| occupation         | text       | null: false            |
| position           | text       | null: false            |

### Asociation
- has_many :prototypes
- has_many :comments



## prototypesテーブル
| Column       | Type       | Options                |
| ----------   | --------   | ------------           |
| title        | string     | null: false            |
| catch_copy   | text       | null: false            |
| concept      | text       | null: false            |
| user         | references | null: false    外部キー |

### Asociation
- belongs to :users
- has many :comments



## commentsテーブル
| Column       | Type       | Options                |
| ----------   | --------   | ------------           |
| content      | text       | null: false            |
| prototype    | references | null: false    外部キー |
| user         | references | null: false    外部キー |

### Asociation
- belongs to :users
- belongs to :comments


