## Usage

docker 起動
```
make start
```

ブラウザからGraphiQLへアクセス
http://localhost:3000/graphql

### GraphiQL操作

#### ユーザー登録

```
mutation ($data: UserData!){
  createUser(data: $data) {
    id
    name
    address
  }
}
  
{
  "data": {
    "name": "ヤマダタロウ",
    "address": "岩手県盛岡市"
  }
}
```



#### ユーザー更新
```
mutation ($data: UserData!){
  updateUser(id: 1, data: $data) {
    name
    address
  }
}

{
  "data": {
    "name": "ヤマダタロウ",
    "address": "岩手県盛岡市駅西"
  }
}

```

idを指定して検索

```
query { 
  user(id: 1) { 
    name
  }
}

// 結果
{
  "data": {
    "user": {
      "name": "ヤマダタロウ"
    }
  }
}
```

全検索
```
query { 
  users {
    name
    address
  }
}
```

mysqlのdockerに接続
```
docker exec -it mysql bash  
mysql -u root -proot
use sample
```


make restart
make ps
make kill
make logs
make build
