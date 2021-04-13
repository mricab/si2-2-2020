## DEPLOYING LARAVEL APP TO HEROKU

- Crear archivo procfile, para establecer la raiz de la aplicación.
echo "web: vendor/bin/heroku-php-apache2 public/" > Procfile

- Crear la aplicación de Heroku y agrega la direccion a sus repositorios
heroku create
heroku apps:rename newname //para renombrar

- Si no se agrega el repositorio a git
git remote add heroku <direccion>

- Obtener la llave de la aplicación o crearla
    - buscar en el archivo .env la variable APP_KEY
    - ejecutar php artisan key:generate --show para obtener una nueva llave.

- Grabar la llave en las variables de ambiente de Heroku
heroku config:set APP_KEY=<llave>

- No utilizar la function assets() de Laravel para cargar app.js
https://laracasts.com/discuss/channels/laravel/heroku-not-loading-appcss-or-appjs

- Subir la aplicación
git add .
git commit -m "mensaje"
git push heroku master

- Agregar los buildpacks que requiere Laravel (si no se puede subir)
heroku buildpacks:add heroku/php

- Abrir la aplicación
heroku open

## SETTING UP THE DATABASE
https://devcenter.heroku.com/articles/heroku-postgresql

- Agregar plugin para la base de datos
heroku addons:create heroku-postgresql:hobby-dev //automaticamente configura la DATABASE_URL

- Actualizar las siguiente credenciales con este comando y obteniendo las credenciales 
de: Database Settings>Database Credentials
heroku config:set DB_CONNECTION=pgsql
heroku config:set DB_DATABASE=d5b73vm85qu154
heroku config:set DB_HOST=ec2-23-23-36-227.compute-1.amazonaws.com
heroku config:set DB_PASSWORD=80b6db44aff7dbd43335c2594d2ab61c9a0b4e619dd48af3163ed60ccea6bbd0
heroku config:set DB_PORT=5432
heroku config:set DB_USER=xhxzszlsbdvlqz

## RUNNING COMMANDS ON HEROKU
para entrar: heroku run bash
para salir: exit