バックエンドをgoで、フロントエンドをreactで実験する

# バックエンド

## 開発時

開発環境（build用）

```
docker build
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
docker build
docker run -t backend-go-and-frontend-react-backend-prod
```

curl http://localhost:8080
{"id":1,"name":"太郎","e-mail":"thome@example.com"}%

## deploy

google cloud platformにデプロイする。
gcloudをインストールした後に下記実行
- gcloud init
- gcloud builds submit --tag gcr.io/PROJECT_ID/helloworld
- gcloud run deploy --image gcr.io/PROJECT_ID/helloworld
- gcloud run deploy

# フロントエンド

### frontendのイメージを作成してcreate-react-app

 1. docker compose build
 2. docker compose run --rm frontend sh -c "npm install -g create-react-app && create-react-app . --template typescript"



### frontend
firebase hosting

- firebase deploy
