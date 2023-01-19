<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

# Teslo API

1. Clonar proyecto
2. ```yarn install```
3. Clonar el archivo ```.env.template``` y renombrarlo a ```.env```
4. Cambiar las variables de entorno

|Variable de entorno|Ejemplo|Descripción|
|---|---|---|
| APP_VERSION |1.0.1| Version de la app|
| STAGE |prod| Estado [dev, prod, staging, test] |
| DB_USERNAME | username | nombre de usuario de la db |
| DB_NAME |teslodb | nombre de la db |
| DB_HOST |teslodb | dns name/ip del host  |
| DB_PORT |5432 | puerto donde se conectará en el host |
| DB_PASSWORD | password | contraseña |
| EXTENSIONS_FILE_ACCEPTED | ['jpg','jpeg','png','gif'] | tipos de extenciones permitidas |
| PORT | 3000 | puerto de acceso a la app |
| HOST_API | <http://host:3000/api> | url de conección  |
| JWT_SECRE | SeCrETo| Contraseña de encriptación de JWT|

1. Levantar la base de datos

```$bash
docker-compose up -d
```

6. Levantar: ```yarn start:dev```

7. Ejecutar SEED

```
http://localhost:3000/api/seed
```

## Production notes

Ejecutar este comando

```$bash
docker compose -f docker-compose.prod.yml build
```

## Construccion en multiples arquitecturas

```$bash
docker buildx build \                                            
 --platform linux/amd64,linux/amd64/v2,linux/amd64/v3,linux/arm64 \
 -t pblgllgs/teslo-shop-backend --push .
```
## Construcción multiple arquitecturas y subidda a Digital Ocean
```$bash
docker buildx build \
--platform linux/amd64,linux/amd64/v2,linux/amd64/v3,linux/arm64 \
-t registry.digitalocean.com/teslo-shop/teslo-shop-backend:digital-ocean --push .
```

