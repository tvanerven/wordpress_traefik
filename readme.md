# A short setup for wordpress under Traefik

## Steps 

Dependencies: Docker.

1. Clone repo
2. `docker compose up -d`
3. The environment is now up and can be visited on 127.0.0.1:8000

In order to use a reverse proxy, use Traefik to route http(s) traffic to the containers. If you want to use HTTPS on a remote host, add following elements to your wp-config.php:

```php
if ( ! defined( 'ABSPATH' ) ) {
	define( 'ABSPATH', dirname(__FILE__) . '/' );
}
if (isset($_SERVER['HTTP_X_FORWARDED_PROTO']) && $_SERVER['HTTP_X_FORWARDED_PROTO'] === 'https') {
        $_SERVER['HTTPS'] = 'on';
}

```


## Recovering from duplicator


If you have a Duplicator clone + install file, simply place them into the created directory. Then go to 127.0.0.1:8000/installer.php to start install process.
