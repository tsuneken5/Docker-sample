# ディレクトリ構成

```
$ tree -a -F --dirsfirst
.
├── sample-app/
├── .dockerignore
├── Dockerfile
├── README.md
└── docker-compose.yml
```


# コマンド
## イメージビルド
```
$ docker-compose build
```

## プロジェクト作成
```
$ docker-compose run --rm angular ng new sample-app --directory .
```

## コンテナ起動
```
$ docker-compose up -d
```

# 確認
ブラウザから localhost:4200/ にアクセスして、Angularの画面が表示されれば成功。
