# oauth2
[![Latest Stable Version](https://poser.pugx.org/fts/oauth2/v/stable)](https://packagist.org/packages/fts/oauth2)
[![Total Downloads](https://poser.pugx.org/fts/oauth2/downloads)](https://packagist.org/packages/fts/oauth2)
[![License](https://poser.pugx.org/fts/oauth2/license)](https://packagist.org/packages/fts/oauth2)

# 功能
* oauth2.0授权
# 安装
    composer require fts/oauth
### 发布配置文件和公钥私钥
     php artisan vendor:publish
### 创建公钥和私钥
    # private key
    $ openssl genrsa -out privkey.pem 2048
    
    # public key
    $ openssl rsa -in privkey.pem -pubout -out pubkey.pem
### 添加服务提供者
打开 `config/app.php` 并添加以下内容到 providers 数组:
    
    fts\OAuthServiceProvider.php::class
### 中间件
打开 `app/Http/Kernel.php` 并添加以下内容到 routeMiddleware 数组:

    'oauth' => fts\OAuth2\Middleware\OAuth2::class
# 用法
     Router::middleware('oauth')->get('');