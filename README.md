# reactphp
app.parkingomat.com

# ENV

## PHP

    apt install -y php

## Composer

    sudo apt install -y composer


## [Composer](https://getcomposer.org/download/)

> php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" php -r "if (hash\_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP\_EOL;" php composer-setup.php php -r "unlink('composer-setup.php');"

    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"


## npm

    apt install -y npm


## kill proces

    npx kill-port 8080
    npx kill-port 80
    
    
## Install [reactphp/reactphp: Event-driven, non-blocking I/O with PHP.](https://github.com/reactphp/reactphp)

recommended install: pick required components
    
    composer require react/event-loop react/http
    
quick protoyping only: install all stable components
  
    composer require react/react:^1.2
    

## Run react php [ReactPHP: Event-driven, non-blocking I/O with PHP - ReactPHP](https://reactphp.org/)

web server written in ReactPHP responds with "Hello World!" for every request.


        <?php

        require __DIR__ . '/vendor/autoload.php';

        $http = new React\Http\HttpServer(function (Psr\Http\Message\ServerRequestInterface $request) {
            return React\Http\Message\Response::plaintext(
                "Hello World!\n"
            );
        });

        $socket = new React\Socket\SocketServer('0.0.0.0:80');
        $http->listen($socket);

        echo "Server running at http://localhost:80" . PHP_EOL;

