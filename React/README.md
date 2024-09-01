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


# 手順
## プロジェクトフォルダの作成
```
$ mkdir sample-app
```

## イメージのビルド
```
$ docker-compose build
```

## プロジェクトの作成
```
$ docker-compose run --rm react npx create-react-app . --template typescript
```

## コンテナの起動
```
$ docker-compose up -d
```

# 確認
ブラウザから http://localhost:3000/ にアクセスして、Reactの画面が表示されれば成功。

