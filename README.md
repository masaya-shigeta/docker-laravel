# docker-laravel
DockerでLaravel環境をシンプルに作るテンプレート

## 主な環境
- php8.0
- Laravel8.x
- MySQL8.0

## 手順
1. 本リポジトリコードをダウンロード（or `git pull`）
2. ビルドを実行 `docker-compose up -d --build`
3. コンテナ名を確認 `docker-compose ps`
4. 確認したコンテナ名でコンテナ内に入る `docker exec -it docker-laravel_app_1 bash`
5. コンテナ内でLaravelをインストール `composer create-project --prefer-dist "laravel/laravel=8.*" .`
6. `/src/.env` 内のDB設定部分を変更
サンプル
```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=local
DB_USERNAME=user
DB_PASSWORD=password
```
7. コンテナ内でmigrationが実行されれば完了 `php artisan migrate`
