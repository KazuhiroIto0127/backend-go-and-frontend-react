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

```
docker compose build frontend
docker compose run --rm frontend sh -c "npm install"
docker compose up -d frontend
```

下記はすでに実行済みなので、実行不要だが最初に実行したのでメモ
```
docker compose run --rm frontend sh -c "npm create vite@latest"
```

### frontend
firebase hosting

- firebase deploy
