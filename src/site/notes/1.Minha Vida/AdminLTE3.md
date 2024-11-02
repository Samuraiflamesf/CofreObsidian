---
{"dg-publish":true,"permalink":"/1-minha-vida/admin-lte-3/","tags":["pessoal/estudos","pessoal/web"]}
---

[Voltar](1.LIFE/index)
## Configurando ambiente
- [Laragon](https://laragon.org/download/index.html)
    - php 8.1
    - MySQL
- [Composer](https://getcomposer.org/download/)
- [Laravel 10](https://laravel.com/docs/11.x/installation#creating-a-laravel-project)
    - [TailwindCss](https://daisyui.com/docs/install/)
    - [AdminLTE3](https://github.com/jeroennoten/Laravel-AdminLTE)
### Criando Projeto + AdminLTE
1. Atravel do Composer:
    ``` 
    composer create-project laravel/laravel example-app
    ```
2. Iniciando server:
    ``` 
    php artisan serve
    ```
3. Migration/ Fazendo as tabelas no banco de dados
    ```
    php artisan migrate:install
    ```
    ```
    php artisan migrate:status
    ```
    ```
    php artisan migrate
    ```
4. Install [AdminLTE](https://github.com/jeroennoten/Laravel-AdminLTE/wiki/Usage) 
    ```
    composer require jeroennoten/laravel-adminlte
    ```
    ```
    php artisan adminlte:install
    ```
    ```
    composer require laravel/ui
    ```
    ```
    php artisan ui bootstrap --auth
    ```
    ```
    php artisan adminlte:install
    ```
    ```
    php artisan adminlte:plugins install --plugin=icheckBootstrap
    ```
5. Trocando linguagem do AdminLTE para "pt-br"
    Ir em config/app.php, realizar troca:
    ```
    'locale' => 'pt-br',
    ```

### References
1. [Curso Laravel](https://www.youtube.com/watch?v=HFnn0DXQgWA&list=PLwXQLZ3FdTVH5Tb57_-ll_r0VhNz9RrXb&index=4)
2. [Laravel + Admin3](https://www.youtube.com/watch?v=d9uRb3YQytI&t=24s)
  