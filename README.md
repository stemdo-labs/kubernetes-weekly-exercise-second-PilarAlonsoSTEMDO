# chart-palonso
![Sin título-2024-04-11-1642](https://github.com/stemdo-labs/kubernetes-weekly-exercise-second-PilarAlonsoSTEMDO/assets/166375061/d81ba9ba-06c5-457f-95b3-93d716513597)

## Descripción

Este chart despliega una aplicación Laravel con una base de datos MySQL y opcionalmente phpMyAdmin en un clúster de Kubernetes.


## Valores de Configuración

### Configuraciones Globales

- `namespace`: Nombre del namespace donde se desplegarán los recursos.

### Laravel

- `chartPalonso.image.laravel`: Imagen de Docker para Laravel.
- `chartPalonso.resources.laravel.requests`: Requests de recursos para Laravel.
- `chartPalonso.resources.laravel.limits`: Límites de recursos para Laravel.
- `chartPalonso.persistence.laravel`: Configuración del volumen persistente para Laravel.

### MySQL

- `chartPalonso.image.mysql`: Imagen de Docker para MySQL.
- `chartPalonso.resources.mysql.requests`: Requests de recursos para MySQL.
- `chartPalonso.resources.mysql.limits`: Límites de recursos para MySQL.
- `chartPalonso.persistence.mysql`: Configuración del volumen persistente para MySQL.

### phpMyAdmin (Opcional)

- `chartPalonso.phpmyadmin.enabled`: Habilita o deshabilita phpMyAdmin.
- `chartPalonso.image.phpmyadmin`: Imagen de Docker para phpMyAdmin.
- `chartPalonso.phpmyadmin.auth`: Configuración de autenticación para phpMyAdmin.

### Ingress

- `chartPalonso.ingress.enabled`: Habilita o deshabilita Ingress.
- `chartPalonso.ingress.hosts`: Configuración de los hosts para Laravel y phpMyAdmin.

### CronJob (Opcional)

- `chartPalonso.cronjob.enabled`: Habilita o deshabilita el CronJob de backup.
- `chartPalonso.cronjob.schedule`: Configuración del cron para el backup.
- `chartPalonso.cronjob.image`: Imagen de Docker para el CronJob.
- `chartPalonso.cronjob.persistence`: Configuración del volumen persistente para los backups.

## Ejemplos

### Despliegue de Laravel y MySQL

```sh
helm install my-release -f values-example-laravel.yaml ./chart-palonso

