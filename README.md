https://docs.strapi.io/dev-docs/installation/docker

## 起動
```
docker compose up -d
```

##ビルド
```
docker compose exec app yarn build
```

##開発
```
docker compose exec app yarn strapi develop
```

##ビルド
```
docker build \
  --build-arg NODE_ENV=production \
  # --build-arg STRAPI_URL=https://api.example.com \ # Uncomment to set the Strapi Server URL
  -t mystrapiapp:latest \ # Replace with your image name
  -f Dockerfile.prod .
```