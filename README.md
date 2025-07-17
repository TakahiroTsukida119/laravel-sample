# laravel sample

## 構築手順
```shell
docker compose up -d

# コンテナ内に入る
docker compose exec app /bin/bash

npm install && npm run build
php artisan migrate
```

http://localhost へアクセス
