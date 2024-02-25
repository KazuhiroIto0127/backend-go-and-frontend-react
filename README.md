バックエンドをgoで、フロントエンドをreactで実験する

# バックエンド

## 開発時

開発環境（build用）

```
docker compose build backend-dev
docker compose up -d backend-dev
```

devコンテナ内では下記を実行します。
ホットリロード対応

```
air
```

## 本番

### backendをrun

```
docker compose build backend-prod

docker compose up -d backend-prod
or
docker run -t go-backend-prod
```

# フロントエンド

### frontendのイメージを作成してcreate-react-app

 1. docker compose build
 2. docker compose run --rm frontend sh -c "npm install -g create-react-app && create-react-app . --template typescript"

### frontend
firebase hosting

- firebase deploy
