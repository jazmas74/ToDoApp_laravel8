# laravel8で、「入門Laravelチュートリアル」

参考にさせていただいた記事
https://www.hypertextcandy.com/laravel-tutorial-todo-app-list-folders

## Docker環境について
php8 + nginx + MariaDB 

## dockerで動かす

```
git clone https://github.com/jazmas74/ToDoApp_laravel8.git;
cd ToDoApp_laravel8/src;
cp .env.example .env;
cd ..;
docker-compose up -d;
docker-compose exec app composer update
```
