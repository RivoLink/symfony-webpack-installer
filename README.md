## Symfony Webpack Installer

### Clone this installer
```sh
git clone https://github.com/RivoLink/symfony-webpack-installer.git
```

### Create new symfony 6.3 project
```sh
cd symfony-webpack-installer

symfony composer create-project symfony/skeleton <project-name> 6.3.*
```

### Replace default configs
```sh
cd <project-name>

rm -f symfony.lock
rm -f composer.lock
rm -f composer.json

cp ../package.json ./package.json
cp ../composer.json ./composer.json
```

### Install project
```sh
symfony composer install

yarn install
```

### Create tests page
```sh
symfony console make:controller TestController --no-interaction
```

### Replace default files
```sh
rm -R assets
rm -R templates
rm -R webpack.config.js

cp -R ../assets ./assets
cp -R ../templates ./templates
cp -R ../webpack.config.js ./webpack.config.js
```

### Build webpack
```sh
yarn encore prod
```

### Start server
```sh
symfony serve --port=8080 -d

open https://127.0.0.1:8080/test
```