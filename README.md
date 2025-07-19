# laravel sample
PHP: 8.4
Laravel: 12.20.0

## 構築手順
```shell
cp .env.example .env

docker compose up -d

# コンテナ内に入る
docker compose exec app /bin/bash
# コンテナ内で実行
composer install
npm install && npm run build
php artisan migrate
```

http://localhost へアクセス
